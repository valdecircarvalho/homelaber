---
ID: 4919
post_title: 'VMware vSphere 6.7 &#8211; Novidades &#8211; Parte 1'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2HQ7nG1
published: true
post_date: 2018-04-19 08:00:14
---
Olá Homelabers!

Ontem a VMware anunciou o GA (General Availability) do VMware vSphere 6.7

Quase <a href="http://homelaber.com.br/vmware-vsphere-6-5-lancamento-oficial/" target="_blank" rel="noopener">um ano e meio após o release do VMware vSphere 6.5</a> e um dia após o seu aniversário de 20 anos essa nova versão está cheia de novidades e melhorias.

Nesse post, vou descrever brevemente as features que eu acredito que devam ser discutidas e mencionadas.
<ul style="list-style-type: square;">
 	<li>O vSphere Client (HTML5) tem cerca de 95% de recursos completos</li>
 	<li>Monitoramento aprimorado do vCenter appliance (VCSA)</li>
 	<li>Melhor gerenciamento de backup do vCenter</li>
 	<li>Atualizações do ESXi com Single Reboot</li>
 	<li>Inicialização rápida do ESXi</li>
 	<li>Suporte nativo para discos 4K</li>
</ul>
<img class="aligncenter size-large wp-image-4953" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vmware-vsphere-67-principais-novidades-novas-features-new-features-644x319.jpg" alt="" width="644" height="319" />
<h2>vSphere Client HTML5</h2>
O vSphere 6.7 <strong>marca a versão final do vSphere Web Client (Flash)</strong>

<img class="aligncenter size-large wp-image-4949" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vsphere-67-vsphere-client-features-parity-644x319.jpg" alt="" width="644" height="319" />

Essa é uma feature na wishlist de muita gente. Desde a versão 6.5 quando a <a href="https://blogs.vmware.com/vsphere/2016/05/goodbye-vsphere-client-for-windows-c-hello-html5.html" target="_blank" rel="noopener">VMware anunciou a morte do "Fat Client"</a> e o desenvolvimento de um client 100% baseado em HTML5 muita coisa evoluiu.

Infelizmente o <strong>Client HTML5 ainda não está 100% operacional</strong>, mas segundo a VMware nesse <strong>release teremos certa de 95% das funcionalidades implantadas</strong> e a VMware promete que <strong>novas funcionalidades serão incluídas nos próximos releases</strong>.

De acordo com Duncan Epping (@duncanyb), que já tem usado essa interface por um longo período de tempo, a interface é mais rápida e intuitiva.
<blockquote>I think the majority of you will be very very happy with what you will see and with the overall experience. It just <strong>feels fast(er)</strong> and seems <strong>more intuitive</strong>. Duncan Epping (<a href="http://www.yellow-bricks.com/2018/04/17/vsphere-6-7-announced/" target="_blank" rel="noopener">link</a>)</blockquote>
Há também um cliente a menos, a interface do Platform Services Controller (PSC) (/ psc) agora faz parte do vSphere Client. Agora, localizado no menu Administração, as opções do PSC são divididas entre duas guias. O gerenciamento de certificados tem sua própria guia e todos os outros gerenciamento estão na guia de configuração.

<img class="aligncenter size-large wp-image-4935" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vSphere-Client-6.7-644x362.png" alt="" width="644" height="362" />

Os destaques incluem:
<ul style="list-style-type: square;">
 	<li>vSphere Update Manager</li>
 	<li>Content Library</li>
 	<li>Suporte ao vSAN</li>
 	<li>Suporte ao vRealize Operations</li>
 	<li>Suporte ao NSX</li>
 	<li>Storage Policies</li>
 	<li>Host Profiles</li>
 	<li>Diagrama de topologia de vDS</li>
 	<li>Licenciamento</li>
</ul>
<h2>Monitoramento aprimorado do vCenter appliance (VCSA):</h2>
Outra feature muito bacana e que melhorou muito em relação a versão 6.5

O vSphere Appliance Management Interface (VAMI) - vcenter:5480 - foi reconstruído e está usando a nova interface padrão da VMware chamada <a href="https://vmware.github.io/clarity/" target="_blank" rel="noopener">Clarit UI</a>. Em relação ao VAMI da versão 6.5 agora existem várias novas tabs na interface relacionadas a saúde do VCSA.

Na tab de monitoração é possível ver o status de CPU, Memória, Discos, etc.

<img class="aligncenter size-large wp-image-4940" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/VCSA-6.7-VAMI-Disk-644x333.png" alt="" width="644" height="333" />
<h2>Melhor gerenciamento de backup do vCenter:</h2>
Na versão 6.5 já havia a possibilidade de fazer o backup do VCSA pela UI, mas não era possível fazer agendamentos. Na versão 6.7 você pode agendar backups, definir retenção, encriptar o backup e selecionar o que você quer fazer backup.

<img class="aligncenter size-full wp-image-4947" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vsphere-67-vcsa-vcenter-agendar-backup.jpg" alt="" width="640" height="544" />

<img class="aligncenter size-large wp-image-4952" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vsphere-67-backup-644x319.jpg" alt="" width="644" height="319" />
<h2>Atualizações do ESXi com Single Reboot:</h2>
Na versão 6.7 do VMware vSphrere a VMware eliminou um processo de boot para grandes releases, em outras versões eram necessários 2 boots e agora somente 1. Isso faz uma diferença enorme quando se você levar em conta que um servidor enterprise leva em torno de 10-15 minutos para reiniciar e você precisa atualizar um DC inteiro, é uma grande economia de tempo.

<img class="aligncenter size-large wp-image-4950" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vsphere-67-single-reboot-vsphere-quick-boot-644x319.jpg" alt="" width="644" height="319" />
<h2>Inicialização rápida do ESXi:</h2>
Essa é uma feature MUITO MUITO legal.

Basicamente, é uma maneira de reiniciar o hipervisor sem passar pelo processo de reinicialização do hardware físico. Isso significa que você está removendo a última reinicialização. Por enquanto somente alguns hardwares (servidores) serão compatíveis com essa feature.

https://www.youtube.com/watch?v=T3OZiuAJnmE&amp;list=PLNolXBQS42ixDXWTX3oHph4mZbFptSSPv

<strong>Lista de servidores compatíveis no momento:</strong>

Dell PowerEdge R630
Dell PowerEdge R640
Dell PowerEdge R730
Dell PowerEdge R740
HPE Proliant DL360 Gen9
HPE Proliant DL360 Gen10
HPE Proliant DL380 Gen9
HPE Proliant DL380 Gen10
Nested - ESXi Nested (viva os homelabs)
<h2>Suporte nativo para discos 4K:</h2>
A versão 6.7 do VMware vSphere agora suporta nativamente <a href="https://www.bit-tech.net/reviews/tech/storage/the-facts-4k-advanced-format-hard-disks/1/" target="_blank" rel="noopener">discos 4K</a>, uma feature muito útil para aqueles que querem usar os dispositivos de grande capacidade.

<img class="aligncenter size-large wp-image-4951" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/4k-adv-format-sectors-644x225.png" alt="" width="644" height="225" />

&nbsp;

Vou parar por aqui, mas já estou preparando novos posts com mais novidades sobre o VMware vSphere 6.7

O lab já está sendo preparado para receber a nova versão, então aguardem novidades.

Fique de olho na página <a href="http://homelaber.com.br/vmware-vsphere-6-7-links-e-informacoes/" target="_blank" rel="noopener">VMware vSphere 6.7 Links e Informações</a> aqui no blog, lá você vai encontrar tudo sobre o VMware vSphere 6.7

Deixe nos comentários, sua opinião sobre essa nova versão. Pelo que você viu até agora, faltou alguma coisa que você esperava não foi implementado? Te pegou de surpresa?