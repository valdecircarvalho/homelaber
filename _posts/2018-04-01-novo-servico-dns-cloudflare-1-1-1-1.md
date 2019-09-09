---
ID: 4811
post_title: 'Novo serviço DNS &#8211; CloudFlare 1.1.1.1'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2H3c3YG
published: true
post_date: 2018-04-01 13:24:18
---
Olá Homelabers!

Qual servidor de DNS vocês costumam usar em seu ambiente?

Hoje, sim, dia 01/04, também considerado o <a href="https://pt.wikipedia.org/wiki/Dia_da_mentira" target="_blank" rel="noopener">dia da mentira</a>, a <a href="https://www.cloudflare.com/br/" target="_blank" rel="noopener">CloudFlare</a> lançou publicamente o seu serviço de DNS Público com um endereço IP terrivelmente fácil de se lembrar : 1.1.1.1 e 1.0.0.1

https://twitter.com/Cloudflare/status/980430875258212352

Para quem é mais antigo na área, o DNS <a href="https://www.tummy.com/articles/famous-dns-server/" target="_blank" rel="noopener">padrão era o 4.2.2.2 da Level3</a>. Anos depois o Google lançou o seu próprio serviço 8.8.8.8,  que acabou virando o padrão. Em 2016 a IBM apresentou o 9.9.9.9 (<a href="https://www.quad9.net/" target="_blank" rel="noopener">Quad9</a>) e agora a CloudFlare chega com o 1.1.1.1 #1dot1dot1dot1
<h2>O que é um servidor DNS e para que serve?</h2>
O DNS ou Servidor DNS (Domain Name System) é o serviço responsável por converter - ou melhor dizendo RESOLVER - um nome de domínio para o seu correspondente endereço IP. O DNS é a grande lista telefônica da internet.

https://www.youtube.com/watch?v=ACGuo26MswI

Outro <a href="https://howdns.works/" target="_blank" rel="noopener">link bem legal explicando como funciona um servidor de DNS</a>
<h2>Porque usar o 1.1.1.1 ?</h2>
<ul style="list-style-type: square;">
 	<li>O serviço é totalmente gratuito</li>
 	<li>Privacidade - É o foco da CloudFlare para o serviço - eles prometem nunca gravar sua solicitação de DNS no disco e não manter os registros por mais de 24 horas.</li>
 	<li>Velocidade - Baixa latência e baixo tempo de resposta - em média 14ms para endereços fora da sua rede</li>
 	<li>Suporte a DNS over HTTPS eDNS-over-TLS, o que significa que até mesmo seu ISP não saberá qual nome de domínio você está solicitando.</li>
 	<li>Suporte a IPv6</li>
 	<li>Presença - A CloudFlare e consequentemente seu novo serviço está presente em 151 cidades espalhadas por 74 países, <a href="https://blog.cloudflare.com/parabens-brasil-cloudflares-27th-data-center-now-live/" target="_blank" rel="noopener">incluindo o Brasil</a></li>
</ul>
<img class="aligncenter size-large wp-image-4812" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/rede-cloudflare-no-mundo-644x389.jpg" alt="" width="644" height="389" />

Eu já uso alguns serviços da CloudFlare aqui no Homelaber, como DNS Autoritativo, WAF, Cache, CDN, etc e vou passar a utilizar o seu DNS público no meu lab e também como DNS principal da minha rede aqui de casa.
<h2>Testes</h2>
De acordo com o site <a href="https://www.dnsperf.com/#!dns-resolvers,South%20America" target="_blank" rel="noopener">dnsperf</a>, o 1.1.1.1 é o servidor de DNS mais rápido no momento para a América do Sul

<img class="aligncenter size-large wp-image-4814" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/dnsperf-resultado-america-do-sul-644x478.jpg" alt="" width="644" height="478" />

Link para o anúncio: https://blog.cloudflare.com/announcing-1111/

Link para o post explicando como o serviço foi concebido e criado: https://blog.cloudflare.com/dns-resolver-1-1-1-1/

E ai? Você vai mudar o seu DNS atual para o 1.1.1.1? Responda ai nos comentários.

&nbsp;

&nbsp;