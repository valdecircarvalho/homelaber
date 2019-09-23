---
ID: 28
post_title: Meu Homelab
author: Valdecir Carvalho
post_excerpt: ""
layout: page
permalink: http://homelaber.com.br/meu-homelab/
published: true
post_date: 2015-03-07 13:18:50
---
<p style="text-align: left;">Olá HomeLabers!</p>
<p style="text-align: left;">Muitos me perguntam o que eu tenho de equipamento rodando no meu lab e aqui está a resposta.</p>

<h1 style="text-align: center;">Homelab 2018</h1>
<img class="alignright wp-image-4337 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/equipamentos-homelab-homelaber-01.jpg" alt="" width="1920" height="1080" />
<h2>Um pouco de história.</h2>
Eu comecei com um lab de VMware vSphere rodando em um notebook e ao longo do tempo fui comprando, trocando e conseguindo uma tonelada de equipamentos, já tive quase que um datacenter em casa - servidor de rack, storage, etc - mas o consumo de energia era proibitivo para deixar ligado 24X7 e o calor e ruído eram excessivos e causava um incômodo desnecessário.

Fiz um downgrade e o equipamento que tenho hoje atendem plenamente aos meus requisitos:
<ul style="list-style-type: square;">
 	<li>Custo acessível</li>
 	<li>Baixo ruído</li>
 	<li>Baixo consumo de energia</li>
 	<li>Potência - poder de processamento.</li>
</ul>
<h2>Equipamento:</h2>
Hoje o meu lab é composto de 3 Hosts vSphere, sendo um servidor "Enterprise" e dois "Desk Servers" e também um Switch Layer 3.

<strong>HPE ML 110 G9</strong> - falei sobre esse servidor <a href="http://homelaber.com.br/novo-homelab-para-2017-hpe-ml-110-g9/">aqui</a>
Intel(R) Xeon(R) CPU E5-1603 v3 @ 2.80GHz
64GB RAM
2X HD 2.0 TB
2X SSD 256 GB

<strong>Lenovo M92p</strong>
Intel(R) Core(TM) i7-3770 CPU @ 3.40GHz
32GB RAM
1X HD 2.5 TB
1X SSD 256 GB

<strong>Lenovo M92p</strong>
Intel(R) Core(TM) i7-3770 CPU @ 3.40GHz
28GB RAM
1X HD 1.5 TB
1X SSD 256 GB

<strong>Switch Cisco SG500X-24 24-Port Gigabit</strong>

Esse é um switch Cisco da linha Small Business, que atende perfeitamente o meu Lab para tudo o que eu quiser fazer. <a href="https://www.cisco.com/c/en/us/support/switches/sg500x-24-24-port-gigabit-4-port-10-gigabit-stackable-managed-switch/model.html" target="_blank" rel="noopener noreferrer">Link para o datasheet</a>

<img class="alignright wp-image-4338 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/equipamentos-homelab-homelaber-02.jpg" alt="" width="1920" height="1080" />
<h2>Arquitetura do Lab</h2>
Não vou postar aqui uma arquitetura do lab, pois ela está sempre mudando, mas basicamente esses equipamentos estão atrás do modem da minha operadora e rodando em uma rede (VLAN) isolada do resto da rede da minha casa.
<h2>Software</h2>
A base do meu lab é o VMware ESXi. Em cima dele consigo rodar praticamente qualquer workload que eu desejar, até mesmo outros hypervisors utilizando Nested Virtualization.

Tenho acesso a todo o portfólio de produtos VMware através do programa <a href="http://homelaber.com.br/category/vexpert/" target="_blank" rel="noopener noreferrer">VMware vExpert</a> e também do <a href="http://homelaber.com.br/como-obter-licencas-full-dos-produtos-vmware/" target="_blank" rel="noopener noreferrer">VMUG Advantange</a>. Então #ficaadica

Felizmente, por causa do vExpert, acabo tendo acesso a licenças NFR (Not For Resale) de vários outros fabricantes, como Veeam, Vembu, Zerto, Nutanix, etc.

Os software que não tenho acesso NFR - no caso de produtos Microsoft - acabo utilizando uma assinatura MSDN que eu tenho - e está acabando - ou ainda em Trial Mode.

<a href="https://www.vmug.com/VMUG-Join/VMUG-Advantage"><img class="aligncenter size-large wp-image-4510" src="http://homelaber.com.br/site/wp-content/uploads/2018/02/HOMELAB-POWERED-BY-VMUG-ADVANTAGE-644x540.png" alt="" width="644" height="540" /></a>
<h2 style="text-align: left;">Lab dos Sonhos</h2>
SE eu tivesse grana para investir em um lab dos sonhos, HOJE ele seria assim:
<ul style="list-style-type: square;">
 	<li>3 Hosts <a href="https://www.supermicro.com/products/system/Mini-ITX/SYS-E300-8D.cfm" target="_blank" rel="noopener noreferrer">SuperMicro SYS-E300-8D</a> com 128GB de RAM com 1X SSD 1TB + 1 SSD 512 GB em cada (All Flash baby!!)</li>
 	<li>1 Intel <a href="https://www.intel.com/content/www/us/en/nuc/nuc-kit-nuc6i7kyk-brief.html" target="_blank" rel="noopener noreferrer">NUC SKULL (NUC6i7KYK)</a> com 32Gb e SSD 512GB</li>
 	<li>1 Switch 10GB <a href="https://www.netgear.com/business/products/switches/smart/XS708T.aspx" target="_blank" rel="noopener noreferrer">Netgear XS708T-100NES</a> (8 portas 10GB)</li>
 	<li>1 Switch Cisco L3 24 portas (um 2960 já estaria de bom tamanho ou um ainda menor)</li>
 	<li>1 NAS <a href="https://www.synology.com/en-us/products/DS1517+" target="_blank" rel="noopener noreferrer">Synology DS1517</a>+ com interface 10GB</li>
</ul>
Tudo isso dentro de um Rack pequenininho para caber embaixo da minha mesa :)

Deixe ai nos comentários, qual é o seu lab e qual é o seu lab dos sonhos!
<h2>Fotos</h2>
[su_slider source="media: 4347,4346,4345,4344,4343" link="lightbox" width="960" height="600" title="no"]