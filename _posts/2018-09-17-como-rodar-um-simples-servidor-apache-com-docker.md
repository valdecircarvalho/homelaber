---
ID: 5186
post_title: >
  Como rodar um simples servidor Apache
  com Docker
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2MHWzKy
published: true
post_date: 2018-09-17 14:03:15
---
Olá Homelabers,

Você já precisou rodar um servidor web (Apache) para testar um código HTML rápidinho?

Pois então, sexta-feira passada, eu estava brincando de dev, criando um layout em HTML para um site da VMware e precisava testar localmente o código. Como o meu lab está desligado - falta de tempo, bandeira vermelha na conta de energia, etc - resolvi dar uma pesquisada rápida no google para subir um servidor Apache no Docker.

A operação é muito simples e vai te economizar um bocado de tempo. Veja como eu fiz:

Com o <strong>docker já instalado</strong> no Mac - esse procedimento vale para Windows e Linux também - execute o comando abaixo:

<code>docker run -dit --name web-xxxxx -p 8080:80 -v /Users/valdecircarvalho/Documents/DockerHD/vpro-map:/usr/local/apache2/htdocs/ httpd:2.4</code>

Explicando o comando:

<strong>docker run</strong> - executa o container
<strong>-dit</strong>
<strong>Detached (-d)</strong> - Roda o container em background
<strong>Interactive (-i)</strong> - Roda o container em modo interativo
<strong>tty (-t)</strong> - Roda o container com um pseudo TTY
<strong>--name</strong> web-xxxx
Cria um nome para o container
<strong>-p</strong> 8080:80
Redireciona a porta 80 do container para a porta 8080 do seu computador
<strong>-v</strong> /Users/valdecircarvalho/Documents/DockerHD/vpro-map:/usr/local/apache2/htdocs/
Redireciona o volume (diretório) <strong>/Users/valdecircarvalho/Documents/DockerHD/vpro-map</strong> do seu computador para o diretório <strong>/usr/local/apache2/htdocs/</strong> do container. Desse modo, basta você colocar o seu código nesse diretório e ele aparecerá automaticamente dentro do seu container  e vice versa, sem perder o seu código quando o container for desligado.
<strong>httpd:2.4</strong>
Nome da imagem que você vai usar. No caso, estou utilizando a versão 2.4 do apache (httpd).

Então, com um simples comando, você consegue subir um servidor web para testes.

E ai? Deixe nos comentários desse post, se isso foi útil para você!

&nbsp;