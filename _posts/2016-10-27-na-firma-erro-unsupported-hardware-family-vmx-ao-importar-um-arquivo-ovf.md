---
ID: 2418
post_title: 'Na FIRMA &#8211; Erro: Unsupported hardware family vmx ao importar um arquivo .OVF'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2dOovev
published: true
post_date: 2016-10-27 08:00:01
---
Olá Homelabers!

No post de hoje vou contar uma situação que enfrentei na <strong>FIRMA</strong> e como resolvi o problema. Acredito que isso possa ser útil para muita gente. Então vamos lá:

Hoje a tarde recebi um fornecedor que iria fazer um deploy de uma VM com um software para uma PoC (Prova de Conceito ou Proof of Concept em Inglês). Ele me trouxe um HD com o o OVF, os discos, etc. Até ai tudo fácil e normal. Fazer deploy de OVF é fácil.

Quando comecei a importação do OVF, tomei o seguinte erro:

<blockquote><strong>This OVF package uses features that are not supported. </strong><strong>The OVF package requires unsupported hardware. Details: Line 31: Unsupported hardware family 'vmx-11'.</strong></blockquote>

<img class="aligncenter wp-image-2419 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/2016-10-25-19_07_02-Deploy-OVF-Template.png" alt="This OVF package uses features that are not supported. The OVF package requires unsupported hardware. Details: Line 31: Unsupported hardware family 'vmx-11'" width="469" height="236" />

<h2 style="text-align: center;">Unsupported hardware family vmx- during OVF import</h2>

Logo suspeitei que fosse a <strong>versão do ESXi que a VM foi exportada</strong>. Fui consultar a<a href="https://kb.vmware.com/selfservice/microsites/microsite.do" target="_blank"><strong> base de KB's da VMware</strong></a> e encontrei um <a href="https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&amp;cmd=displayKC&amp;externalId=1003746" target="_blank">artigo</a> explicando as <strong>versões de hardware de uma VM</strong> - <strong>Virtual machine hardware versions (1003746)</strong> e nesse artigo descobri que a familia vmx-11 se refere a VMs criadas no ESXi 6.x. Como o meu ambiente lá na FIRMA roda em ESXi 5.5 matei o problema na hora.

Agora tinha que descobrir como converter um OVF criado na versão 6.x para a versão 5.5 do VMware ESXi. Mais uma vez com a ajudinha do Google, <a href="http://www.running-system.com/unsupported-hardware-family-vmx-10-during-ovf-import/" target="_blank">encontrei um artigo no Running-System.com</a> de Julho de 2015 que ensinava a converter um OVF da familia vmx-10. Tentei o mesmo procedimento e deu certo. Vou reproduzir aqui para vocês o que eu fiz.

<img class="aligncenter wp-image-2426 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/troubleshooting.jpg" alt="troubleshooting" width="512" height="391" />

<!--more-->

<strong>1. Editar o arquivo .OVF para trocar a versão do hardware</strong>

<ul style="list-style-type: square;">
    <li>Faça uma cópia do arquivo .ovf</li>
    <li>Abra o arquivo e edite a seguinte linha:
<em>&lt;VirtualHardwareSection&gt;</em>
<em> &lt;Info&gt;Virtual hardware requirements&lt;/Info&gt;</em>
<em> &lt;System&gt;</em>
<em> &lt;vssd:ElementName&gt;Virtual Hardware FamilyElementName&gt;</em>
<em> &lt;vssd:InstanceID&gt;0InstanceID&gt;</em>
<em> &lt;vssd:VirtualSystemIdentifier&gt;OracleBigDataDiscovery1.2VirtualSystemIdentifier&gt;</em>
<em> &lt;vssd:VirtualSystemType&gt;<strong>vmx-11</strong>&lt;/vssd:VirtualSystemType&gt;</em>
<em> &lt;/System&gt;</em></li>
    <li>Troque o <strong>vmx-11</strong> por <strong>vmx-10</strong> que é a família da VM do ESXi 5.5</li>
    <li>Salve o arquivo e "reserve".</li>
</ul>

<img class="aligncenter wp-image-2421" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/2016-10-26_00-08-09-300x203.png" alt="2016-10-26_00-08-09" width="800" height="542" />

<ol>
<li>Editar o arquivo .mf e trocar o hash que representa o arquivo .ovf O hash desse arquivo usa SHA-1</li>
</ol>

<ul style="list-style-type: square;">
    <li>Acessar o site <a href="http://onlinemd5.com/" target="_blank">http://onlinemd5.com/</a></li>
</ul>

<img class="aligncenter wp-image-2423" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/2016-10-26_00-46-04-300x134.png" alt="2016-10-26_00-46-04" width="800" height="358" />

<ul style="list-style-type: square;">
    <li>Carregar o arquivo <strong>.ovf alterado</strong></li>
    <li>Calcular o <strong>valor do hash SHA-1</strong></li>
    <li>Trocar o <strong>hash do arquivo antigo</strong> para <strong>hash do arquivo editado</strong></li>
    <li>Salvar o arquivo .mf</li>
</ul>

<img class="aligncenter wp-image-2422 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/2016-10-26_00-12-52.png" alt="2016-10-26_00-12-52" width="655" height="427" />

&nbsp;

Após isso, é só voltar a fazer o deploy do .ovf normalmente no ESXi e pronto. Vai passar liso!

<table style="width: 557px;" cellspacing="0" cellpadding="0">
<tbody>
<tr style="height: 38.5627px;">
<td style="width: 259.319px; height: 38.5627px; text-align: center;"><strong>Virtual Hardware Version</strong></td>
<td style="width: 300.681px; height: 38.5627px; text-align: center;"><strong>Products</strong></td>
</tr>
<tr style="height: 70px;">
<td style="width: 259.319px; height: 70px; text-align: center;">12</td>
<td style="width: 300.681px; height: 70px;">Fusion 8.x
Workstation Pro 12.x
Workstation Player 12.x</td>
</tr>
<tr style="height: 93px;">
<td style="width: 259.319px; height: 93px; text-align: center;">11</td>
<td style="width: 300.681px; height: 93px;">Fusion 7.x
Workstation 11.x
Player 7.x
<strong>ESXi 6.x</strong></td>
</tr>
<tr style="height: 93px;">
<td style="width: 259.319px; height: 93px; text-align: center;">10</td>
<td style="width: 300.681px; height: 93px;"><strong>ESXi 5.5</strong>
Fusion 6.x
Workstation 10.x
Player 6.x</td>
</tr>
<tr style="height: 93px;">
<td style="width: 259.319px; height: 93px; text-align: center;">9</td>
<td style="width: 300.681px; height: 93px;">ESXi 5.1
Fusion 5.x
Workstation 9.x
Player 5.x</td>
</tr>
<tr style="height: 93px;">
<td style="width: 259.319px; height: 93px; text-align: center;">8</td>
<td style="width: 300.681px; height: 93px;">ESXi 5.0
Fusion 4.x
Workstation 8.x
Player 4.x</td>
</tr>
<tr style="height: 163px;">
<td style="width: 259.319px; height: 163px; text-align: center;">7</td>
<td style="width: 300.681px; height: 163px;">ESXi/ESX 4.x
Fusion 3.x
Fusion 2.x
Workstation 7.x
Workstation 6.5.x
Player 3.x
Server 2.x</td>
</tr>
<tr style="height: 23px;">
<td style="width: 259.319px; height: 23px; text-align: center;">6</td>
<td style="width: 300.681px; height: 23px;">Workstation 6.0.x</td>
</tr>
<tr style="height: 93px;">
<td style="width: 259.319px; height: 93px; text-align: center;">4</td>
<td style="width: 300.681px; height: 93px;">ACE 2.x
ESX 3.x
Fusion 1.x
Player 2.x</td>
</tr>
<tr style="height: 140px;">
<td style="width: 259.319px; height: 140px; text-align: center;">3 and 4</td>
<td style="width: 300.681px; height: 140px;">ACE 1.x
Lab Manager 2.x
Player 1.x
Server 1.x
Workstation 5.x
Workstation 4.x</td>
</tr>
<tr style="height: 46px;">
<td style="width: 259.319px; height: 46px; text-align: center;">3</td>
<td style="width: 300.681px; height: 46px;">ESX 2.x
GSX Server 3.x</td>
</tr>
</tbody>
</table>

Uma informação importante: <strong>A VM não vai ligar se vc utilizar uma versão de VM acima do ambiente instalado. Ex. O ESXi 6 vai rodar uma VM criada no ESXi 5.X, mas o contrário não é verdade.</strong>

É isso ai pessoal! Até a próxima!

VC