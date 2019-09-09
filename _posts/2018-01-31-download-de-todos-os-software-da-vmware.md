---
ID: 4457
post_title: >
  Free Download de todos os software da
  VMware
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2rVpHsD
published: true
post_date: 2018-01-31 09:00:50
---
Olá Homelabers!

Você já precisou fazer o download de um software da VMware para o seu lab não tinha acesso ao software em questão?

Acredito que muitos de nós já passamos por essa situação, seja porque o seu trial já expirou ou porque você saiu da empresa e o seu perfil no my.vmware.com não tem acesso a mais nada.

Há muito tempo atrás, fiz um post sobre o <strong><a href="http://homelaber.com.br/vmware-software-manager/" target="_blank" rel="noopener">VMware Software Manager</a></strong>, que é um software disponibilizado pela VMware onde você pode navegar e baixar praticamente toda a biblioteca de softwares de uma maneira bem fácil. Mas o VSM tem alguns problemas:
<ul style="list-style-type: square;">
 	<li>Somente roda em ambiente Windows</li>
 	<li>Nem sempre (ou quase nunca) funciona</li>
 	<li>Foi descontinuado pela VMware</li>
</ul>
<h2>A resposta da comunidade: LinuxVSM</h2>
O <a href="https://www.astroarch.com/blog/" target="_blank" rel="noopener">Edward Haletky</a> aka @Texiwill criou um port do VSM para Linux que funciona perfeitamente bem e é super fácil de usar. Estou rodando o LinuxVSM há mais ou menos 2 semanas e estou muito feliz com o resultado.

Com o LinuxVSM você terá um <strong>repositório de softwares VMware sempre atualizado</strong>, dentro de sua empresa ou no seu lab, com a vantagem de não precisar de esperar horas para baixar aquela nova versão.

O port pode ser encontrado no Github do Texiwill (<a href="http://bit.ly/2GyLp94" target="_blank" rel="noopener">link</a>) e a sua instalação é bem fácil.
<h2>Instalação</h2>
Para rodar o LinuxVSM você vai precisar de uma VM com Linux RedHat (RHEL) ou CentOS - não funciona no Ubuntu - e configurações mínimas. A minha VM tem 1vCPU e 2GB RAM e está rodando lisa. Você também vai precisar de uma conta no <a href="https://my.vmware.com" target="_blank" rel="noopener">my.vmware.com</a>

<img class="aligncenter size-large wp-image-4458" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/linuxvsm-1-644x366.jpg" alt="" width="644" height="366" />
<ul style="list-style-type: square;">
 	<li>Crie um diretório chamado vsmlinux (ou qualquer outro nome de sua preferência)</li>
</ul>
<pre class="">mkdir vsmlinux</pre>
<ul style="list-style-type: square;">
 	<li>Acesse o diretório e execute o comando abaixo para baixar o instalador</li>
</ul>
<pre class="">cd vsmlinux/

wget https://raw.githubusercontent.com/Texiwill/aac-lib/master/vsm/install.sh</pre>
<ul style="list-style-type: square;">
 	<li>Conceda as permissões para executar o arquivo e execute o instalador:</li>
</ul>
<pre class="">chmod a+x install.sh &amp;&amp; ./install.sh</pre>
Ao final do processo o executável do LinuxVSM está localizado na pasta <strong>/usr/local/bin/vsm.sh</strong>
<h2>Executando o LinuxVSM</h2>
<h4>Mostrar o help</h4>
<pre class="">/usr/local/bin/vsm.sh --help</pre>
<h4>Executar sem nenhum parâmetro mostra as opções de download</h4>
<pre class="">/usr/local/bin/vsm.sh</pre>
<h4>Informar o usuário, password do<a href="https://my.vmware.com/" target="_blank" rel="noopener"> my.vmware.com</a> e local para salvar os downloads</h4>
<pre class="">/usr/local/bin/vsm.sh -m -u &lt;usuário_my_vmware&gt; -p &lt;password&gt; --repo &lt;diretorio_para_download&gt;</pre>
Use esse comando para executar regularmente o download, buscando sempre as últimas atualizações.
<pre class="">/usr/local/bin/vsm.sh -m -mr -y</pre>
Toda a navegação é feita via menu, como mostrado na imagem abaixo

<img class="aligncenter size-large wp-image-4459" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/linuxvsm-2-644x448.jpg" alt="" width="644" height="448" />

Outros comandos úteis:

Para atualizar o sistema automaticamente e diretamente do repositório Github
<pre class="">./aac-base.install -u</pre>
Então é isso pessoal, por hoje ficamos por aqui. Deixe ai nos comentários se você já usava o VMware Software Manager antes e se pretende utilizar o LinuxVSM. Peço também que deixe um alô para o Edward no twitter (<a href="https://twitter.com/texiwill" target="_blank" rel="noopener">@Texiwill</a>) agradecendo por disponibilizar seu magnífico trabalho - de graça - para a comunidade.

Se você for um VMware vExpert, existe uma "chave secreta" que libera mais alguns downloads. Entre em contato comigo ou com o @Texiwill para descobrir o easter egg :)

Conheça o site do Edware visitando o link <a href="https://www.astroarch.com/2018/01/vsphere-upgrade-saga-linux-vmware-software-manager-vsm/" target="_blank" rel="noopener">https://www.astroarch.com/2018/01/vsphere-upgrade-saga-linux-vmware-software-manager-vsm/</a>

Até a próxima!

VC