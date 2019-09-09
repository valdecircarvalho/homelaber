---
ID: 1602
post_title: 'Alpine Linux &#8211; Uma nova distro linux ligth que vale a pena conhecer'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1Y2n3IM
published: true
post_date: 2016-06-06 02:31:57
---
Olá Homelabers!

Essa semana por meio de uma galera do grupo <a href="https://telegram.me/infraestruturati" target="_blank">Infraestrutura TI</a> no Telegram conheci uma nova distro Linux super levinha chamada Alpine Linux (<a href="http://www.alpinelinux.org/" target="_blank">http://www.alpinelinux.org/</a>).

&nbsp;

<img class="aligncenter wp-image-1603 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/Alpine_Linux.png" alt="Alpine Linux - www.alpinelinux.org" width="665" height="162" />

<blockquote>Segundo o site, o Alpine Linux é uma distro independente, não comercial e de uso geral, criada para power users que buscam segurança, simplicidade e eficiência de recursos.  Foi criado tendo por base <a href="https://en.wikipedia.org/wiki/Musl" target="_blank">musl libc</a> e <a href="https://en.wikipedia.org/wiki/BusyBox" target="_blank">busybox</a>, o que permitiu criar uma distro extremamente enxuta.</blockquote>

<!--more-->

O <a href="http://www.alpinelinux.org/downloads/" target="_blank">download do Alpine Linux</a> tem apenas 87MB em sua versão Standard. E em meus testes, consegui rodar em uma VM com 128MB de memória.

Estou testando o Alpine Linux e gostando muito. A curva de aprendizagem para quem está acostumado com outras distros como Ubuntu, CentOS, RedHat é bastante curta e a documentação existente no site é bem completa.

Vale comentar que ainda existem versões para Raspberry Pi e outros dispositivos ARM. Essa distro promete!

E ao que parece, o Alpine Linux vem chamando a atenção nos últimos tempos, de acordo com o <a href="https://www.google.com/trends/explore#q=%22alpine%20linux%22" target="_blank">Google Trends</a>.

<img class="aligncenter wp-image-1624" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/alpine-linux-google-trends.jpg" alt="alpine-linux-google-trends" width="800" height="325" />

Eu já fiz um <a href="http://homelaber.com.br/3-distros-linux-pequenas-e-leves-para-o-seu-home-lab/" target="_blank">post aqui sobre Distros Ligths</a> e o Alpine Linux certamente merece um lugar de destaque nessa categoria.

Acabei fazendo um video com a instalação e as primeiras configurações do Alpine, assim facilita para o pessoal.

[embed]https://youtu.be/qiGnjQ4mRns[/embed]

<h3>Instalação</h3>

A instalação do Alpine Linux é feita em 3 simples passos:

<ol>
    <li>Fazer o download do ISO em <a href="http://www.alpinelinux.org/downloads/" target="_blank">http://www.alpinelinux.org/downloads/</a> Para simplificar, use a versão Standard.</li>
    <li>Crie um pendrive de boot usando o <a href="http://homelaber.com.br/criando-ubs-boot-vmware-exsi-com-rufus/" target="_blank">Rufus</a> (instruções no link)</li>
    <li>De o boot pelo pendrive, logue com o usuário "root" sem senha e pronto! Está feito!</li>
</ol>

<img class="aligncenter wp-image-1621" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-009.png" alt="tutorial-alpine-linux-homelaber-009" width="800" height="480" />

<img class="aligncenter wp-image-1620" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-008.png" alt="tutorial-alpine-linux-homelaber-008" width="800" height="121" />

Após a instalação, você deve executar o comando:

<pre class="float-enable:true lang:default decode:true">setup-alpine</pre>

Esse comando irá nos guiar através de um wizard bem simples (em modo texto)

<img class="aligncenter wp-image-1619" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-007.png" alt="tutorial-alpine-linux-homelaber-007" width="800" height="190" />

<img class="aligncenter wp-image-1618" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-006.png" alt="tutorial-alpine-linux-homelaber-006" width="800" height="187" />

<img class="aligncenter wp-image-1617" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-005.png" alt="tutorial-alpine-linux-homelaber-005" width="800" height="396" />

<img class="aligncenter wp-image-1616" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-004.png" alt="tutorial-alpine-linux-homelaber-004" width="800" height="158" />

<img class="aligncenter wp-image-1615" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-003.png" alt="tutorial-alpine-linux-homelaber-003" width="800" height="421" />

&nbsp;

<h3>Pós-Instalação</h3>

<strong>Trabalhando com pacotes no Alpine Linux (instalar, remover, atualizar, procurar, etc)</strong>

O gerenciador de pacotes utilizado pelo Alpine Linux é o apk

Abaixo está uma tabela com os comandos no Alpine Linux e seus correspondentes no Ubuntu/Debian e RHEL/CentOS

<table style="width: 1019px; border-color: #000000;">
<tbody>
<tr>
<td style="width: 260px; text-align: center;">Ação</td>
<td style="width: 247px; text-align: center;">Alpine Linux (apk)</td>
<td style="width: 247px; text-align: center;">Ubuntu/Debian (apt)</td>
<td style="width: 239px; text-align: center;">RHEL/CentOS (yum)</td>
</tr>
<tr>
<td style="width: 260px; text-align: center;">Instalar pacote</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true">apk add [nome-do-pacote]</pre>
</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true ">apt-get install [nome-do-pacote]</pre>
</td>
<td style="width: 239px; text-align: center;">
<pre class="lang:default decode:true ">yum install [nome-do-pacote]</pre>
</td>
</tr>
<tr>
<td style="width: 260px; text-align: center;">Remover pacote</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true"> apk del [nome-do-pacote]</pre>
</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true ">apt-get remove [nome-do-pacote]</pre>
</td>
<td style="width: 239px; text-align: center;">
<pre class="lang:default decode:true ">yum remove [nome-do-pacote]</pre>
</td>
</tr>
<tr>
<td style="width: 260px; text-align: center;">Atualizar todos os pacotes instalados</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true">apk upgrade -U -a</pre>
</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true ">apt-get update &amp;&amp; apt-get upgrade</pre>
</td>
<td style="width: 239px; text-align: center;">
<pre class="lang:default decode:true ">yum update &amp;&amp; yum upgrade</pre>
</td>
</tr>
<tr>
<td style="width: 260px; text-align: center;">Procurar pacotes</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true">apk search [string]</pre>
</td>
<td style="width: 247px; text-align: center;">
<pre class="lang:default decode:true ">apt-get search [string]</pre>
</td>
<td style="width: 239px; text-align: center;">
<pre class="lang:default decode:true">yum search [string]</pre>
</td>
</tr>
</tbody>
</table>

<strong>Como configurar hostname</strong>

As configurações do hostname estão localizadas no arquivo <em>/etc/hostname</em>

Para configurar o hostname de seu servidor, execute o comando :

<pre class="lang:default decode:true">setup-hostname

/etc/init.d/hostname --quiet restart</pre>

<strong>Como configurar interface de rede</strong>

As configurações de rede estão localizadas no arquivo <em>/etc/network/interfaces</em>

Para configurar a(s) interface(s) de rede de seu servidor, execute o comando:

<pre class="lang:default decode:true">setup-interfaces

/etc/init.d/networking --quiet start</pre>

<strong>Como configurar DNS</strong>

As configurações de DNS estão localizadas no arquivo <em>/etc/resolv.conf</em>

Para configurar o DNS em seu servidor, execute o comando:

<pre class="lang:default decode:true">setup-dns</pre>

<strong>Como configurar Timezone</strong>

Para configurar o Timezone de seu servidor, execute o comando:

<pre class="lang:default decode:true ">setup-timezone</pre>

<strong>Como configurar o Proxy</strong>

Para configurar o Proxy de seu servidor, execute o comando:

<pre class="lang:default decode:true ">setup-proxy</pre>

Os dados do proxy deve ser inseridos utilizando o formado: <em>http://&lt;url-ou-ip-do-proxy&gt;:&lt;porta-do-proxy&gt;</em>, para excluir o proxy, execute o comando novamente e escolha<em> [none]</em>.

<strong>Como acessar o console via SSH com o usuário root</strong>

Se você tentar acessar o console do servidor via SSH com o usuário root, não vai conseguir, pois o sshd vem por default configurado para bloquear acessos do usuário root, por motivos de segurança.

Para contornar esse problema, você deve ou criar um novo usuário ou alterar o parâmetro "<strong>PermitRootLogin</strong>" para <strong>yes</strong> dentro do arquivo <em>/etc/ssh/sshd_config</em> e em seguida reiniciar o servidor sshd utilizand o comando <em>service sshd restart</em>

Como instalar acf (Alpine Configuration Framework)

O Alpine ACF é uma "aplicação" web para gerenciamento e monitoração do Alpine. E a seus instalação é feita com o comando:

<pre class="lang:default decode:true ">setup-acf</pre>

Após a instalação, basta acessar o ip ou url do seu servidor (com https).

<em>https://&lt;ip-do-servidor&gt;</em>

<img class="aligncenter wp-image-1614" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-002.png" alt="tutorial-alpine-linux-homelaber-002" width="800" height="522" />

<img class="aligncenter wp-image-1613" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-001.png" alt="tutorial-alpine-linux-homelaber-001" width="800" height="522" />

<img class="aligncenter wp-image-1612" src="http://homelaber.com.br/site/wp-content/uploads/2016/06/tutorial-alpine-linux-homelaber-000.png" alt="tutorial-alpine-linux-homelaber-000" width="800" height="522" />

<strong>Onde está o comando man?</strong>

O comando man não é instalado por padrão. Primeiramente, execute o comando abaixo para instalar o pacote do man:

<pre class="lang:default decode:true ">apk add man</pre>

O próximo passo é instalar o pacote de documentação do pacote ou comando desejado, executando o comando:

<pre class="lang:default decode:true ">apk add &lt;package-doc&gt;</pre>

ex: apk add nano-doc

Mas atenção, nem todos os pacotes tem disponível o pacote do manual. Para uma lista de todos os pacotes "-doc" execute o comando:

<pre class="lang:default decode:true ">apk search | grep doc | more</pre>

(se você tiver uma sugestão melhor, deixe um comentário no post!)

<strong>Repositório de Pacotes</strong>

O repositório de pacotes está localizado no arquivo <em>/etc/apk/repositories</em>

Instalando Java 8 no Alpine Linux

Para instalar o Java 8 no Alpine Linux, execute os comandos abaixo:

<pre class="lang:default decode:true ">apk add openjdk8-jre-base --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ --allow-untrusted \ &amp;&amp; rm -rf /var/cache/apk/*</pre>

Se você precisar instalar o Java da Oracle, <a href="http://blog.takipi.com/lean-mean-java-virtual-machine-making-your-docker-7x-lighter-with-alpine-linux/" target="_blank">aqui</a> e <a href="https://developer.atlassian.com/blog/2015/08/minimal-java-docker-containers/" target="_blank">aqui</a> são bons lugares para encontrar ajuda.

<h3>Links:</h3>

Não deixe de visitar esses links sobre o Alpine Linux:

Alpine Linux no <a href="https://en.wikipedia.org/wiki/Alpine_Linux" target="_blank">Wikipedia</a>

Twitter - <a href="https://twitter.com/alpinelinux" target="_blank">@alpinelinux</a>

<a href="http://forum.alpinelinux.org/forum" target="_blank">Forum Alpine Linux</a>

<a href="https://wiki.alpinelinux.org/wiki/Main_Page" target="_blank">Wiki (leitura obrigatória)</a>

<a href="http://distrowatch.com/weekly.php?issue=20150706#alpine" target="_blank">Review no Distrowatch</a> (em Inglês)

É isso ai pessoal! Mais um post e video publicado!

Deixe os seus comentários e até a próxima!

VC