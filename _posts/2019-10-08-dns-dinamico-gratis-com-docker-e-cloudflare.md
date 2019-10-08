---
ID: 5866
post_title: >
  DNS Dinâmico Grátis com Docker e
  Cloudflare
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/35fDjyK
published: true
post_date: 2019-10-08 07:00:38
---
Olá Homelabers,

Qual serviço de DNS dinâmico vocês usam em seus labs ou suas empresas?

Nesse post vou mostrar a vocês como utilizar a <a href="http://cloudflare.com" target="_blank" rel="noopener noreferrer">Cloudflare</a> como DDNS substituindo o <a href="https://www.noip.com/pt-BR" target="_blank" rel="noopener noreferrer">NoIP.ne</a>t ou DYN com a vantagem de ser totalmente grátis e você pode usar seu próprio domínio.

Infelizmente o meu provedor de internet não oferece a opção de comprar um IP fixo para um contrato residencial- olha a demanda existente ai Vivo Fibra - sempre que preciso expor algum serviço do meu lab para internet ou acessar minhas cameras de segurança tenho que apelar para o redirecionamento de portas no meu roteador e para facilitar utilizar um DDNS.

Há anos que uso a Cloudflare para gerenciamento de DNS dos meus domínios e eu tenho um domínio válido para usar no lab (homelab.srv.br).

No passado eu <a href="http://homelaber.com.br/duckdns-servico-de-dns-dinamico-gratis/" target="_blank" rel="noopener noreferrer">utilizava o DuckDNS como meu DNS dinâmico</a> mas há algum tempo passei <strong>a utilizar a Cloudflare com um container Docker para atualizar o IP da minha conexão</strong> e nesse post vou mostrar a vocês como estou fazendo isso.

Eu gostaria muito que o registro.br oferecesse uma opção de gerenciamento de DNS via API.
<h2>Configuração Cloudflare</h2>
Primeiro você vai precisar <a href="https://dash.cloudflare.com/sign-up" target="_blank" rel="noopener noreferrer">criar a sua conta grátis</a> na Cloudflare.

Após criar sua conta, você precisa<span style="display: inline !important; float: none; background-color: #ffffff; color: #333333; cursor: text; font-family: 'Source Sans Pro',sans-serif; font-size: 18px; font-style: normal; font-variant: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: left; text-decoration: none; text-indent: 0px; text-transform: none; -webkit-text-stroke-width: 0px; white-space: normal; word-spacing: 0px;"> mudar o servidor de DNS do <a href="https://registro.br" target="_blank" rel="noopener noreferrer">registro.br</a> para a Cloudflare.</span>

Feito isso, crie um <strong>registro do tipo A</strong> na Cloudflare. Esse será o registro que atualizado automaticamente. No meu caso, eu usei <strong>vpn.homelab.srv.br</strong>
<h2>Docker</h2>
A segunda parte da configuração - e onde está toda a inteligência do projeto - é um container Docker. No meu caso, estou rodando esse container em um Raspberry Pi 3B, mas você pode rodar em uma VM ou onde você quiser.

Você precisa ter o Docker instalado e rodando (não vou cobrir isso neste post, mas <a href="https://docs.docker.com/install/" target="_blank" rel="noopener noreferrer">aqui você encontra as instruções para instalar o Docker</a>.)

Estou usando o container desse local (<a href="https://github.com/oznu/docker-cloudflare-ddns" target="_blank" rel="noopener noreferrer">https://github.com/oznu/docker-cloudflare-ddns</a>).

Aqui uso o <a href="https://docs.docker.com/compose/" target="_blank" rel="noopener noreferrer">Docker Compose</a> para subir o container e o código yaml para executar está aqui embaixo, mas você vai precisar colocar suas informações:

<code><span class="pl-ent">version</span>: <span class="pl-s"><span class="pl-pds">'</span>2<span class="pl-pds">'</span></span></code>
<code><span class="pl-ent">services</span>:</code>
<code>  <span class="pl-ent">cloudflare-ddns</span>:</code>
<code>    <span class="pl-ent">image</span>: <span class="pl-s">oznu/cloudflare-ddns:latest</span></code>
<code>    <span class="pl-ent">restart</span>: <span class="pl-s">always</span></code>
<code>    <span class="pl-ent">environment</span>:</code>
<code>      - <span class="pl-s">EMAIL=hello@example.com</span></code>
<code>      - <span class="pl-s">API_KEY=xxxxxxx</span></code>
<code>      - <span class="pl-s">ZONE=example.com</span></code>
<code>      - <span class="pl-s">SUBDOMAIN=subdomain</span></code>
<code>      - <span class="pl-s">PROXIED=false</span></code>

Você pode copiar o arquivo <a href="https://gist.github.com/valdecircarvalho/3653a3f7299d1a59cfd6a985a41bdf0a" target="_blank" rel="noopener noreferrer">docker-compose.yaml deste link</a>
<ul style="list-style-type: square;">
 	<li>No campo <strong>EMAIL</strong> você vai preencher com o e-mail usado no cadastro/login da Cloudflare.</li>
 	<li>No campo <strong>API_KEY</strong> você vai preencher com o código GLOBAL API KEY que você vai encontrar <a href="https://dash.cloudflare.com/profile/api-tokens" target="_blank" rel="noopener noreferrer">nesse link</a>. Cuidado com esse código, não compartilhe com ninguem!</li>
 	<li>No campo <strong>ZONE</strong> preencha com o seu domínio - no meu caso homelab.srv.br</li>
 	<li>No campo <strong>SUBDOMAIN</strong> preencha com o registro que você criou na Cloudflare - no meu caso usei VPN.</li>
</ul>
Feito isso, basta rodar o container executando o comando <code>docker-compose up -d</code>

Após alguns segundos, o container estará ativo e rodando. Você poderá validar se o seu IP está correto na Cloudflare comparando com o site <a href="http://www.meuip.com.br/" target="_blank" rel="noopener noreferrer">meuip.com.br</a>

Caso você queira outros hostnames, basta criar uma entrada do tipo CNAME na Cloudflare e adicionar o registro A principal que você criou.

<img class="aligncenter size-large wp-image-5873" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/cloudflare-ddns-configuracao-644x368.png" alt="" width="644" height="368" />
<h2>Próximos passos</h2>
Os próximos passos vão depender de você e infelizmente não vou conseguir postar aqui, pois cada modem/roteador tem a sua maneira de configurar o encaminhamento de portas (port forward) e também vai depender da sua operadora. Nesse<a href="https://portforward.com/" target="_blank" rel="noopener noreferrer"> site você irá encontrar instruções</a> para a grande maioria dos roteadores consumer do mercado, se não achar o seu, o google é sempre seu amigo.
<h2>Outras opções</h2>
Se você quiser utilizar a Cloudflare, mas não quer ou não tem como executar um container Docker, existem outras opções:
<ul style="list-style-type: square;">
 	<li>Cloudflare API - <a href="https://api.cloudflare.com/#dns-records-for-a-zone-update-dns-record" target="_blank" rel="noopener noreferrer">https://api.cloudflare.com/#dns-records-for-a-zone-update-dns-record</a></li>
 	<li>ddclient - <a href="https://www.cloudflare.com/technical-resources/#ddclient" target="_blank" rel="noopener noreferrer">https://www.cloudflare.com/technical-resources/#ddclient</a></li>
 	<li>DNS-O-Matic - <a href="https://dnsomatic.com/wiki/" target="_blank" rel="noopener noreferrer">https://dnsomatic.com/wiki/</a></li>
 	<li><a href="https://github.com/bruxo00/CloudIP" target="_blank" rel="noopener noreferrer">https://github.com/bruxo00/CloudIP</a></li>
 	<li><a href="https://github.com/mark-wagner/cfdc" target="_blank" rel="noopener noreferrer">https://github.com/mark-wagner/cfdc</a></li>
 	<li><a href="https://github.com/gigili/Cloudflare-dns-update" target="_blank" rel="noopener noreferrer">https://github.com/gigili/Cloudflare-dns-update</a></li>
</ul>
E ai? Deixe nos comentários o que você usa como solução de DDNS e se esse post te ajudou.

Até a próxima!