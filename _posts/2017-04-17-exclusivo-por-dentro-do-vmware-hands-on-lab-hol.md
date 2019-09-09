---
ID: 2745
post_title: 'Exclusivo: Por dentro do VMware Hands-on Lab (HOL)'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2nUhXou
published: true
post_date: 2017-04-17 09:00:07
---
<p class="">Olá Homelabers!</p>

Hoje vamos falar sobre o <strong>VMware Hands-On Labs (HOL)</strong>.

<p class="">Eu já fiz algumas postagens<a href="http://homelaber.com.br/lab-vmware-gratis-vmware-hol-hands-on-lab/" target="_blank"> aqui</a> sobre o HOL e posso dizer que sou um grande fã dessa ferramenta.</p>

<p class="">Na semana passada, tive a oportunidade de bater um longo papo com os responsáveis pelo HOL e descobrir o que  Sempre tive a curiosidade de saber o que existe <strong>debaixo do capô do HOL</strong>.</p>

<p class="">Então vamos lá!</p>

<img class="aligncenter wp-image-2778 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/vmware-hand-on-lab-under-the-hood.jpg" alt="" width="797" height="400" />

<h2 class="">O que é o VMware Hands-On Labs (HOL)?</h2>

<p class="">O <strong>VMware Hands-on Labs</strong> é um portal online gratuito criado pela VMware, que fornece acesso aos mais recentes produtos em um ambiente de laboratório virtual baseado em nuvem.</p>

<p class="">O VMware Hands-on Labs (HOL) pode ser acesso nesse link <a href="http://hol.vmware.com" target="_blank">hol.vmware.com</a></p>

<p class=""><img class="aligncenter size-medium wp-image-2777" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/VMW-LOGO-HANDS-ON-LABS-LO-300x69.png" alt="" width="300" height="69" /><!--more--></p>

<h2 class="">Números:</h2>

<p class="">Os números do HOL são impressionantes:</p>

<ul style="list-style-type: square;">
    <li>3 Datacenters</li>
    <li>+ 500 servers</li>
    <li>Time fixo de 10 pessoas e mais de 250 voluntários que são no fundo o coração do programa.</li>
    <li>+ 1 milhão de labs desde Janeiro '13</li>
    <li>+ 10 milhões de virtual machines</li>
    <li>Os usuários em média gastam 51 minutos no laboratório,</li>
    <li>Esses usuários fazem em média 3.7 laboratórios</li>
    <li>São entregues entre 1200 - 1800 laboratórios por dia</li>
    <li>São mais de 70 laboratórios e 400 módulos</li>
    <li>O volume de dados passa de  32 TB por nuvem</li>
</ul>

Vocês podem acompanhar os números e estatísticas do HOL de forma online no link <a href="http://go.hol.vmware.com/live-stats/" target="_blank">http://go.hol.vmware.com/live-stats/</a>

<img class="aligncenter wp-image-2768 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/2017-04-17_00-58-53.png" alt="" width="800" height="425" />

O projeto do HOL <strong>teve início em 2004</strong> e foi apresentado pela primeira vez durante a <strong>primeira VMworld em San Diego</strong>.

Em Janeiro de 2013, o projeto foi disponibilizado pela primeira vez ao público.

<img class="aligncenter wp-image-2779" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/New-users-1024x581-300x170.png" alt="" width="800" height="454" />

<h2>Top Labs:</h2>

Como era de se esperar, o lab mais acessado é o de NSX, e acredito que a principal razão seja a dificuldades em conseguir os "bits para instalação" ou ainda pela quantidade de recursos necessários para executar o NSX em um homelab.

<img class="aligncenter wp-image-2769 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/2017-04-17_01-00-29.png" alt="" width="800" height="423" />

<h2>Infraestrutura:</h2>

Essa era uma das minha maiores curiosidades. Qual é a infraestrutura que suporta o HOL?

Toda a infraestrutura do HOL é baseada em um modelo de Cloud, com um time interno responsável por manter e gerir tudo referente ao HOL.

<h2>Localização:</h2>

O HOL está distribuído em <strong>3 datacenters</strong>, sendo 2 nos EUA - Santa Clara na Califórnia e Washington State e 1 datacenter na Europa em Amsterdã, Holanda.

<h2>Hardware:</h2>

Os equipamentos responsáveis por suportar a enorme carga de trabalho são um mix de várias tecnologias. O parque computacional é basicamente formado por servidores Cisco UCS e agora servidores Dell. Na parte de storage são utilizados Storages EMC Extreme IO e VMware vSAN. Os equipamentos são constantemente atualizados.

<img class="aligncenter size-medium wp-image-2780" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/Dell-R820_1-300x140.png" alt="" width="300" height="140" />

<h2>Software:</h2>

A stack de software utilizada para suportar o HOL é basicamente composta de produtos VMware: vSphere 6.0 e 6.5 (em fase de migração) e vApps em conjunto com o vCloud Director.

<h2>Automação</h2>

Como era de se esperar, a base do HOL é a automação, pois para suportar uma carga de trabalho tão grande, automação e ferramentas de automação são fundamentais.

O grande desafio é o deploy de novos labs e a replicação entre datacenters. As principais ferramentas utilizadas são scripts em Powershell e PowerCLI em conjunto com o VMware vCloud Director.

<h2>O Time:</h2>

O time do HOL bastante grande, contando com um aproximadamente 10 pessoas fixas que cuidam de toda a sustentação do ambiente, suporte, desenvolvimento de novos labs, marketing, divulgação, etc. Existe também um outro time que não é fixo, que conta com mais de 250 pessoas focadas no desenvolvimento de novos labs.

No Brasil, temos uma pessoa que faz parte do time do HOL. É o <a href="https://www.linkedin.com/in/danny-farber-22a45823/" target="_blank">Danny Farber</a>, que supervisiona todas as necessidades da América Latina referentes ao HOL. Ele, em conjunto com a equipe internacional, são responsáveis pelo desenvolvimento da estratégia da LATAM + Brasil e tem um papel ativo na garantia de que os Laboratórios em manuais estejam localizados para os usuários brasileiros.

Os principais membros do time do HOL são (sigam esses caras no twitter):

<a href="https://www.linkedin.com/in/pabloroesch/" target="_blank"><strong>Pablo Roesch</strong></a> - Director Technical Marketing - @heyitspablo
<a href="https://www.linkedin.com/in/dobaer/" target="_blank"><strong>Doug Baer</strong></a> (AKA Trevor) - @dobaer
<a href="https://www.linkedin.com/in/andrewhald/" target="_blank"><strong>Andrew Hald</strong></a> - Consulting Architect - @vmxl
<a href="https://www.linkedin.com/in/david-rollins-905a231/" target="_blank"><strong>Dave Rollins</strong></a> - Content Architect - @vmwdave

<img class="aligncenter wp-image-2767 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/VMware-Hands-On-Labs-Team-2016.jpg" alt="" width="800" height="300" />

<h2>Processo de seleção de conteúdo:</h2>

De acordo com Pablo Roesch, a escolha de novos conteúdos são feitas com base na demanda das BU (Business Units), releases de novos produtos e demanda dos usuários.

Novos conteúdos sempre são lançados para a VMWorld e o time trabalha o ano inteiro desenvolvendo novos labs.

Eles começaram a trabalhar no novo catálogo de 2017-2018 agora. Muitas novidades deverão aparecer até a VMworld '17 (eles não puderam contar) mas eu aposto que o BOOM será um lab de VMware com AWS.

https://twitter.com/VMwareHOL/status/852200815938949120

<h2>Catalogo de Labs</h2>

O catálogo completo do HOL conta com mais de 160 labs disponíveis em Inglês, Português, Japonês, Espanhol, Chinês e Coreano.

<img class="aligncenter wp-image-2785 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/language_logos.png" alt="" width="586" height="104" />

<h2>Labs em Português</h2>

Atualmente existem <strong>06 laboratórios traduzidos para o Português</strong> no catálogo do HOL:

<strong>HOL-1701-USE-2-PT</strong> - vRealize Operations e vRealize Business: otimizar utilização de processamento

<strong>HOL-1703-SDC-1-PT</strong> - Tour de recursos do Vmware NSX

<strong>HOL-1703-SDC-4-PT</strong> - Passo a passo da instalação VMware NSX

<strong>HOL-1708-SDC-1-PT</strong> - Introdução ao Virtual SAN

<strong>HOL-1710-SDC-6-PT</strong> - O que há de novo: vSphere with Operations Management

<strong>HOL-1757-MBL-3-PT</strong> - Introdução à integração do Workspace One com o VMware AirWatch

<img class="aligncenter wp-image-2775 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2017/04/2017-04-17_01-28-22.png" alt="" width="800" height="423" />

Video do Danny Farber explicando como funciona o HOL

[embed]https://youtu.be/O04Ln5qRkCQ[/embed]

Gostaria de deixar aqui o meu <strong>muito obrigado</strong> a todo o time do HOL, principalmente ao <strong>Pablo Roesch, </strong>que prontamente respondeu meu tweet, entrou em contato comigo e marcou o conference call, mobilizando várias pessoas importantes da comunidade e que trabalham diretamente com o HOL.

Vou deixar aqui alguns links referentes ao HOL, que valem a pena serem vistos com calma:

<ul style="list-style-type: square;">
    <li>Blog do HOL - <a href="https://blogs.vmware.com/hol/" target="_blank">https://blogs.vmware.com/hol/</a></li>
    <li>Twitter do HOL - <a href="https://twitter.com/@VMwareHOL" target="_blank">https://twitter.com/@VMwareHOL</a></li>
    <li><a href="https://communities.vmware.com/community/vmtn/resources/how/content?filterID=contentstatus%5Bpublished%5D~objecttype~objecttype%5Bthread%5D" target="_blank">Comunidade do HOL no VMTN</a></li>
    <li><a href="http://talkshoe.s3-website-us-east-1.amazonaws.com/TC-19367/TS-1159314.mp3" target="_blank">Episódio do VMware Community Roundtable Podcast sobre o HOL</a></li>
</ul>

E para finalizar, se ficou alguma dúvida, alguma curiosidade que não apareceu aqui, fiquem a vontade para me escreverem ou ainda, entrar em contato diretamente com o pessoal do HOL. Eles mostraram um interesse bastante genuíno sobre o Brasil, seus usuários e suas necessidades, ou seja, nós, então chegou a hora de aproveitar esse canal aberto e fazer contato.

<h2>Pesquisa:</h2>

A equipe do HOL me pediu para ajudá-los a descobrir quais conteúdos são relevantes para o público brasileiro e quais os labs que vocês mais gostam. Peço que por favor, preencham a pesquisa abaixo, pois irei compartilhar os resultados com eles. Essa é a nossa chance de poder contribuir e melhorar essa ferramenta incrível. Conto com vocês!

<iframe width="800" height="1300" src="https://docs.google.com/forms/d/e/1FAIpQLSdtVfSZjyGH4bnknZALbd_YN4IbS9EVQ_CNMhszN4N_ec83lA/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Carregando…</iframe>