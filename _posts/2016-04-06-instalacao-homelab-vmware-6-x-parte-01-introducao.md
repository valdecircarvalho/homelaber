---
ID: 1245
post_title: 'Instalação Homelab VMware 6.x &#8211; Parte 01 &#8211; Introdução'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1RDDPLO
published: true
post_date: 2016-04-06 04:00:23
---
Olá Homelabers!

Como <a href="http://homelaber.com.br/acabou-o-carnaval/" target="_blank">prometido</a>, estou de volta com o Reboot da série <strong>Instalação Home lab VMware</strong>.

E desta vez eu vou até o final. Escolhi fazer de uma maneira diferente dessa vez, em formato de videos, para tornar a coisa mais dinâmica e <del>mais fácil</del> (para vocês) seguirem a série.

Eu gosto de texto, posts longos e cheios de figuras (como os blogs da década passada), mas o mundo mudou. A nova geração (vocês) preferem videos e não o antigo e ultrapassado (será) textão. E como eu sou um cara "antenado" e "<a href="http://s.dicio.com.br/prafrentex.jpg" target="_blank">prafrentex</a>" resolvi embarcar nessa também.

<img class="aligncenter size-full wp-image-1293" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/homelab-serie-reboot.png" alt="Instalação Homelab VMware 6.x" width="697" height="409" />

Não vou deixar de lado os posts (com texto e figuras) do blog para produzir apenas videos, mas os videos serão muito mais frequentes aqui. Dito isso, chega de enrolação e vamos lá:<!--more-->

<h2>Video 1 - Introdução</h2>

<img class="aligncenter size-full wp-image-1273" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide002.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide002" width="800" height="450" />

Nessa série vamos apresentar a instalação completa de um ambiente VMware sendo executado diretamente do VMware Workstation Pro. Você poderá cria esse laboratório no seu desktop ou notebook, sem a necessidade de um “servidor”.

Vamos trabalhar com um cenário fictício, onde você é o SysAdmin de uma empresa que irá implantar uma solução VMware para virtualização dos servidores físicos atualmente instalados.

Nesse video você verá os seguintes tópicos:

<ul>
<li>Os pré-requisitos para a instalação do nosso lab,</li>
<li>O cenário atual,</li>
<li>O cenário futuro,</li>
<li>As premissas do projeto e</li>
<li>Apresentação dos próximos passos.</li>
</ul>

<h3>Pré-Requisitos:</h3>

<img class="aligncenter wp-image-1278 size-full" title="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide007 " src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide007.jpg" alt="Hardware: Computador  com no mínimo 8GB de memória RAM (16GB ou mais é recomendado) &gt; 300GB de espaço livre no HD (recomendado um HD separado para as VMs) Software: VMware Workstation Pro VMware ESXi 6.x VMware vCenter 6.x Microsoft Windows Server 2012 R2 Datacenter Microsoft Windows 7 Professional Linux Ubuntu Server" width="800" height="450" />

Vamos utilizar a versão de avaliação de todos os software aqui listados, então se você não tem acesso aos software de forma legal (<a href="http://homelaber.com.br/como-montar-um-homelab-software/" target="_blank">já expliquei aqui como conseguir softwares para os eu home lab sem ter de recorrer a pirataria.</a>) utilize as versões de avaliação. Para facilitar as coisas, eu vou deixar no final do post, um link onde você poderá fazer o download de TODOS os programas e software que utilizaremos ao longo da série.

Falando em Hardware, eu estou utilizando <a href="http://homelaber.com.br/homelab-movel-thinkpad-w510/">aquele notebook que<del> comprei</del> fiz rolo recentemente</a>. Para quem não lembra é um Lenovo W510 - Intel i7 com 32Gb de RAM e 2 SSDs.

<h3>Cenário Atual:</h3>

Eu gosto sempre de trabalhar com cenários fictícios, pois acredito que dessa maneira fica mais fácil apresentar (e pensar) no problema e também mais divertido.

<img class="aligncenter wp-image-1279 size-full" title="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide008" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide008.jpg" alt="Você trabalha como SysAdmin em uma empresa de médio porte chamada FIRMALABS e a sua infraestrutura hoje é composta por servidores antigos, sem garantia e sem suporte do fabricante. Você enfrenta problemas frequentes de quedas e paradas dos sistemas durante o dia e o seu trabalho consiste em apagar incêndios e manter o ambiente funcionando da melhor maneira possível. A sua diretoria aprovou um orçamento para o refresh tecnológico de sua infraestrutura e você será o responsável pelo projeto. Foi decidido que todos os servidores físicos serão substituídos por um ambiente virtualizado baseado nos produtos VMware. A arquitetura de rede, no momento será mantida, portanto está fora do escopo do projeto." width="800" height="450" />

<img class="aligncenter size-full wp-image-1280" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide009.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide009" width="800" height="450" />

<img class="aligncenter size-full wp-image-1281" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide010.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide010" width="800" height="450" />

<img class="aligncenter size-full wp-image-1282" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide011.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide011" width="800" height="450" />

<h3>Cenário Futuro:</h3>

Esse é o cenário que iremos chegar ao final da série. Claro que mudanças ao longo do projeto poderão acontecer, como acontecem na grande maioria dos projetos. Mas esse é o nosso NORTE.

<img class="aligncenter wp-image-1283 size-full" title="Cenário Futuro" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide012.jpg" alt="Cenário Futuro" width="800" height="450" />

<h3>Premissas do Projeto:</h3>

<h3><img class="aligncenter size-full wp-image-1284" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide013.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide013" width="800" height="450" /></h3>

<h3>Próximos Passos:</h3>

No próximo video, iremos finalmente botar a mão na massa e começar com a instalação do VMware Workstation e do nosso primeiro host ESXi.

<img class="aligncenter size-full wp-image-1285" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Instalação-Homelab-VMware-6-Parte-1-Introdução-Slide014.jpg" alt="Instalação Homelab VMware 6 - Parte 1 - Introdução - Slide014" width="800" height="450" />

Novamente, faça o download dos arquivos. Se a sua internet for lenta, deixe baixando ou faça o download ao menos dos arquivos que iremos utilizar no próximo video.

É só acessar o link que está no final do post (uma pasta compartilhada no site mega.co) e baixar os arquivos abaixo. <strong>Update:</strong> <em>Ouvi dizer que o Mega.co está "limitando" o volume de downloads agora, então mais uma razão para você começar a fazer os downloads o quanto antes.</em>

<img class="aligncenter wp-image-1290" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/arquivos-download-mega-lab-vmware.png" alt="arquivos-download-mega-lab-vmware" width="800" height="171" />

Instalador do ESXi: VMware-VMvisor-Installer-201507001-2809209.x86_64.iso - (360Mb)

Instalador do VMware Workstation: VMware-workstation-full-12.1.0-3272444.exe (300Mb)

[su_box title="Links para Download:" style="glass" box_color="#FF0000"]

<b><a href="http://bit.ly/1MRvF2f"> http://bit.ly/1MRvF2f </a> </b>
<b>_Download PPT apresentação &gt;&gt; <a href="http://bit.ly/1qtsBPM"> http://bit.ly/1qtsBPM </a> </b>
<b>_Download ISO (mega.co) &gt;&gt; <a href="http://bit.ly/1TB8tXt"> http://bit.ly/1TB8tXt </a> </b>
[/su_box]

<h3>Pegue a sua pipoca e curta o filme :)</h3>

<img class="aligncenter size-full wp-image-1294" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Optimized-toystoryandpopcorn-106487-e1459926498116.jpeg" alt="Optimized-toystoryandpopcorn-106487" width="300" height="188" />

[su_youtube_advanced url="https://youtu.be/uBcU8h2jmCA" width="900" height="600" rel="no" modestbranding="yes" theme="light" https="yes" wmode="transparent"]

É isso pessoal! Termina aqui mais um post/video. Peço a vocês que deixe seus comentários no post,<a href="http://bit.ly/youtubehomelaber" target="_blank"> assine o nosso canal no YouTube</a> e <a href="http://facebook.com/homelaber" target="_blank">curta a nossa página no Facebook</a>. O seu feedback é muito importante para mim, pois estou fazendo esse trabalho de coração e desde o inicio a ideia foi sempre tentar criar conteúdo de qualidade em Português.

Até a próxima!