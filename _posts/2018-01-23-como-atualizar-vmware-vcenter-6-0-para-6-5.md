---
ID: 4361
post_title: >
  Como atualizar VMware vCenter 6.0 para
  6.5
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2rypifx
published: true
post_date: 2018-01-23 09:00:24
---
Olá Homelabers!

Qual <strong>versão do VMware vSphere</strong> vocês estão rodando em seus labs ou ambientes produtivos?

No meu lab, por diversos motivos, eu estou rodando o vSphere versão 6.0 e nessa série de posts, vou mostrar <strong>como fazer o upgrade para o vSphere versão 6.5</strong>, começando pelo <strong>VMware vCenter Server 6.5</strong>

<img class="aligncenter size-full wp-image-4436" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/migrate2vcsa-300x269-300x269.jpg" alt="" width="300" height="269" />
<h2>Recomendações iniciais:</h2>
Se você for planejar um upgrade, seja em produção ou em seu lab, é muito importante que você <a href="https://docs.vmware.com/en/VMware-vSphere/6.5/vsphere-esxi-vcenter-server-65-upgrade-guide.pdf" target="_blank" rel="noopener"><strong>leia a documentação disponível</strong></a> e o <strong><a href="https://docs.vmware.com/en/VMware-vSphere/6.5/rn/vsphere-esxi-vcenter-server-65-release-notes.html" target="_blank" rel="noopener">Release Notes</a></strong> da versão, <strong>planeje bem a mudança</strong>, <strong>valide se o seu hardware é suportado</strong> - <a href="https://www.vmware.com/resources/compatibility/" target="_blank" rel="noopener">consulte a HCL</a> - e se possível <strong>não faça a mudança direto em produção</strong>. Se você não tiver um ambiente de homologação, ao menos <strong>faça testes</strong> com um ambiente nested para você se <strong>acostumar com a migração e evitar surpresas</strong>.

E o <strong>primeiro componente</strong> que você deve <strong>atualizar é o vCenter Server</strong>.
<h2>Preparativos:</h2>
<img class="aligncenter size-large wp-image-4431" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/vSphere-6.5-Documents-644x191.png" alt="" width="644" height="191" />
<ul style="list-style-type: square;">
 	<li>Baixe o ISO <strong>antes da janela de manutenção</strong>, pode parecer obvio mas...</li>
 	<li><strong>Desligue o DRS</strong> antes a atualização.</li>
 	<li>O processo envolve um I<strong>P temporário</strong> para a nova VM do VCSA, de modo que o antigo e o novo IP vão estar online simultaneamente para transferir dados. <strong>Providencie o IP antecipadamente</strong>.</li>
 	<li>Adicione o <strong>IP temporário a quaisquer regras de firewall</strong> envolvendo o VCSA existente.</li>
 	<li>Verifique se você tem <strong>algum plugin</strong> (Anti-Vírus, Backup, vRA, etc) e certifique-se da <strong>compatibilidade com a nova versão</strong>. <a href="https://www.vmware.com/resources/compatibility/sim/interop_matrix.php" target="_blank" rel="noopener">Product Interoperability Matrix</a></li>
 	<li><strong>Valide</strong> as suas entradas no <strong>DNS</strong>! Aliás, <strong>a culpa é sempre do DNS</strong>.</li>
 	<li><strong>Faça um backup e/ou snapshot</strong> do seu vCenter antes de iniciar o processo.</li>
 	<li>Renomeie o seu vCenter, pois durante o processo de upgrade e criação da nova VM, o instalador irá solicitar um nome para a VM.</li>
 	<li><strong>Valide se você tem espaço suficiente no datastore</strong>. O vCenter 6.5 <strong>consome mais CPU, disco e memória</strong> do que o 6.0 (<a href="https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.upgrade.doc/GUID-88571D8A-46E1-464D-A349-4DC43DCAF320.html" target="_blank" rel="noopener">Hardware Requirements</a> | <a href="https://docs.vmware.com/en/VMware-vSphere/6.5/com.vmware.vsphere.upgrade.doc/GUID-FB268055-5D36-4624-A64C-9800D3FCB689.html" target="_blank" rel="noopener">Software Requirements</a>)</li>
 	<li>Tenha em mãos o <strong>usuário e senha (root) do ESXi</strong> onde está o seu vCenter atual.</li>
 	<li>Tenha em mãos o <strong>usuário e senha do vCenter atual</strong>. Se a senha estiver expirada, a instalação vai parar.</li>
 	<li>Certifique-se de que o host ao qual você fará o deploy da nova versão não está em <strong>Lockdown</strong> ou <strong>Maintenance</strong> <strong>Mode</strong></li>
 	<li>Você pode utilizar o software de update no <strong>Windows</strong>, <strong>Linux</strong> ou <strong>MacOS</strong> e o arquivo de instalação está no diretório <strong>\vcsa-ui-installer\&lt;so&gt;\installer</strong></li>
 	<li>Certifique-se de ter <strong>lido esse KB</strong> (2147548) <a href="https://kb.vmware.com/s/article/2147548" target="_blank" rel="noopener"><strong>Important information before upgrading to vSphere 6.5</strong></a></li>
</ul>
<blockquote>
<p style="text-align: center;"><strong>E lembre-se, o <span style="color: #ff0000;">vSphere Client</span> (Fat Client) <span style="color: #ff0000;">não é mais suportado</span> nesta versão. Então, é bom você se acostumar com o Web Client e o HTML5 Client</strong></p>
</blockquote>
<h2>Como atualizar VMware vCenter 6.0 para 6.5</h2>
A atualização do VCSA (<strong>V</strong>Mware v<strong>C</strong>enter <strong>S</strong>erver <strong>A</strong>ppliance) 6.5 é dividida em <strong>duas etapas</strong>.

A <strong>primeira etapa</strong> é a implantação de um novo vCenter Server Appliance e a <strong>segunda etapa</strong> é copia dados do vCenter 6.0 para o VCSA 6.5.

Interessante notar, que não é um upgrade de fato, pois uma nova VM é criada e os dados do vCenter atual são copiados para o novo e a VM antiga fica desligada, podendo ser apagada do ambiente após a validação da mudança.
<h2>Passo-a-Passo:</h2>
Fazer o download da última versão do VMware vCenter Server (versão <a href="https://my.vmware.com/web/vmware/details?productId=614&amp;downloadGroup=VC65U1E" target="_blank" rel="noopener">6.5.0U1</a>e na data de publicação desse post)
<ul style="list-style-type: square;">
 	<li>Montar o ISO no seu computador</li>
 	<li>Executar o instalador localizado na pasta  \vcsa-ui-installer\&lt;so&gt;\installer</li>
 	<li>Selecionar a opção <strong>Upgrade</strong> - Para atualizar um vCenter Server Appliance existente.</li>
</ul>
<img class="size-large wp-image-4398 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-14-00-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Clicar em Next para iniciar o primeiro estágio do Upgrade</li>
</ul>
<img class="size-large wp-image-4399 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-14-21-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Aceitar a EULA e clicar em Next</li>
</ul>
<img class="aligncenter size-large wp-image-4400" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-14-30-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Informar o endereço (FQDN) do servidor vCenter atual</li>
 	<li>Clicar em Connect to Source</li>
 	<li>Clicar em Next</li>
</ul>
Aqui se o instalador não conseguir encontrar o seu vCenter Server, pare a instalação e verifique o DNS, IP, conectividade, etc.

<img class="aligncenter size-large wp-image-4401" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-14-47-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Informe os dados de SSO - login de seu vCenter Server</li>
 	<li>Informe os dados do Host ESXi de seu vCenter atual</li>
 	<li>Clique em Next</li>
</ul>
<img class="aligncenter size-large wp-image-4402" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-16-39-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Se você informou os dados corretos, aqui pode aparecer uma tela de Certificate Warning, clique em YES e continue.</li>
 	<li>Informe os dados do Host ESXi onde o novo vCenter será instalado</li>
 	<li>Clique em Next</li>
</ul>
<img class="aligncenter size-large wp-image-4404" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-17-43-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Se você informou os dados corretos, aqui pode aparecer uma tela de Certificate Warning, clique em YES e continue.</li>
 	<li>Informe o nome da nova VM do vCenter - Se você renomeou a VM antiga, utilize o mesmo nome. No meu caso, eu dei um nome diferente.</li>
 	<li>Informe também a senha de root do vCenter. Anote essa senha!</li>
</ul>
<img class="aligncenter size-large wp-image-4407" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-18-46-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Escolha o tamanho da sua instalação de acordo com o seu ambiente</li>
</ul>
<img class="aligncenter size-large wp-image-4408" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-19-26-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Escolha o Datastore</li>
</ul>
<img class="aligncenter size-large wp-image-4409" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-19-41-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Informe rede ao qual o novo servidor vCenter irá se conectar</li>
 	<li>Informe o IP Temporário, Default Gateway e Servidor DNS</li>
</ul>
<img class="aligncenter size-large wp-image-4410" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-20-27-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Valide as informações e clique em Finish</li>
</ul>
<img class="aligncenter size-large wp-image-4411" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-20-35-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>O processo de instalação do estágio 1 irá iniciar. O processo pode demorar em torno de 20-30 minutos.</li>
</ul>
<img class="aligncenter size-large wp-image-4412" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_18-20-42-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Ao finalizar, clique em Continue</li>
</ul>
<img class="aligncenter size-large wp-image-4413" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-10-56-644x483.jpg" alt="" width="644" height="483" />

Até agora, o processo de upgrade criou uma nova VM com o VCSA no IP temporário. O próximo estágio será a cópia dos dados da VM antiga para a nova.
<ul style="list-style-type: square;">
 	<li>Clique em Next para iniciar o segundo estágio do processo</li>
</ul>
<img class="aligncenter size-large wp-image-4414" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-11-36-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Aguarde a validação</li>
</ul>
<img class="aligncenter size-large wp-image-4415" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-11-56-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Se você não desligou o DRS antes de começar o procedimento, deve fazer agora.</li>
</ul>
<img class="aligncenter size-large wp-image-4416" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-13-11-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Escolha quais dados serão migrados. No meu caso, eu escolhi migrar todos os dados.</li>
 	<li>Clique em Next</li>
</ul>
<img class="aligncenter size-large wp-image-4417" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-13-22-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Escolha se você quer participar do <a href="https://www.vmware.com/solutions/trustvmware/ceip.html" target="_blank" rel="noopener">Customer Experience Improvement Program</a></li>
 	<li>Clique em Next</li>
</ul>
<img class="aligncenter size-large wp-image-4418" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-13-29-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Confira as informações</li>
 	<li>Selecione a caixa dizendo que você fez o backup de todas as configurações do vCenter atual - certifique-se de ter feito mesmo.</li>
 	<li>Clique em Next.</li>
</ul>
<img class="aligncenter size-large wp-image-4419" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-13-39-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Confirme mais uma vez. Nesse ponto, o upgrade de fato irá começar. O vCenter atual será desligado.</li>
 	<li>Clique em Finish para iniciar o upgrade</li>
</ul>
<img class="aligncenter size-large wp-image-4420" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-14-12-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Aguarde a cópia dos dados do vCenter antigo para o novo</li>
</ul>
<img class="aligncenter size-large wp-image-4421" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-14-26-644x483.jpg" alt="" width="644" height="483" />

Eu deixei um ping para o IP do vCenter antigo, durante a troca dos appliances, pedi apenas 9 pacotes.

<img class="aligncenter size-large wp-image-4423" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-29-06-644x483.jpg" alt="" width="644" height="483" />
<ul style="list-style-type: square;">
 	<li>Ao final do processo, clique em Close</li>
 	<li>Acesse vCenter https://:443</li>
</ul>
<img class="aligncenter size-large wp-image-4425" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-35-56-644x483.jpg" alt="" width="644" height="483" />vCenter atualizado

<img class="aligncenter size-large wp-image-4429" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-40-09-644x340.jpg" alt="" width="644" height="340" />

Para acessar o HTML5 Client, utilize a URL <strong>https://&lt;ip-do-vcenter&gt;/ui</strong>

<img class="aligncenter size-large wp-image-4426" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Como-atualizar-VMware-vCenter-6.0-para-6.5_2018-01-22_19-38-59-644x340.jpg" alt="" width="644" height="340" />
<h2>Próximos passos:</h2>
Se você tiver algum plugin (Backup, AV, vRA, vROps, etc) , esse será o momento de fazer a atualização, portanto, não apague o seu backup ou a VM antiga até se certificar de que tudo está funcionando.

Cheque as configurações de login, AD, etc. Se for necessário fazer qualquer ajuste, você pode acessar o <strong>vSphere Appliance Manager</strong> na URL https://:<strong>5480</strong> com o usuário <strong>root</strong>
<p style="text-align: center;"><em>Não se esqueça, você <strong>não conseguirá</strong> mais <strong>acessar a console do vCenter utilizando o vSphere Client</strong>. Certifique-se de que todas as pessoas que precisam acessar o vCenter saibam disso.</em></p>

<h2>Considerações finais:</h2>
Eu achei o processo para fazer o upgrade do vCenter Server 6.0 para o 6.5 muito tranquilo, pelo menos no meu ambiente - LAB - não encontrei nenhum problema.

Gastei algumas horas <strong>lendo a documentação</strong>, <strong>fazendo pesquisas</strong> e <strong>planejando o upgrade</strong>, da mesma forma que faria se o upgrade fosse realizado em um ambiente produtivo - só não precisei abrir uma change :) -  e <strong>recomendo que você faça o mesmo</strong> para evitar surpresas.

Vou deixar aqui mais alguns KBs e links importantes que recomendo a leitura.

<a href="https://kb.vmware.com/s/article/2147686" target="_blank" rel="noopener">Best practices for upgrading to vCenter Server 6.5 (2147686)</a>

<a href="https://kb.vmware.com/s/article/2147289" target="_blank" rel="noopener">Update sequence for vSphere 6.5 and its compatible VMware products (2147289)</a>

<a href="https://blogs.vmware.com/vov/2018/01/22/tips-upgrading-vsphere-6-5-large-scale-environment/" target="_blank" rel="noopener">Tips for upgrading to vSphere 6.5 in a Large-Scale Environment</a>

<a href="https://docs.vmware.com/en/VMware-vSphere/6.5/rn/vsphere-client-65-html5-functionality-support.html" target="_blank" rel="noopener">Lista de funcionalidades suportadas e não suportadas</a> do Client HTML5 e WebClient

vSphere 6.5 Upgrade Considerations - <a href="https://blogs.vmware.com/vsphere/2017/05/vsphere-6-5-upgrade-considerations-part-1.html" target="_blank" rel="noopener">Parte 1</a>, <a href="https://blogs.vmware.com/vsphere/2017/07/vsphere-6-5-upgrade-considerations-part-2.html" target="_blank" rel="noopener">Parte 2</a> e <a href="https://blogs.vmware.com/vsphere/2017/08/vsphere-6-5-upgrade-considerations-part-3.html" target="_blank" rel="noopener">Parte 3</a> (Série de posts escritos pelo Emad Younis (@emad_younis)

<a href="https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/vsphere/vmware-vsphere-top-reasons-to-upgrade-infographic.pdf">Maiores razões para fazer o upgrade para o vSphere 6.5</a>

E para finalizar, um episódio do <a href="http://www.talkshoe.com/talkshoe/web/talkCast.jsp?masterId=19367" target="_blank" rel="noopener">podcast Community Roundtable</a> sobre porque você deve fazer o upgrade para o @VMwarevSphere 6.5

https://twitter.com/VMware/status/955563823926251520

É isso pessoal! Deixe nos comentários <strong>se você já fez, está pensando ou não vai fazer o upgrade para o vSphere 6.5 e porque!</strong>

Nos próximos posts, vou mostrar como fazer o upgrade dos hosts ESXi.

Até a próxima!

--VC