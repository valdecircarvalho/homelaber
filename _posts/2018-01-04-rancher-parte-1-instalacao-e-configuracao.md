---
ID: 4189
post_title: 'Rancher Parte 1 &#8211; Instalação e configuração'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2E3vD46
published: true
post_date: 2018-01-04 05:36:53
---
Olá Homelabers!

Você conhece o <strong>Rancher</strong>?

Se você que é de infra estrutura e está querendo começar a estudar sobre containers, docker, devops, etc, uma hora ou outra vai precisar de um gerenciador de container e o<a href="http://rancher.com/" target="_blank" rel="noopener"> Rancher</a> é um dos melhores da atualidade.

Para quem não está familiarizado com o assunto, o Rancher é um projeto bem legal que entrega uma plataforma de gerenciamento de containers, através de uma UI (User Interface) fácil de ser compreendida e utilizada.

Nessa série de 3 posts (e vídeos), vou mostrar como criar um <strong>lab de Rancher</strong> para que você possa entender o seu funcionamento e ter um ponto de partida para seus estudos.

Para acessar os 3 posts da série sobre Rancher <a href="http://bitly.com/rancher-lab" target="_blank" rel="noopener">clique aqui</a>
<ul style="list-style-type: square;">
 	<li><a href="http://homelaber.com.br/rancher-parte-1-instalacao-e-configuracao/" target="_blank" rel="noopener">Rancher Parte 1 – Instalação e configuração (este post)</a></li>
 	<li><a href="http://homelaber.com.br/rancher-parte-2-instalacao-e-configuracao/" target="_blank" rel="noopener">Rancher Parte 2 – Instalação e configuração</a></li>
 	<li><a href="http://homelaber.com.br/rancher-parte-3-integracao-com-vmware-vsphere-e-cloud-amazon-aws/" target="_blank" rel="noopener">Rancher Parte 3 – Integração com VMware vSphere e Cloud Amazon AWS</a></li>
</ul>
<h2><strong>O que é o Rancher?</strong></h2>
<blockquote><b>Entenda</b><b> o Rancher </b><b>como</b><b> um </b><b>painel</b><b> de </b><b>controle</b><b> e </b><b>gerenciamento</b><b> para </b><b>sua </b><b>infraestrutura</b><b> de containers. </b></blockquote>
Imagine que você quer começar a utilizar containers na sua empresa. Tudo começa pequeno - um host, alguns containers na sua máquina, etc. Mas com o tempo (bem rápido) esse ambiente vai crescendo. Você vai precisar de uma ferramenta para gerenciar esses containers. É ai que entra o Rancher.

Para quem é do mundo VMware, uma boa analogia é dizer que o Rancher é <b>o vCenter do Docker!</b>
<h2><strong>A arquitetura do Lab</strong></h2>
<img class="aligncenter size-full wp-image-4190" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/Slide09-e1515049322507.jpg" alt="" width="600" height="338" />

Nosso lab será composto de:
<ul style="list-style-type: square;">
 	<li>Rancher Mngr - 1vCPU - 2GB RAM - 20GB Disco - Ubuntu Server 16.04</li>
 	<li>Rancher Host-1 - 1vCPU - 2GB RAM - 60GB Disco - Ubuntu Server 16.04</li>
</ul>
Teremos ainda mais dois hosts que serão provisionados diretamente do Rancher em um ambiente VMware vSphere e mais dois hosts provisionados na AWS.

Vale lembrar que estou criando esse lab, em um ambiente VMware vSphere, mas você pode utilizar o VMware Workstation, VMware Fusion, Virtualbox ou o hypervisor de sua preferência.
<h2>Instalando o Servidor Ubuntu Server 16.04</h2>
Esse será o nosso <strong>Rancher Server</strong>. Não vou detalhar aqui nesse post a instalação do Ubuntu. Se você tiver dúvidas, acesse <a href="http://homelaber.com.br/como-instalar-e-configurar-o-linux-ubuntu-server/" target="_blank" rel="noopener">esse post</a> e veja como fazer a instalação,
<h2>Instalando o Docker</h2>
Nesse lab vou utilizar um script de instalação fornecido pelo time da Rancher Labs para instalar o Docker na sua versão correta. Todos os comandos abaixo devem ser executados no Rancher Server.
<pre class="crayon-selected">$ sudo curl https://releases.rancher.com/install-docker/17.03.sh | sh</pre>
<img class="aligncenter size-full wp-image-4191" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-1.jpg" alt="" width="650" height="141" />

Esse comando faz o download de um script e inicia a instalação do Docker versão 17.03.

Ao final da instalação, você verá a seguinte tela, que mostra que o Docker versão 17.03.2-ce foi instalado e pergunta se você que executar o comando para evitar que você precise digitar "sudo" sempre que for rodando algum comando Docker. Em nosso lab, eu recomendo habilitar essa "funcionalidade" por questões práticas. Mas em seu ambiente de Produção, leia e pesquise sobre os riscos.

<img class="aligncenter size-full wp-image-4192" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2.jpg" alt="" width="650" height="296" />
<pre class="">$ sudo usermod -aG docker $USER</pre>
onde $USER é o nome do seu usuário - apenas copie e cole essa linha no seu terminal. Será necessário fazer um logout para fazer efeito ok?
<pre class="">$ docker run hello-world</pre>
Esse comando irá criar um container para que você valide sua instalação. O resultado do comando é o apresentado abaixo:

<img class="aligncenter size-full wp-image-4193" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-3.jpg" alt="" width="600" height="414" />

O próximo passo, é configurar o Docker para inicializar junto com o SO, assim, se a sua VM reiniciar, o Docker será inicializado automaticamente.
<pre class="">$ sudo systemctl enable docker</pre>
<h2>Instalando o Rancher</h2>
Com isso feito, agora iremos fazer a "instalação" do Rancher Server. Uma das inúmeras vantagens do Rancher é que ele roda dentro de um container Docker, então para fazer sua instalação, basta executar o comando:
<pre class="">$ docker run -d --restart=unless-stopped -p 8080:8080 rancher/server:stable</pre>
Após alguns minutos, o Rancher estará pronto para uso.

<img class="aligncenter size-full wp-image-4196" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-4.jpg" alt="" width="650" height="277" />
<h2>Acessando o Rancher Server</h2>
Para acessar o Rancher, abre um browser e acesse o endereço

<strong>http://&lt;IP_DO_SERVIDOR&gt;:8080</strong>

<img class="aligncenter size-full wp-image-4197" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-5.jpg" alt="" width="600" height="203" />
<h2>Configurando autenticação local no Rancher Server</h2>
A primeira configuração que você deve fazer em seu Rancher Server é configurar a forma de autenticação de acesso. O Rancher suporta diversos tipos de autenticação - Microsoft Active Directory, Azure AD, GitHub, OpenLDAP, local, etc. Em nosso lab, iremos utilizar a <strong>autenticação local.</strong>

Clique no menú <strong>Admin</strong> &gt;&gt; <strong>Access Control</strong>

<img class="aligncenter size-full wp-image-4198" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-6.jpg" alt="" width="650" height="182" />

Selecione a opção <strong>LOCAL</strong>, preencha os campos e clique no botão Enable Local Auto.

<img class="aligncenter size-full wp-image-4199" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-7.jpg" alt="" width="650" height="404" />

<img class="aligncenter size-full wp-image-4200" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-8.jpg" alt="" width="650" height="172" />

Feche o browser e abra novamente. Agora, o Rancher irá solicitar um usuário e senha para acessar o seu painel de controle.

<img class="aligncenter size-full wp-image-4201" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-9.jpg" alt="" width="282" height="373" />
<h2>Próximos passos</h2>
Nesse post, você aprendeu como fazer a preparação de um servidor Ubuntu, instalando o Docker para receber o Rancher Server, instalar o Rancher Server e configurar a autenticação local. <a href="http://homelaber.com.br/rancher-parte-2-instalacao-e-configuracao" target="_blank" rel="noopener">No próximo post</a>, irei abordar os seguintes passos:
<ul style="list-style-type: square;">
 	<li>Configurar o Rancher Server</li>
 	<li>Configurar e adicionar um host local no Rancher</li>
 	<li>Fazer o deploy de containers</li>
</ul>
É isso pessoal! Deixe nos comentários o que você achou do post, do assunto, do vídeo, etc. Não esqueça de compartilhar esse post com seus amigos nas sua redes sociais!
<h2>Bonus</h2>
Vídeo com o passo a passo da parte 1 dessa série.

[embed]https://www.youtube.com/watch?v=G2NWngEdLNU[/embed]