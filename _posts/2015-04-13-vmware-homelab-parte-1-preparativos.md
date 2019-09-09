---
ID: 306
post_title: >
  VMware HomeLab – Parte 1 –
  Preparativos
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1FBtIwO
published: true
post_date: 2015-04-13 09:00:59
---
Olá HomeLabers!

Esse é o segundo post da série VMware HomeLab e iremos falar sobre os preparativos para a instalação do nosso HomeLab.

O primeiro passo é verificar e garantir que o hardware onde será instalado o VMware ESXi atender os requisitos mínimos para a instalação. Existe um KB (2017269) da VMware indicando esses requisitos e pode ser consultado <a href="http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&amp;cmd=displayKC&amp;externalId=2017269">aqui</a>. Em resumo necessitamos de:

<ul>
    <li>CPU x86 64 bits e 2 cores</li>
    <li>2GB Memória RAM</li>
    <li>1 Placa de rede</li>
</ul>

<!--more-->

Após garantir que o seu hardware é suportado para a instalação, o próximo passo é fazer o download do VMware ESXi através do site da VMware. <a href="https://my.vmware.com/web/vmware/evalcenter?p=vsom">https://my.vmware.com/web/vmware/evalcenter?p=vsom</a>

<img class="aligncenter wp-image-308 " src="http://homelaber.com.br/site/wp-content/uploads/2015/04/VMware-HomeLab-–-Parte-1-–-Preparativos_01-1024x500.png" alt="VMware HomeLab – Parte 1 – Preparativos_01" width="735" height="295" />

Se você não tiver uma conta no my.vmware.com, basta criar clicando em “Create an Account” e seguir o passo-a-passo no site.

<img class="aligncenter wp-image-309 " src="http://homelaber.com.br/site/wp-content/uploads/2015/04/VMware-HomeLab-–-Parte-1-–-Preparativos_02.png" alt="VMware HomeLab – Parte 1 – Preparativos_02" width="788" height="361" />

&nbsp;

O link correto para baixar a versão 5.5 (a que iremos utilizar nesse laboratório) é <strong><a href="https://my.vmware.com/group/vmware/info?slug=datacenter_cloud_infrastructure/vmware_vsphere_with_operations_management/5_5">https://my.vmware.com/group/vmware/info?slug=datacenter_cloud_infrastructure/vmware_vsphere_with_operations_management/5_5</a></strong>

Por padrão, você será direcionado para baixar a ultima versão (6.0) mas esse não é o nosso intuito. Então, após se registrar, utilize a URL acima.

<img class="aligncenter  wp-image-310" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/VMware-HomeLab-–-Parte-1-–-Preparativos_03-1024x478.png" alt="VMware HomeLab – Parte 1 – Preparativos_03" width="778" height="346" />

&nbsp;

Faça o download dos seguintes componentes:

<b>ESXi 5.5 Update 2 Driver Rollup (Includes VMware Tools) - ISO - 340 MB</b>

<b>VMware vCenter Server 5.5 Update 2d and modules - ISO - 3 GB</b>

Feito o download, guarde os arquivos para o próximo post, onde iniciaremos a instalação do VMware ESXi no seu Homelab.

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

&nbsp;