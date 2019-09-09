---
ID: 266
post_title: >
  Como criar Pendrive com Boot do VMware
  EXSi utilizando a ferramenta Rufus
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1BQopsn
published: true
post_date: 2015-04-01 12:03:17
---
Olá Homelaber!

Nesse post, vamos aprender como criar um Pendrive com o boot do VMware ESXi para instalação do seu servidor ESXi utilizando a ferramenta Rufus. <a href="https://rufus.akeo.ie/">https://rufus.akeo.ie/</a>

<strong><img class="aligncenter size-full wp-image-267" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/Rufus-Crie-drives-USB-bootaveis-facilmente.jpg" alt="Rufus - Crie drives USB bootaveis facilmente" width="588" height="227" /></strong>

Fazendo o boot e instalando o ESXi no pendrive, você irá economizar um HD no seu servidor ESXi e ainda terá a faciliade de quando quiser testar outra versão ou ainda outro virtualizador, não precisa gastar tempo reinstalando tudo do zero. É só dar o boot pelo pendrive e pronto.

<!--more-->

Primeiramente, vamos fazer o download do Rufus no site <a href="https://rufus.akeo.ie/">https://rufus.akeo.ie/</a> . A versão atual é a 2.1, mas sempre acesse o site para baixar a ultima versão. Eu particularmente prefiro utilizar a versão “portable”, pois não necessita de instalação, mas isso fica a seu critério.

Inicie o Rufus

&nbsp;

<img class="aligncenter size-full wp-image-272" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-01.png" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-01" width="320" height="480" />

Clique no ícone
<img class="size-full wp-image-271 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-02.png" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-02" width="41" height="33" /> e selecione o ISO do VMware

&nbsp;

Cliquem em OK. O seu pendrive será apagado.

<strong><img class="aligncenter size-full wp-image-270" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-03.png" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-03" width="402" height="165" /> </strong>

Clique em Iniciar e aguarde

<img class="aligncenter size-full wp-image-269" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-04.png" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-04" width="320" height="480" />

&nbsp;

Quando o processo finalizar (são 5 etapas), o pendrive está pronto para ser iniciado no seu servidor.

<img class="aligncenter size-full wp-image-273" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-06.jpg" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-06" width="320" height="244" />

<img class="aligncenter wp-image-268 size-large" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/homelaber-criando-usb-boot-vmware-esxi-com-rufus-05-1024x578.png" alt="homelaber-criando-usb-boot-vmware-esxi-com-rufus-05" width="1024" height="578" />

&nbsp;

Esse é um procedimento bastante fácil e tranquilo e pode ser utilizado não somente para criar pendrive de boot do VMware ESXi, mas também do Windows Server, Distros Linux, etc.

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no<a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidade do blog.