---
ID: 921
post_title: 'Postfix Mail Relay &#8211; Instalação servidor de e-mail Postfix no Linux Ubuntu e configuração para enviar e-mails via Gmail'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1RVnGyM
published: true
post_date: 2015-11-13 11:00:27
---
Olá Homelabers!

Nesse post vou mostrar a vocês como instalar e configurar o servidor de e-mail Postfix no Linux Ubuntu e como usar a sua conta do Gmail para enviar e-mails a partir desse servidor. Iremos criar um chamado Mail Relay, ou seja, esse servidor será o responsável por enviar e-mails de todas as suas aplicações ao mundo externo atraves do Gmail.

[caption id="attachment_922" align="aligncenter" width="580"]<img class="wp-image-922" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/postfix-logo.jpg" alt="postfix-logo" width="580" height="300" /> Logo PostFix - http://www.postfix.org/[/caption]

Esse tipo de configuração é muito utilizada nas empresas, imagine o cenário:

<blockquote>Você tem um servidor de monitoração de rede instalado, como por exemplo o Zabbix. Sempre que um evento acontecer - um link de internet cair, o disco do servidor debanco de dados está quase cheio, etc - você vai querer ser notificado via e-mail para que alguma ação seja tomada. Para que o servidor de monitoração consiga mandar e-mails existem duas opções:

1. O servidor de monitoração TAMBÉM será um servidor de e-mail (o que não é algo muito legal) ou

2. o servidor de monitoração precisa conhecer e falar com um servidor de e-mail. Então é ai que entra no nosso servidor de Mail Relay.</blockquote>

Veja abaixo uma figura explicando o conceito<!--more-->

&nbsp;

<img class="aligncenter wp-image-923" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/exemplo-mail-relay.png" alt="exemplo-mail-relay" width="900" height="665" />

&nbsp;

Então vamos lá!

[su_note radius="0"]Eu fiz essa instalação em uma VM com as seguintes configurações:
1 vCPU
20GB disco
1 GB memória
<a href="http://homelaber.com.br/como-instalar-e-configurar-o-linux-ubuntu-server/" target="_blank">Linux Ubuntu Server </a> (clique no link para ver o post da instalação do Ubunto no VMware)
[/su_note]

Sempre lembrando, os comandos abaixo devem ser executados como sudo

A primeira coisa que faremos é instalar o Postfix e os módulos necessários.

<pre class="lang:default decode:true">apt-get install postfix mailutils libsasl2-2 ca-certificates libsasl2-modules</pre>

<img class="aligncenter size-full wp-image-925" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-002.png" alt="homelaber-mailrelay-postfix-gmail-002" width="1037" height="354" />

Na tela de configuração do Postfix selecione as opções padrão

<img class="aligncenter size-full wp-image-936" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-013.png" alt="homelaber-mailrelay-postfix-gmail-013" width="1163" height="425" />

Escolha a opção Internet Site

<img class="aligncenter size-full wp-image-924" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-001.png" alt="homelaber-mailrelay-postfix-gmail-001" width="1083" height="553" />

Escolha um nome para o sistema. Eu costumo usar o mesmo nome da maquina para facilitar.

<img class="aligncenter size-full wp-image-935" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-012.png" alt="homelaber-mailrelay-postfix-gmail-012" width="1163" height="425" />

O próximo passo é criar um backup do arquivo de configuração inicial do Postfix  /etc/postfix/main.cf

<pre class="lang:default decode:true ">mv /etc/postfix/main.cf /etc/postfix/main.cf.original</pre>

Feito isso, vamos criar um novo arquivo em branco, apenas com as configurações necessárias.

<pre class="lang:default decode:true">nano /etc/postfix/main.cf</pre>

Copie e cole o texto abaixo dentro do arquivo <strong>main.cf</strong>

<pre class="lang:default decode:true" style="padding-left: 30px;">relayhost = [smtp.gmail.com]:587
smtp_sasl_auth_enable = yes
smtp_sasl_password_maps = hash:/etc/postfix/sasl/sasl_passwd
smtp_sasl_security_options = noanonymous
smtp_tls_CAfile = /etc/postfix/cacert.pem
smtp_use_tls = yes
message_size_limit = 10485760 #10Mb
mynetworks = 0.0.0.0/8 #aceita qualquer rede. ideal personalizar com a sua rede
#mynetworks = 192.168.100.0/24, 10.153.227.17 #ip dos servidores liberados para enviar email separado por virgula
inet_interfaces = all
inet_protocols = all
</pre>

O arquivo de configuração do Postfix deve ficar assim:

<img class="aligncenter size-full wp-image-934" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-011.png" alt="homelaber-mailrelay-postfix-gmail-011" width="1139" height="193" />

Agora vamos criar as chaves de criptografia para proteger o arquivo onde a senha de acesso da sua conta será guardada.

<pre class="lang:default decode:true">cat /etc/ssl/certs/Thawte_Premium_Server_CA.pem | tee -a /etc/postfix/cacert.pem</pre>

Edite o arquivo /etc/postfix/sasl/sasl_passwd.

<pre class="lang:default decode:true">nano /etc/postfix/sasl/sasl_passwd</pre>

Copie e cole o texto abaixo no arquivo e configure com as suas informações.

<pre class="lang:default decode:true ">[smtp.gmail.com]:587 USERNAME@gmail.com:PASSWORD</pre>

O arquivo deve ficar assim:

<img class="aligncenter size-full wp-image-931" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-mailrelay-postfix-gmail-008.png" alt="homelaber-mailrelay-postfix-gmail-008" width="734" height="77" />

[su_box title="ATENÇÃO" box_color="#FF0000"]Se a sua conta do Gmail tem o segundo fator de autenticação habilitado, será necessário criar uma senha de aplicativo para utilizar aqui, caso contrário não irá funcionar.

<b>Como gerar uma senha de app: </b>
<ul type="square">
	<li>Acesse a página Senhas de app <a href="https://security.google.com/settings/security/apppasswords"> link </a>. Talvez seja necessário fazer login na sua Conta do Google.</li>
	<li>Na parte inferior da página, clique em Selecionar aplicativo e escolha o aplicativo que você está usando.</li>
	<li>Clique em Selecionar dispositivo e escolha o dispositivo que você está usando.</li>
	<li>Selecione Gerar.</li>
	<li>Siga as instruções para inserir a senha de app (o código de 16 caracteres na barra amarela) no seu dispositivo.</li>
	<li>Selecione Concluído.</li>
</ul>
[/su_box]

Altere as permissões do arquivo:

<pre class="lang:default decode:true">chmod 400 /etc/postfix/sasl/sasl_passwd</pre>

Execute a criptografia:

<pre class="lang:default decode:true">postmap /etc/postfix/sasl/sasl_passwd</pre>

E para finalizar reinicie o serviço do Postfix:

<pre class="lang:default decode:true">service postfix restart</pre>

Prontinho. O seu servidor de MailRelay já está instalado e configurado!

[su_note radius="0"]Troubleshooting:[/su_note]

Para fazer o teste, abra uma segunda janela e monitore o log do Postfix com o comando abaixo. Todos os e-mails enviados com sucesso ou não aparecerão nesse arquivo.

<pre class="lang:default decode:true ">tail -f /var/log/maillog</pre>

Para enviar um e-mail utilize o comando abaixo:

echo "MONITOR ... AVISO DE MONITORAÇÃO HOMELAB" | mail -s "MONITOR DO SEU HOMELAB" -a "From: monitor@homelab.srv.br" presidenta@presidencia.gov.br

É isso! Finalizamos mais um post.

Escreva nos comentário se você conseguiu fazer a instalação e como está usando o Postfix no seu lab.

<img class="aligncenter size-full wp-image-942" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/gato-no-computador.jpeg" alt="gato-no-computador" width="600" height="400" />

Faça igual ao gatinho ai da foto! Curta a página do <a href="http://fb.com/homelaber" target="_blank">Homelaber Brasil no Facebook</a> - já estou apelando para gatinhos :)