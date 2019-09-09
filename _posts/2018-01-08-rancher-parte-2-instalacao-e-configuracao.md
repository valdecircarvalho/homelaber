---
ID: 4211
post_title: >
  Rancher Parte 2 – Instalação e
  configuração
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2Fix8gr
published: true
post_date: 2018-01-08 17:40:23
---
Olá Homelabers!

Essa é segunda parte da série sobre Rancher.

Se você perdeu a primeira parte, não tem problema! Acesse o<a href="http://homelaber.com.br/rancher-parte-1-instalacao-e-configuracao/"> link e veja o post e o vídeo com todos os detalhes</a> sobre como fazer a preparação de um servidor Ubuntu, instalando o Docker para receber o Rancher Server, instalar o Rancher Server e configurar a autenticação local.

https://twitter.com/homelaber/status/948835714954915857

Hoje vou mostrar a vocês como:
<ul>
 	<li>Configurar o Rancher Server</li>
 	<li>Configurar e adicionar um host local no Rancher</li>
 	<li>Fazer o deploy de containers</li>
</ul>
<h2>Configurando Environments (Ambientes) no Rancher</h2>
<b>O que </b><b>é</b><b> um </b><b>ambiente</b><b>?</b>

O Rancher suporta agrupamento de recursos em vários ambientes. Cada um com seu próprio conjunto de serviços e recursos de infraestrutura  gerenciado por um ou mais usuários ou equipes.

Por exemplo, você pode criar ambientes separados de "dev", "teste" e "produção" para manter as coisas isoladas e dar acesso ao ambiente de "dev" a todos os desenvolvedores, mas restringir o ambiente de "produção” a apenas ao time de produção.

<strong>Para configurar um novo ambiente:</strong>

Acesse o servidor do Rancher em http://&lt;ip-rancher-server&gt;:8080

Clique em <strong>Default</strong> &gt;&gt; <strong>Manage Environments</strong> &gt;&gt; <strong>Add Environment</strong>

Preencha os campos e clique em <strong>Create</strong>

<img class="aligncenter size-full wp-image-4212" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-1.jpg" alt="" width="650" height="159" /> <img class="aligncenter size-full wp-image-4213" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-2.jpg" alt="" width="650" height="152" /> <img class="aligncenter size-full wp-image-4214" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-3.jpg" alt="" width="650" height="287" />
<h2>Adicionando Hosts no Rancher</h2>
O próximo passo da nossa configuração é adicionar um host "local" ao Rancher Server.

<strong>O que é um host?</strong>
Antes de adicionar seu primeiro serviço ou iniciar um contêiner, você deve <strong>adicionar pelo menos um único host Linux que suporte o Docker e seja capaz de se comunicar com o servidor Rancher via HTTP</strong>. O Rancher suporta a adição de hosts Linux na forma de uma máquina virtual ou física de qualquer fornecedor de nuvem pública, nuvens local ou mesmo em servidores bare metal (físicos).

Em nosso lab, vamos utilizar um servidor Linux Ubuntu Server 16.04. Nesse post não vou mostrar como instalar o Ubuntu, mas <a href="http://homelaber.com.br/como-instalar-e-configurar-o-linux-ubuntu-server/">deixo aqui um link</a> com o passo-a-passo da instalação caso você tenha alguma dúvida.

<strong>Instalando o Docker</strong>

Antes de adicionar o host ao Rancher, vamos fazer a instalação do Docker utilizando um script de instalação fornecido pelo time da Rancher Labs para instalar o Docker na sua versão correta. Todos os comandos abaixo devem ser executados em seu Rancher Host.
<pre class="">$ sudo curl https://releases.rancher.com/install-docker/17.03.sh | sh</pre>
Esse comando faz o download de um script e inicia a instalação do Docker versão 17.03.

<img class="aligncenter size-full wp-image-4218" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-5.jpg" alt="" width="650" height="187" />

Ao final da instalação, você verá a seguinte tela, que mostra que o Docker versão 17.03.2-ce foi instalado e pergunta se você que executar o comando para evitar que você precise digitar “sudo” sempre que for rodando algum comando Docker. Em nosso lab, eu recomendo habilitar essa “funcionalidade” por questões práticas. Mas em seu ambiente de Produção, leia e pesquise sobre os riscos.

<img class="aligncenter size-full wp-image-4219" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-6.jpg" alt="" width="650" height="362" />
<pre class="">$ sudo usermod -aG docker $USER</pre>
<img class="aligncenter size-full wp-image-4220" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-7.jpg" alt="" width="650" height="363" />
<pre class="">$ docker run hello-world
</pre>
Esse comando irá criar um container para que você valide sua instalação. O resultado do comando é o apresentado abaixo:

O próximo passo, é configurar o Docker para inicializar junto com o SO, assim, se a sua VM reiniciar, o Docker será inicializado automaticamente.
<pre class="">$ sudo systemctl enable docker</pre>
<strong>Para adicionar um host local: </strong>

Com o seu host já preparado - Docker instalado e configurado, na tela principal do Rancher Server:

Clique em <strong>Infrastructure</strong> &gt;&gt; <strong>Hosts</strong> &gt;&gt; <strong>Add Host</strong>

<img class="aligncenter size-full wp-image-4217" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-4.jpg" alt="" width="650" height="195" />

Selecione a opção <strong>Custom</strong> &gt;&gt; <strong>Preencha o IP do servidor host</strong> (192.168.1.41 no exemplo) &gt;&gt; <strong>copie o comando gerado</strong> &gt;&gt; <strong>Close</strong>

<img class="aligncenter size-full wp-image-4222" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-8.jpg" alt="" width="650" height="295" />

O próximo passo, é executar o comando gerado pelo Rancher em seu host:
<pre class="">sudo docker run -e CATTLE_AGENT_IP="<strong>192.168.1.41</strong>" --rm --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/rancher:/var/lib/rancher rancher/agent:v1.2.7 http://192.168.1.40:8080/v1/scripts/A8D092E0859FCEEE7D37:1514678400000:bqWHhDgZAxcmaBtZAA7BYECCUsE</pre>
O que esse comando faz é criar um container do Rancher Agent em seu host e apontar para o servidor Rancher.

<img class="aligncenter size-full wp-image-4223" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-9.jpg" alt="" width="650" height="302" />

Após alguns minutos, o seu host já deve aparecer no painel do Rancher

<img class="aligncenter size-full wp-image-4224" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-10.jpg" alt="" width="650" height="230" />
<h2>Criando o primeiro container no Rancher</h2>
Agora que nós já adicionamos o host ao nosso server Rancher, vamos criar um container.

O primeiro passo é clicar em <strong>INFRASTRUCURE</strong> &gt;&gt; <strong>Containers</strong> &gt;&gt; <strong>Add Container</strong> e preencher os campos:
<ul style="list-style-type: square;">
 	<li><strong>Name</strong>: Nome do container</li>
 	<li><strong>Description</strong>: Descrição do container</li>
 	<li><strong>Select Image</strong>: Imagem Docker que você quer utilizar.</li>
 	<li><strong>Public Host Port</strong>: Porta pública da sua aplicação</li>
 	<li><strong>Private Container Port</strong>: Porta privada da sua aplicação/container.</li>
</ul>
<img class="aligncenter size-full wp-image-4226" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-11.jpg" alt="" width="650" height="115" /> <img class="aligncenter size-full wp-image-4227" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-12.jpg" alt="" width="650" height="331" />

Após isso, clique em <strong>Create</strong> e em alguns segundos o seu container estará criado e rodando.

<img class="aligncenter size-full wp-image-4232" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/instalacao-rancher-2-13.jpg" alt="" width="650" height="208" />
<blockquote>Uma dica é utilizar o Docker Hub, onde estão disponíveis mais de 100 imagens oficiais <a href="https://hub.docker.com/explore/" target="_blank" rel="noopener">https://hub.docker.com/explore/</a></blockquote>
<h2>Próximos passos</h2>
Nesse post, falamos sobre a configuração de Environments no Rancher, o setup e preparação de um servidor Ubuntu para se tornar um host Rancher, como adicionar o host ao Rancher e como fazer o deploy de um container simples.

No próximo e último post da série, irei abordar os seguintes assuntos:
<ul style="list-style-type: square;">
 	<li>Provisionar hosts no VMware vSphere.</li>
 	<li>Provisionar hosts na cloud Amazon AWS.</li>
</ul>
Bom pessoal, por hoje é isso! No vídeo demonstro mais algumas coisas como o catálogo de aplicações do Rancher e outras dicas. Não deixe de assistir.

[embed]https://youtu.be/Bh7XS51VmTw[/embed]

Deixe ai nos comentários o que você está achando da série! Se você já está colocando em prática o que aprendeu aqui!

Um abraço e até o próximo post!