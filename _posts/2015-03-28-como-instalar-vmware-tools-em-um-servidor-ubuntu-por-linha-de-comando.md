---
ID: 214
post_title: >
  Como instalar VMware Tools em um
  servidor Ubuntu por linha de comando
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1I2lL6s
published: true
post_date: 2015-03-28 04:08:41
---
Olá HomeLabers!

Essa semana estava subindo uma nova VM no meu ambiente e aproveitei para documentar o passo a passo de como instalar o VMware Tools em um servidor Ubuntu por linha de comando.

<img class="aligncenter wp-image-258" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/instalaçao-vmware-tools-no-ubuntu-server-0.jpg" alt="instalaçao-vmware-tools-no-ubuntu-server-0" width="900" height="503" />

<!--more-->

Vamos lá:

Selecione a VM que onde você quer instalar o VMware Tools, clique com o botão direito e escolha a opção "Open Console"

<img class=" size-full wp-image-237 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/instalaçao-vmware-tools-no-ubuntu-server-1.jpg" alt="instalaçao-vmware-tools-no-ubuntu-server-1" width="370" height="118" />

&nbsp;

&nbsp;

&nbsp;

&nbsp;

Clique no men VM --&gt; Guest --&gt; Install/Upgrade VMware Tools

<img class=" size-full wp-image-236 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/instalaçao-vmware-tools-no-ubuntu-server-2.jpg" alt="instalaçao-vmware-tools-no-ubuntu-server-2" width="527" height="146" />

&nbsp;

&nbsp;

&nbsp;

&nbsp;

Acesse seu servidor com o Putty ou via Console

Faça o login no seu servidor

Entre no modo sudo (administração)

<pre class="font:monospace lang:sh decode:true"> sudo su</pre>

Atualize o sistema operacional

<pre class="lang:sh decode:true">apt-get update -y
apt-get upgrade -y
</pre>

Crie um diretório para montar o cd do vmtools

<pre class="lang:default decode:true ">mkdir -p /media/cdrom</pre>

Monte o ISO do VMware Tools

<pre class="lang:default decode:true ">mount /dev/cdrom /media/cdrom</pre>

Você deve ver a mensagem: <em>mount: block device /dev/sr0 is write-protected, mounting read-only</em>

Copie o arquivo .tar do vmtools para o diretório temporario (/tmp)

<pre class="lang:default decode:true ">cp -v /media/cdrom/VM*.tar.gz /tmp/</pre>

Descompacte o arquivo tar

<pre class="lang:default decode:true ">tar xzvf /tmp/VM*.tar.gz</pre>

Crie o diretorio /lib64 para evitar um possível erro do Ubuntu

<pre class="lang:default decode:true ">mkdir -p /usr/lib64</pre>

Execute o script de instalação. A opção -d automaticamente responde sim para todas as perguntas e faz a instalação padrão.

<pre class="lang:default decode:true ">./vmware-tools-distrib/vmware-install.pl -d</pre>

Remova os arquivos temporários da instalação

<pre class="lang:default decode:true ">rm -r -f -v vmware-tools-distrib/</pre>

Reinicie o servidor

<pre class="lang:default decode:true ">reboot</pre>

Valide a instalação checando no cliente do vsphere o status do VMware Tools

<img class=" size-full wp-image-235 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/instalaçao-vmware-tools-no-ubuntu-server-3.jpg" alt="instalaçao-vmware-tools-no-ubuntu-server-3" width="293" height="48" />

&nbsp;

&nbsp;

Se funcionou para você, deixe o seu recado nos comentários.

É isso Homelabers! Fico por aqui e espero que vocês tenham gostado. Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado com as novidades do blog.