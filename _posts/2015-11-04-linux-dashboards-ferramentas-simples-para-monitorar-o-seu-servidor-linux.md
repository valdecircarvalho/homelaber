---
ID: 842
post_title: 'Linux Dashboards &#8211; Ferramentas simples para monitorar o seu servidor Linux'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1KWK0T2
published: true
post_date: 2015-11-04 09:50:19
---
Olá Homelabers!

<img class="aligncenter size-full wp-image-852" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/virus-aquarium.png" alt="virus-aquarium" width="500" height="234" />

Nesse post vou apresentar a vocês 3 opções de ferramentas simples, porém muito poderosas para monitorar o seu servidor Linux.

Eu gosto muito de "fuçar" no GitHub e foi lá que encontrei essas ferramentas.

Todas elas necessitam apenas de um servidor Linux com Apache (ou outro servidor web) e Php instalado e podem ser executadas em todas as distribuições.

<!--more-->

Antes de mostrar como instalar cada uma das ferramentas, vamos instalar os pacotes básicos e comum aos 3 sistemas.

Como premissa, vou considerar que o Apache já está instalado no seu servidor.

Execute o comando abaixo como root:

<pre class="lang:sh decode:true">apt-get install unzip php5 libapache2-mod-php5</pre>

Agora vamos a apresentação e instalação de cada ferramenta.

<h2><strong>Linux Dash</strong></h2>

<a href="https://github.com/afaqurk/linux-dash" target="_blank">https://github.com/afaqurk/linux-dash</a>

Esse é o meu Dashboard predileto. Ele é simples, mas ao mesmo tempo mostra bastante informações úteis sobre o servidor. Possui temas, animações e é super leve.

Você pode acompanhar com gráficos em tempo real informações sobre Memórioa, CPU, Processos, Disco, Rede, etc.

<img class="aligncenter wp-image-844" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-simples-linux-monitores-em-php-003.png" alt="homelaber-simples-linux-monitores-em-php-003" width="900" height="486" />

Instalação:

Baixar o arquivo do GitHub

<pre class="lang:default decode:true">wget https://github.com/afaqurk/linux-dash/archive/master.zip -O linux-dash.zip</pre>

Descompactar o arquivo

<pre class="lang:default decode:true">unzip linux-dash.zip</pre>

Mover os arquivos para a pasta html do Apache

<pre class="lang:default decode:true">cp -v -R linux-dash-master/ /var/www/html/dash/</pre>

Reiniciar o Apache

<pre class="lang:default decode:true">service apache2 restart</pre>

Abrir o browser e navegar ate o endereço: http:///dash/

<h2><strong>eZ Server Monitor</strong></h2>

<a href="https://github.com/shevabam/ezservermonitor-web" target="_blank">https://github.com/shevabam/ezservermonitor-web</a>

Esse é a mais customizável das 3 ferramentas apresentadas aqui. Possui informações do Sistema, Carga, Disco, CPU, Rede, etc.

É possível customizar o tema (cor do sistema), os módulos apresentados, etc. Para maiores informações, acesse a página do desenvolvedor <a href="http://www.ezservermonitor.com/esm-web/documentation" target="_blank">http://www.ezservermonitor.com/esm-web/documentation</a>

<img class="aligncenter wp-image-845" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-simples-linux-monitores-em-php-002.png" alt="homelaber-simples-linux-monitores-em-php-002" width="900" height="486" />

Instalação:

Baixar o arquivo do GitHub

<pre class="lang:default decode:true">wget https://github.com/shevabam/ezservermonitor-web/archive/master.zip -O ezservermonitor-web.zip</pre>

Descompactar o arquivo

<pre class="lang:default decode:true">unzip ezservermonitor-web.zip</pre>

Mover os arquivos para a pasta html do Apache

<pre class="lang:default decode:true">cp -v -R ezservermonitor-web-master/ /var/www/html/ezmonitor/</pre>

Reiniciar o Apache

<pre class="lang:default decode:true">service apache2 restart</pre>

Abrir o browser e navegar ate o endereço: http:///ezmonitor/

<h2><strong>Dashboard</strong></h2>

<a href="https://github.com/jenssegers/dashboard" target="_blank">https://github.com/jenssegers/dashboard</a>

Esse é o mais simples das 3 ferramentas apresentadas. Ela funciona apenas no Ubuntu. Apresenta informações sobre Uptime, Memória, CPU, Disco e Network.

<img class="aligncenter wp-image-846" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-simples-linux-monitores-em-php-001.png" alt="homelaber-simples-linux-monitores-em-php-001" width="900" height="486" />

Instalação:

Baixar o arquivo do GitHub

<pre class="lang:default decode:true">wget https://github.com/jenssegers/dashboard/archive/master.zip -O dashboard.zip</pre>

Descompactar o arquivo

<pre class="lang:default decode:true">unzip dashboard.zip</pre>

Mover os arquivos para a pasta html do Apache

<pre class="lang:default decode:true">cp -v -R dashboard-master/ /var/www/html/dashboard/</pre>

Reiniciar o Apache

<pre class="lang:default decode:true">service apache2 restart</pre>

Abrir o browser e navegar ate o endereço: http:///ezmonitor/

É isso! Finalizamos mais um post. Agora é a sua vez, instale essas ferramentas em seus servidores, explore, veja o que mais lhe seja útil, mostre aos seus colegas...

Em breve, pretendo fazer um post apresentando verdadeiras ferramentas de monitoração usadas pelas empresas. Aguarde!

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

&nbsp;