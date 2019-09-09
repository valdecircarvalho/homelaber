---
ID: 1336
post_title: >
  3 distros Linux pequenas e leves para o
  seu home lab
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/24yVj0s
published: true
post_date: 2016-05-04 11:00:43
---
Olá Homelabers!

Nesse post vou falar sobre algumas distribuições (distro) Linux bem pequenas para aqueles momentos onde você precisa apenas fazer alguns testes seu lab, mas não quer (ou não pode) subir um SO (Sistema Operacional) grande e pesado.

Eu costumo usar bastante essas distros quando preciso testar redes (interconexão de uma rede com outra) e também testes de vMotion e HA.

Essas distros linux são simples, leves e não consomem muitos recursos de disco, memória ou processador.

Vamos lá?

<img class="aligncenter size-full wp-image-1353" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/fat-penguin-e1462411923638.png" alt="fat-penguin" width="300" height="269" />

<!--more-->

<a href="http://tinycorelinux.net/intro.html" target="_blank">TinyCore Linux</a>

Uma das versões mais conhecidas. Atualmente no release 7.0,  é apresentada em 3 versões:

Core - (11 MB) - Versão reduzida, apenas interface de texto (tela preta).

TinyCore - (16 MB) - Versão normal, com interface gráfica

CorePlus - (106 MB) - Versão completa, com interface gráfica e com alguns programas simples pré-instalados.

Nos meus testes eu consegui subir uma VM do TinyCore com apenas 256Mb de memória. Tentei subir com 128Mb e não deu certo. De qualquer maneira, é uma VM bem pequena para um sistema totalmente funcional.

Link para download: <a href="http://tinycorelinux.net/downloads.html" target="_blank">http://tinycorelinux.net/downloads.html</a>

<img class="alignnone wp-image-1337" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/tiny-core-linux.png" alt="Tela Tiny Core Linux" width="800" height="600" />

Tela Tiny Core Linux

<a href="http://puppylinux.org/" target="_blank">Puppy Linux</a>

Outra distribuição bastante conhecida e antiga. A imagem é bem pequena, variando entre 100Mb e 250Mb com a versão completa já com o OpenOffice instalado.

Nos meus testes, não consegui subir uma VM com menos de 256Mb de RAM.

<a href="ftp://ftp.vcu.edu/pub/gnu_linux/puppylinux/puppy-slacko-6.3.0/64/slacko64-6.3.0.iso" target="_blank">Download versão 6.3</a>

[caption id="attachment_1341" align="aligncenter" width="800"]<img class="wp-image-1341" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/PuppyLinux-ScreenShot.png" alt="Tela PuppyLinux" width="800" height="640" /> Tela PuppyLinux[/caption]

<a href="http://www.damnsmalllinux.org/" target="_blank">DammSmallLinux (DSL)</a>

Mais uma distribuição clássica e que já está ai há muitos anos (desde 2005), 11 anos para ser exato.

A versão mais recente é a 4.11 e o download tem 50Mb. Nos meus testes, consegui subir uma VM com 256Mb de memória e rodou liso.

Link para download: <a href="http://www.damnsmalllinux.org/download.html" target="_blank">http://www.damnsmalllinux.org/download.html</a>

[caption id="attachment_1350" align="aligncenter" width="800"]<img class="wp-image-1350" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/dsl-4.2.x.jpg" alt="Damm Small Linux" width="800" height="600" /> Damm Small Linux[/caption]

Vou deixar aqui um link da Wikipedia, onde você poderá conferir dezenas de outras distribuições pequenas e leves para o seu home lab.

<a href="https://en.wikipedia.org/wiki/Lightweight_Linux_distribution" target="_blank">https://en.wikipedia.org/wiki/Lightweight_Linux_distribution</a>

Em resumo, são 3 distribuições bastante sólidas e leves, que sobem liso com 256MB de memória RAM e ajudam muito no home lab para realização de testes.

<img class="aligncenter size-full wp-image-1354" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/im_fat_but_at_least_im_not_a_window.jpg" alt="im_fat_but_at_least_im_not_a_window" width="400" height="400" />

Deixe nos comentários sua opinião sobre essas distribuições linux. Se você já usou ou usa alguma delas ou comente se você usa alguma outra que não apareceu aqui!

Edit: Depois que publiquei esse post, fiquei pensando, em tempos de Containers, Docker, etc... será que essas imagens ainda são utilizadas? Comenta ai...

Até o próximo post!