---
ID: 534
post_title: 'phpIPAM &#8211; Open Source IP Address Management'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1HNFTwL
published: true
post_date: 2015-04-27 09:00:15
---
Olá Homelabers!

Neste post vou apresentar o <a href="http://phpipam.net/">phpIPAM</a>, uma ferramenta Open Source, bastante útil para a administração de qualquer rede, seja a rede de seu pequeno Home lab com apenas 1 bloco /24 ou a rede de sua empresa com diversas redes, com milhares de IPs, VLANs, VRF, etc. Essa aplicação será bastante útil no seu ambiente de Home lab para evitar que você crie IPs duplicados ou fique na dúvida sobre qual IP está vago para associar a aquela nova VM que você está subindo.

&nbsp;

<img class="aligncenter size-full wp-image-535" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/phpipam_logo_small@2x.png" alt="phpipam_logo_small@2x" width="650" height="160" />

<!--more-->

Existem diversas ferramentas para gerenciamento de IP, tanto open source como comerciais. Eu testei diversas ferramentas open source e a que mais gostei (comparando as funcionalidades, estabilidade, facilidade de operação, usabilidade, etc) foi o phpIPAM, tanto é que utilizo essa ferramenta em produção na empresa onde trabalho. <a href="http://en.wikipedia.org/wiki/IP_address_management" target="_blank">Aqui tem um link do Wikipedia</a> que mostra algumas das principais ferramentas. Vale a pena dar uma olhada para conhecer.

<blockquote>Em um ambiente corporativo, um software de IPAM (seja qual for) substitui de maneira elegante aquela velha planilha excel de IPs que nunca está atualizada e muitas vezes perdida na rede. #ficaadica - se você não tem uma ferramenta de IPAM na sua empresa, está aqui uma boa chance de apresentar algo novo ;0</blockquote>

O phpIPAM roda em cima da stack <a href="http://en.wikipedia.org/wiki/LAMP_(software_bundle)" target="_blank">LAMP (Linux, Apache, MySQL e PHP)</a> e neste post vamos realizar a instalação passo-a-passo desse software.

<strong>Requisitos:</strong>

Neste tutorial vamos utilizar o <a href="http://www.ubuntu.com/server" target="_blank">Ubuntu Server</a> como base

<ul>
<li>Apache2</li>
<li>MySQL (5.1+)</li>
<li>Php versão 5.3 ou posterior com seguintes módulos PHP ativados: mysqli, session, gmp, ldap, crypt, SimpleXML, json, gettext, pcntl e cli.
Normalmente, a maioria dos módulos php necessários estão presentes na nstalação padrão. Se faltar algum módulo php, o instalador irá falhar e avisar. Você pode verificar quais módulos php são ativados através do comando <em>php -m</em>.</li>
</ul>

No meu caso, tive que instalar alguns módulos e executei os comandos abaixo:

<pre class="lang:default decode:true ">apt-get install libgmp-dev
apt-get install php-pear
apt-get install php5-gmp
apt-get install php5-ldap
apt-get install php5-json
apt-get install php-gettext
service apache2 restart

</pre>

<strong>Instalação:</strong>

<span style="line-height: 1.5;">Crie um diretorio para fazer o download do phpipam</span>

<pre class="lang:default decode:true ">mkdir dl</pre>

Mude para o diretorio de download

<pre class="lang:default decode:true ">cd dl</pre>

Faça o download do arquivo

<pre class="lang:default decode:true ">wget http://nbtelecom.dl.sourceforge.net/project/phpipam/phpipam-1.1.010.tar</pre>

Descompacte o arquivo

<pre class="lang:default decode:true ">tar -xvf phpipam*.tar</pre>

Copie o diretório descompactado para o diretório do apache. No meu caso /var/www/html

<pre class="lang:default decode:true ">cp -r -v phpipam/ /var/www/html/</pre>

Mude para o diretorio do phpipam

<pre class="lang:default decode:true ">cd /var/www/html/phpipam/</pre>

Edite o arquivo<strong> config.php</strong> para configurar o diretorio do phpipam

<pre class="lang:default decode:true">nano config.php</pre>

Atualize a linha com o texto "define('BASE', "/");" para "define('BASE', "/phpipam/");"

<img class="aligncenter size-full wp-image-539" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/2015-04-26_00-50-07.png" alt="2015-04-26_00-50-07" width="748" height="61" />

Edite o arquivo <strong>.htaccess</strong> para configurar o diretorio do phpipam

<pre class="lang:default decode:true">nano .htaccess</pre>

Atualize a linha com o texto "RewriteBase /" para "RewriteBase /phpipam/"

<img class="aligncenter size-full wp-image-540" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/2015-04-26_00-50-46.png" alt="2015-04-26_00-50-46" width="598" height="53" />

Abra o browser e acesse http://ip-do-seu-servidor/phpipam/ e a tela de instalação irá aparecer. Clique na opção: <strong>1 Automatic database instalation</strong>

<img class="aligncenter size-full wp-image-550" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-011.png" alt="homelaber-instalacao-phpIPAM-011" width="800" height="371" />

Preencha os campos <strong>MySQL username</strong> e <strong>MySQL password</strong> com as informações de usuário e senha do seu servidor MySQL e clique no botão <strong>Install phpipam database</strong>

<img class="aligncenter size-full wp-image-547" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-008.png" alt="homelaber-instalacao-phpIPAM-008" width="800" height="396" />

Clique no botão Continue

<img class="aligncenter size-full wp-image-546" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-007.png" alt="homelaber-instalacao-phpIPAM-007" width="800" height="449" />

Preencha os campos <strong>Admin password</strong> com uma senha de sua preferencia. Clique no botão<strong> Save settings</strong>

<img class="aligncenter size-full wp-image-545" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-006.png" alt="homelaber-instalacao-phpIPAM-006" width="800" height="449" />

Clique no botão <strong>Proceed to login</strong> para finalizar a instalação

<img class="aligncenter size-full wp-image-544" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-005.png" alt="homelaber-instalacao-phpIPAM-005" width="800" height="449" />

Faça o login com o usuário "admin" e a senha que vocês escolheu

<img class="aligncenter size-full wp-image-542" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-003.png" alt="homelaber-instalacao-phpIPAM-003" width="800" height="449" />

<img class="aligncenter size-full wp-image-552" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-instalacao-phpIPAM-100.png" alt="homelaber-instalacao-phpIPAM-100" width="800" height="298" />

Pronto, agora basta configurar o phpIPAM com as suas redes e começar a gerenciar seus IPs de uma maneira mais organizada.

Se você tiver qualquer dúvida sobre como instalar ou utilizar o phpIPAM, deixe um comentário no post que terei o maior prazer de responder e tentar te ajudar!

Links úteis:

<a href="https://phpipam.net/demo/" target="_blank">Demo phpIPAM</a>

<a href="http://phpipam.net/documents/" target="_blank">Documentação</a>

[su_box title="Resumo:"]Este post apresenta o software phpIPAM, software open source que facilita o gerenciamento de endereço IPs em uma rede e mostra o passo a passo da instalação do software no Ubuntu 14.04.
<b>phpIPAM:</b> <a href="http://phpipam.net/"> http://phpipam.net/ </a> [/su_box]

É isso Homelabers! Fico por aqui e espero que vocês tenham gostado. Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado com as novidades do blog.