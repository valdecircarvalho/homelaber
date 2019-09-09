---
ID: 820
post_title: >
  Instalar e configurar o SquidAnalyzer no
  Ubuntu Server
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1Q8S0rc
published: true
post_date: 2015-11-03 10:00:51
---
Olá Homelabers!

No <a href="http://homelaber.com.br/instalacao-e-configuracao-proxy-squid-no-ubuntu-server/">post anterior</a>, realizamos a instalação e configuração do <a href="http://homelaber.com.br/instalacao-e-configuracao-proxy-squid-no-ubuntu-server/">Squid Proxy</a>. Agora chegou a hora de aprender como instalar e configurar o <a href="http://squidanalyzer.darold.net/" target="_blank">SquidAnalyzer</a>, um software responsável por ler e formatar os logs do Squid de uma forma totalmente gráfica e intuitiva. É uma excelente ferramenta para que o administrador do Squid possa entender o que passa pelo seu proxy, quais são as URLs de maior acesso, usuários, etc.

Mais uma vez, assim como no post do Squid, o que você aprender aqui pode ser aplicado em seu ambiente de trabalho e não somente em seu HomeLab.

<img class="aligncenter size-full wp-image-825" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_3.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_3" width="1280" height="123" />

<!--more-->

Os pré-requisitos para a instalação do Squid Analyzer são:

<ul>
<li>Servidor Apache (ou Nginx)</li>
<li>Perl</li>
<li>Squid Proxy já instalado e configurado. Vamos fazer a instalação no mesmo servidor do Squid.</li>
</ul>

[su_note radius="0"]Atenção, todos os comandos desse post foram executados como root. Para isso basta digitar sudo su e colocar a sua senha.[/su_note]

Primeiramente vamos realizar a instalação do Apache executando o comando abaixo.

<pre class="theme:terminal lang:default decode:true">apt-get install apache2</pre>

<img class="aligncenter size-full wp-image-834" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_12.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_12" width="1033" height="331" />

<img class="aligncenter size-full wp-image-832" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_10.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_10" width="1033" height="161" />

Para confirmar a instalação, abra um browser e acesse o IP do seu servidor. A tela abaixo deverá aparecer.

<img class="aligncenter size-full wp-image-833" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_11.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_11" width="1241" height="331" />

O próximo passo é instalar o make. Execute o comando abaixo:

<pre class="lang:default decode:true">apt-get install make</pre>

Agora vamos fazer o download do Squid Analyzer. O comando abaixo irá baixar a última versão (6.3-1 na data de publicação desse post) do repositório. O arquivo é bem pequeno tem apenas 152Kb.

<pre class="lang:default decode:true">wget http://sourceforge.net/projects/squid-report/files/latest/download -O squidanalyzer.tar.gz</pre>

Descompate o arquivo baixado usando o comando:

<pre class="lang:default decode:true ">tar zxvf squidanalyzer.tar.gz</pre>

Acesse o diretório e execute os comandos para realizar a instalação

<pre class="lang:default decode:true ">cd squidanalyzer-6.3-1/

Pearl Makefile.PL

make

make install</pre>

<img class="aligncenter size-full wp-image-831" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_9.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_9" width="1033" height="173" /> <img class="aligncenter size-full wp-image-830" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_8.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_8" width="1033" height="109" /> <img class="aligncenter size-full wp-image-829" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_7.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_7" width="1033" height="492" />

Feito isso, chegou a hora de configurar o Apache:

Vamos mover a pasta do SquidAnalyzer para o local correto:

<pre class="lang:default decode:true">mv /var/www/squidanalyzer/ /var/www/html/squidanalyzer</pre>

O próximo passo é criar um Virtual Host no Apache para o SquidAnalyzer. Digite o comando abaixo para criar um novo arquivo:

<pre class="lang:default decode:true">nano /etc/apache2/sites-availabe/squidanalyzer.conf</pre>

Cole o texto abaixo

<pre class="lang:default decode:true">&lt;VirtualHost *:80&gt;
ServerAdmin webmaster@localhost
DocumentRoot /var/www/html/squidanalyzer
ErrorLog ${APACHE_LOG_DIR}/squidanalyzer-error.log
CustomLog ${APACHE_LOG_DIR}/squidanalyzer-access.log combined

</pre>

<span style="line-height: 1.5;">Edite o arquivo squidanalyzer.conf e realize as alterações descritas abaixo:</span>

<pre class="lang:default decode:true">nano /etc/squidanalyzer/squidanalyzer.conf</pre>

#alterar a linha Output de <strong>/var/www/squidanalyzer</strong> para <span style="color: #0000ff;">/var/www/html/squidanalyzer</span>

<span style="line-height: 1.5;">#alterar a linha WebUrl para <span style="color: #0000ff;">/squidanalyzer</span></span>

O arquivo deve ficar igual a figura:

<img class="aligncenter size-full wp-image-828" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_6.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_6" width="1033" height="314" />

Agora vamos fazer o restart do Apache para carregar as modificações

<pre class="lang:default decode:true ">service apache2 restart</pre>

Execute o squidanalyzer:

<pre class="lang:default decode:true ">/usr/local/bin/squid-analyzer -d</pre>

<strong>Aqui cabe uma explicação:</strong> <em>O SquidAnalyzer apenas lê os logs de acesso do Squid quando executado.</em>

Abra o browser e acesse a url http:///squidadnalyzer

<img class="aligncenter size-full wp-image-826" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/instalacao-squidanalyzer-ubuntu-homelaber_4.png" alt="instalacao-squidanalyzer-ubuntu-homelaber_4" width="1280" height="800" />

Voialá... Sucesso. Agora os toques finais.

Vamos adicionar o squidanalyzer na crontab (agendador de tarefas do Linux) para que ele execute sozinho. Em nosso exemplo o SquidAnalyzer vai rodar a cada 5 minutos.

<pre class="lang:default decode:true ">crontab -e</pre>

Cole as linhas abaixo no final do arquivo.

<pre class="lang:default decode:true ">#executa o squidanalyzer a cada 5 minutos.
*/5 * * * * /usr/local/bin/squid-analyzer 2&gt;&amp;1 | /home/timestamp.sh &gt;&gt; /var/log/squidanalyzer-cron.log</pre>

Agora você deve explorar a interface do SquidAnalyzer, que é bastante simples e intuitiva.

Você poderá também explorar o arquivo de configurações do SquidAnalyzer (/etc/squidanalyzer/squidanalyzer.conf) para fazer modificações pertinentes ao seu ambiente. O arquivo está bem documentado. Mas lembre-se de fazer um backup antes.

É isso pessoal. Finalizamos mais um post. Espero que tenha sido útil a você.

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.