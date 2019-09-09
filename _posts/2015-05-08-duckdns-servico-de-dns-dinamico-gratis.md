---
ID: 563
post_title: 'DuckDNS &#8211; Serviço de DNS Dinâmico Grátis'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1zQVmtr
published: true
post_date: 2015-05-08 09:00:28
---
Olá Homelabers!

Hoje vou apresentar a vocês um serviço bastante bacana e útil para nossos Home Labs:<a href="https://www.duckdns.org/" target="_blank"> <strong>DuckDNS</strong></a>.

O DuckDNS é um serviço de DNS dinâmico grátis aos moldes do noip.net, do dyndns entre outros.

<img class="aligncenter size-full wp-image-568" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/Copy-of-duckydns.png" alt="Copy of duckydns" width="800" height="193" />

<!--more-->

Se você não sabe o que é um DNS dinâmico, senta que lá vem história:

<blockquote>Como o DNS funciona?

<strong>DNS significa Domain Name System</strong>
<p class="nomarg"><em>São como as páginas brancas da lista telefônica para a Internet. Você fornece um nome, o DNS fornece um número. O nome, neste caso, é especificamente um nome de host e o número é um endereço IP. Sem o DNS, você teria que lembrar de cada endereço IP de cada site que você deseja visitar.</em></p>
<em>Um computador pessoal conectado na internet recebe um número que o identifica, o seu endereço IP. Porém, em alguns casos como conexões ADSL (Speed, Velox, Netetc), este número varia a cada conexão (IP dinâmico) impossibilitando que seu computador seja encontrado na internet (acesso remoto).</em>

<em>O DDNS (Dynamic Domain Name System) é um dns dinâmico que associa o endereço IP da sua conexão atual a um nome fixo criado por você. Ou seja, com o DDNS o seu computador pessoal agora pode ser encontrado através de um endereço tipo “seucomputador.ddns.com.br” possibilitando o acesso remoto.</em>

Aqui no <a href="http://www.noip.com/pt-BR/what-is-dns" target="_blank">site</a> do NoIP.com tem um texto bem bacana com um videozinho (em Inglês) explicando direitinho como funciona o DNS e o DDNS.</blockquote>

Eu escolhi o DuckDNS pois hoje, na minha opinião é o melhor e mais simples serviço grátis disponível no mercado.Eu já usei o NoIP.com e o Dydns (que era pago) e estou gostando muito do DuckDNS.

Acesse o site do DuckDns.org

<img class="aligncenter wp-image-624" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-008.png" alt="configurar-duckdns-008" width="800" height="349" />

Faça o login com alguma das opções a seguir: Twitter, Facebook, Reddit ou Google

<img class="aligncenter wp-image-625" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-007.png" alt="configurar-duckdns-007" width="800" height="354" />

Escolha o nome do seu dominio.duckdns.org e clique em Add Domain

<img class="aligncenter size-full wp-image-622" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-006.png" alt="configurar-duckdns-006" width="405" height="72" />

<img class="aligncenter wp-image-621" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-005.png" alt="configurar-duckdns-005" width="800" height="56" />

Clique em install

Escolha o seu dominio

<img class="aligncenter size-full wp-image-620" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-004.png" alt="configurar-duckdns-004" width="585" height="106" />

O DuckDns oferece mais de uma dezena de opções entre elas Windows, Linux, Mac, pfSense, dd-wrt, etc. Escolha o que melhor se adeque as suas necessidades. Eu por exemplo, optei por instalar o aplicativo de Windows em uma VM que já rodava outra aplicação para facilitar.

<img class="aligncenter wp-image-619" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-003.png" alt="configurar-duckdns-003" width="800" height="98" />

Você será apresentado ao passo-a-passo para configuração do cliente no seu sistema, basta seguir os passos indicados.

<img class="aligncenter wp-image-618" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-002.png" alt="configurar-duckdns-002" width="800" height="270" />

Pronto! O seu DDNS está configurado. Agora você deve configurar o seu roteador para fazer o redirecionamento de portas para a sua aplicação, mas isso depende de roteador para roteador e infelizmente não tenho como colocar um tutorial aqui para cada tipo de roteador. Mas basta procurar no Google por redirecionamento de portas ou encaminhamento de portas junto com o nome do seu equipamento.

Outro ponto para se levar em consideração, é que a maioria dos provedores de internet bloqueiam o acesso as principais portas (80, 21, 22, etc), então será necessário utilizar uma porta alternativa no redirecionamento. Pode parecer complicado a primeira vista, mas basta dar uma procurada na internet que você vai conseguir.

Um exemplo prático do uso do DNS Dinamico é a configuração de uma VPN para acesso remotou ou rodar um sistema de foto no seu servidor, acessar o seu computador via remote desktop. As possibilidades são infinitas.

Eu subi uma VM Linux com uma aplicação bem simples para testar o DuckDNS. Acesse o endereço <a href="http://homelaber.duckdns.org:8001/" target="_blank">http://homelaber.duckdns.org:8001/</a> para testar.

<img class="aligncenter wp-image-617" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/configurar-duckdns-001.png" alt="configurar-duckdns-001" width="800" height="411" />

Agora é a sua vez. Vai lá e configure uma conta no DuckDNS e faça o teste e depois volte aqui para contar o resultado :D

Se você tiver qualquer dúvida, é só deixar uma mensagem aqui que prometo que tento responder e te ajudar.

Até o próximo post.

Não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no<a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidade do blog.