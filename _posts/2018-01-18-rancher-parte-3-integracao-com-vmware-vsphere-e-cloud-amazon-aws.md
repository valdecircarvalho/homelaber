---
ID: 4312
post_title: 'Rancher Parte 3 &#8211; Integração com VMware vSphere e Cloud Amazon AWS'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2FR0Wkt
published: true
post_date: 2018-01-18 13:56:21
---
Olá Homelabers!

Essa é terceira e última parte da série sobre <a href="http://rancher.com/" target="_blank" rel="noopener">Rancher</a> (@Rancher_Labs).

No <a href="http://homelaber.com.br/rancher-parte-1-instalacao-e-configuracao/" target="_blank" rel="noopener">primeiro post</a>, mostrei como fazer a <strong>instalação e a configuração básica</strong> do Rancher.

https://twitter.com/homelaber/status/948835714954915857

No <a href="http://homelaber.com.br/rancher-parte-2-instalacao-e-configuracao/" target="_blank" rel="noopener">segundo post</a>, mostrei como <strong>preparar e adicionar um host</strong> ao Rancher.

https://twitter.com/homelaber/status/950467311592509440

Hoje, vou mostrar como fazer a <strong>integração do Rancher</strong> com o V<strong>Mware vSphere</strong> e com a Cloud <strong>Amazon AWS</strong>.
<ul style="list-style-type: square;">
 	<li>Provisionar hosts no VMware vSphere</li>
 	<li>Provisionar hosts na Cloud Amazon AWS</li>
</ul>
<h2>Provisionar hosts no VMware vSphere</h2>
Para que o Rancher possa provisionar hosts no ambiente VMware vSphere, primeiramente é necessário adicionar o <a href="https://docs.docker.com/machine/concepts/" target="_blank" rel="noopener">Machine Drive</a> específico para <a href="https://docs.docker.com/machine/drivers/vsphere/" target="_blank" rel="noopener">vSphere</a> e para ativar o Machine Driver é muito simples.

Menu INFRASTRUCTURE &gt;&gt; Hosts &gt;&gt; Add Host &gt;&gt; Manage Available machine drivers &gt;&gt; Add Machine Driver e escolher vSphere.

<img class="size-large wp-image-4326 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Instalando-Rancher-Host-VMware-vSphere-1-644x484.jpg" alt="" width="644" height="484" />

Feito isso, o próximo passo é preencher os campos com as informações do seu servidor vSphere.
<ul style="list-style-type: square;">
 	<li>Nome do Host</li>
 	<li>Quantidade de Hosts</li>
 	<li>Endereço do vCenter ou ESXi (aqui prefira utilizar hostname)</li>
 	<li>Username e Password do vCenter - um usuário que tenha permissão de criar VMs</li>
 	<li>Número de vCPUs, Memória e Disco do host</li>
 	<li>URL do ISO do <a href="https://github.com/boot2docker" target="_blank" rel="noopener">boot2docker</a> - https://github.com/boot2docker/boot2docker/releases/download/v17.03.2-ce/boot2docker.iso (importante utilizar a mesma versão do Docker utilizada no Rancher)</li>
 	<li>Datacenter, Pool, Host, Network e Data Store onde o Host será criado. Se você tem o vCenter no seu ambiente, não preencha nada no campo Host. Importante preencher os valores exatamente como estão no vCenter.</li>
</ul>
Após isso, basta clicar no botão Creat e aguardar o provisionamento dos host no vSphere.

Você pode acompanhar o andamento e caso seja necessário fazer algum troubleshooting através dos logs do Rancher Server.
<pre class="">$ docker ps -a</pre>
<pre class="">$ docker container logs -f &lt;Container ID&gt;</pre>
Após alguns minutos os Hosts estarão provisionados e ativos no Rancher

<img class="size-large wp-image-4327 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Instalando-Rancher-Host-VMware-vSphere-2-644x211.jpg" alt="" width="644" height="211" />

Você pode também, acompanhar a criação das VMs pelo console do vCenter.
<h2>Provisionar hosts na Cloud Amazon AWS</h2>
O processo para provisionar hosts Rancher na AWS é bem parecido com o processo para vSphere.

Caso o Machine Driver da AWS não esteja ativo, basta ativá-lo da mesma maneira a qual fizemos com o vSphere.

Menu INFRASTRUCTURE &gt;&gt; Hosts &gt;&gt; Add Host &gt;&gt; Escolher AWS

<em><strong>Importante ressaltar que você precisa ter uma conta ativa na AWS. Não é o foco desse post a criação da conta e a operação da AWS.</strong></em>

Feito isso, o próximo passo é preencher os campos com as informações da AWS:
<ul style="list-style-type: square;">
 	<li>Escolher a região - São Paulo é a sa-east-1</li>
 	<li>Preencher o seu Access Key e Secret Key</li>
 	<li>Escolher o Availability Zone e a VCP/Subnet</li>
 	<li>Escolher o Security Group</li>
 	<li>Definir as caracteristicas do host - Nome, Quantidade, Tipo de Instância, etc.</li>
</ul>
Após preencher os campos necessários, basta clicar em Create e o Rancher começará a fazer o seu trabalho de provisionar as instâncias na AWS.

Você poderá acompanhar a criação pela UI do Rancher, pelos logs e também pela console da AWS.

Aqui um ponto MUITO importante. <strong>Os hosts criados na AWS precisam se comunicar com o Rancher Server</strong>, se isso não for possível, você receberá um erro "Failed to find rancher-agent container".

<img class="alignright size-large wp-image-4329" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Instalando-Rancher-Host-VMware-vSphere-3-644x384.jpg" alt="" width="644" height="384" />

Eu uso Vivo Fibra, tentei de várias maneiras configurar um Port Forwarding mas não funcionou - aliás, se você tem Vivo Fibra e conseguiu fazer essa configuração, me ajuda ai vai!!! :)

<span style="color: #ff0000;"><strong>Update:</strong></span> Passei mais algumas HORAS tentando fazer esse negócio funcionar e deu certo. A Vivo bloqueia a porta 8080, então eu subi o Rancher Server em uma porta diferente (9999) no caso e criei um redirecionamento de portas no meu modem. Dessa maneira, consegui fazer o provisionamento na AWS sem erros.

Comando para subir o Rancher com uma porta diferente:
<pre class="">docker run -d --restart=unless-stopped -p <strong><span style="color: #ff0000;">9999</span></strong>:8080 rancher/server:stable</pre>
Portanto, se você quiser reproduzir isso, antes de mais nada, precisa configurar o port forwarding (redirecionamento de portas) no seu modem/router (https://portforward.com/) e subir o Rancher na porta configurada.

<img class="size-full wp-image-4334 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/homer-uhuull-deu-certo.png" alt="" width="340" height="311" />

Se você subir o Rancher Server em algum provedor de Cloud, como a AWS ou configurar a sua rede para receber conexões de fora (via Firewall, VPN ou um link Direct Connect com a AWS) você não irá enfrentar esse problema.
<h2>Fechamento e Próximos Passos</h2>
Bom, pessoal, então é isso! Encerro aqui essa série de posts sobre como montar um Lab de Rancher e espero que vocês tenham gostado e aprendido tanto como eu aprendi.

Deixo algumas dicas para quem quiser seguir adiante com os estudos sobre Rancher:
<ul style="list-style-type: square;">
 	<li>Seguir o @Rancher_Labs no twitter</li>
 	<li>Ler a <a href="http://rancher.com/docs/rancher/latest/en/" target="_blank" rel="noopener">documentação do Rancher</a></li>
 	<li>Acompanhar o <a href="http://rancher.com/blog/" target="_blank" rel="noopener">blog</a> para saber das novidades - a <a href="https://rancher.com/rancher2-0/" target="_blank" rel="noopener">versão 2.0 está em Tech Preview</a></li>
 	<li>Passear pelo <a href="http://rancher.com/learn/" target="_blank" rel="noopener">Learning Resources</a>, onde você irá encontrar diversos artigos e vídeos com casos de uso.</li>
 	<li>Entrar e acompanhar o Slack do Rancher - https://rancher-users.slack.com</li>
 	<li>E por fim, testar, praticar e pensar em casos de uso para você e/ou para sua empresa. Monte um lab, comece com algumas aplicações pouco críticas, investigue e estude outros produtos e defina qual é o melhor para você.</li>
</ul>
<h2>Vídeo:</h2>
Você poderá acompanhar o passo-a-passo mais detalhado desse post no vídeo abaixo.

https://youtu.be/HvSBSx1FzLI

Deixe o seu comentário o que você achou da série. Se você conseguiu montar o seu lab, quais foram as suas dificuldades, o que eu poderia ter feito de melhor e diferente.

Até a próxima!

VC