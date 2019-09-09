---
ID: 894
post_title: >
  Instalação e configuração SNMP Linux
  Ubuntu
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1kHY7q4
published: true
post_date: 2015-11-08 15:00:07
---
Olá Homelabers!!!

Nesse post, vou mostrar como se configura o serviço SNMP no Linux Ubuntu Server.

<img class="aligncenter size-full wp-image-897" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/logo-5.2.jpg" alt="logo-5.2" width="816" height="218" />

Antes de mais nada, vou responder a quem vive me perguntando (e criticando): Porque você só posta "coisas" do Ubuntu?

Vamos lá:

<ol>
    <li>
<blockquote>Porque eu <em>gosto muito mais do Ubuntu</em> do que de outras distros como CentOS, RedHat, etc.</blockquote>
</li>
    <li>
<blockquote>Porque eu tenho <em>muito mais facilidade</em> em utilizar o Ubuntu do que outras distros</blockquote>
</li>
    <li>
<blockquote><em>Eu sei que outras distros como o CentOS, RedHat, etc são mais utilizadas no ambiente corporativo</em>, mas nem tanto assim.</blockquote>
</li>
    <li>
<blockquote>Eu <em>sei fazer tudo o que eu quero (ou quase tudo no CentOS ou RedHat) mas eu <strong>GOSTO</strong> do Ubuntu</em></blockquote>
</li>
</ol>

Pronto, mas se vocês meus caros amigos e leitores quiserem que eu poste aqui como fazer "as coisas" tanto no Ubunto como no CentOS, perfeito, eu farei - <strong>deixe o seu comentário no blog :)</strong> ) Caso contrário... vou continuar no meu querido Ubuntu.

Agora chega de <a href="https://www.youtube.com/watch?v=X7u7h3-Yufk" target="_blank">chorumelas</a> e vamos ao post.

<!--more-->

<img class="aligncenter size-full wp-image-903" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/chorumelas.jpg" alt="chorumelas" width="266" height="189" />

&nbsp;

O SNMP é um protocolo da pilha TCP (porta UDP 161) que é responsável pelo gerenciamento de dispositivos de rede. SNMP significa <a href="https://pt.wikipedia.org/wiki/Simple_Network_Management_Protocol">Single Network Manage Protocol </a>ou Protocolo Simples de Gerenciamento de Rede em português.

Ele é amplamente utilizado por ferramentas de monitoração como o Cacti, Nagios, Zabbix, OpManager e  outros - <a href="http://homelaber.com.br/10-ferramentas-para-monitoracao-de-redes-e-servidores/">listados no post anterior</a>.

Não vou me alongar aqui nesse post a falar sobre como o <a href="http://pt.slideshare.net/maximillianx/network-monitoring-basics?related=1" target="_blank">SNMP funciona</a>, etc (mas prometo falar em outro post), mas sim em como realizar a sua instalação e configuração no ambiente Linux Ubuntu.

Então vamos lá:

Acesse o seu servidor Linux Ubuntu já instalado (<a href="http://homelaber.com.br/como-instalar-e-configurar-o-linux-ubuntu-server/">ver outro posto sobre a instalação do Ubuntu</a>) como root (
)

Digite o comando para instalar o SNMP:

<pre class="lang:default decode:true">apt-get install snmp snmpd lm-sensors snmp-mibs-downloader snmptrapd</pre>

<img class="aligncenter size-full wp-image-896" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/snmp.png" alt="snmp" width="1046" height="262" />

Após a instalação, o próximo passo é fazer uma cópia do arquivo de configuração do SNMP utilizando o comando abaico:

<pre class="lang:default decode:true">mv /etc/snmp/snmpd.conf /etc/snmp/snmpd.conf.ori</pre>

Após isso, vamos editar o arquivo snmpd.conf e colocar as configurações necessárias.

<pre class="lang:default decode:true">nano /etc/snmp/snmpd.conf</pre>

Aqui você deve copiar e colar as informções abaixo.

<pre class="lang:default decode:true ">view all included .1
rocommunity homelab #nome da community
sysLocation homelab #local do equipamento
sysContact admin@homelab.srv.br #email de contato do equipamento

</pre>

Salve o arquivo (no nano CTRL+X e Y para salvar) e reinicie o serviço SNMP.

<pre class="lang:default decode:true ">service snmpd restart</pre>

Pronto! O serviço SNMP está instalado e configurado. Agora vamos fazer o teste. Execute o comando abaixo:

<pre class="lang:default decode:true ">snmpwalk -v2c localhost -c homelab .1</pre>

<img class="aligncenter size-full wp-image-899" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/snmpwalk-exemplo.png" alt="snmpwalk-exemplo" width="752" height="177" />

O resultado deverá ser parecido com a tela acima.

Prontinho... o SNMP está instalado, configurado e testado no seu sistema.

Agora que você já sabe configurar o serviço SNMP em seus hosts Linux Ubuntu, você já pode correr atrás e instalar um sistema de monitoração com os citados no post anterior.

Mas se você ainda não se sente confortável em arriscar a instalação de uma das ferramentas postadas no útimo post, aguarde que eu vou fazer um post para cada ferramenta (ou as mais famosas ok?).

É isso meus amigos, fico aqui com mais um "tutorial" e não se esqueçam de  deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

[caption id="attachment_905" align="aligncenter" width="600"]<img class="wp-image-905 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/O-Exterminador-do-Futuro-joinha.jpg" alt="O-Exterminador-do-Futuro-joinha" width="600" height="424" /> Deixe o seu joinha!!![/caption]