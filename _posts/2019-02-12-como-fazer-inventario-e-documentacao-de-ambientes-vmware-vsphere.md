---
ID: 5382
post_title: >
  Como fazer inventário e documentação
  de ambientes VMware vSphere
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2tjbx2I
published: true
post_date: 2019-02-12 08:00:51
---
Olá Homelabers,

<em><strong>Update: 12/02</strong> - Adicionado o conjunto de scripts As Built Report (@AsBuiltReport) by Tim Carman (@tpcarman) - dica do @arielsanchezmor</em>

<strong>Update: 29/10</strong> - <em>Adicionado novos links do As Built Report</em>

Quem nunca assumiu um ambiente que não estava bem documentado e precisou fazer um levantamento completo de todos os componentes desse ambiente desconhecido? Ou mesmo descuidou um pouco da documentação do seu ambiente e agora precisa atualizar?

Hoje, vou mostrar algumas ferramentas e scripts free, criados pela comunidade para que você possa fazer o inventário e documentação de qualquer ambiente VMware.
<h3>vDocumentation - @arielzanchezmor &amp; @edmsanchez13</h3>
<a href="https://github.com/arielsanchezmora/vDocumentation" target="_blank" rel="noopener noreferrer">https://github.com/arielsanchezmora/vDocumentation</a>

Esse set de scripts em Powershell + PowerCLI foram criados pelo Ariel Sanchez e Edgar Sanchez, que produz uma série de informações em formato csv ou excel, da sua infraestrutura vSphere para que você possa conhecer e documentar o seu ambiente.

<img class="aligncenter size-large wp-image-5388" src="http://homelaber.com.br/site/wp-content/uploads/2019/02/vDocumentation-644x200.jpg" alt="" width="644" height="200" />

Informações que podem ser obtidas com os scripts:
<table>
<thead>
<tr>
<th>Comando</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Get-ESXInventory</strong></td>
<td>Informações de hardware e configuração do host</td>
</tr>
<tr>
<td><strong>Get-ESXIODevice</strong></td>
<td>Informações de HBAs, NICs e outros dispositivos PCIe, incluindo PCI IDs, MACs, firmware e drivers</td>
</tr>
<tr>
<td><strong>Get-ESXNetworking</strong></td>
<td>Informações de rede como NICs, vSwitches, VMKernel</td>
</tr>
<tr>
<td><strong>Get-ESXStorage</strong></td>
<td>Informações de configuração de storage como detalhes de iSCSI, FibreChannel, Datastores &amp; Multipathing</td>
</tr>
<tr>
<td><strong>Get-ESXPatching</strong></td>
<td>Informações relativas aos patches instalados e pendentes, incluindo informações dos KBs.</td>
</tr>
<tr>
<td><strong>Get-vSANInfo</strong></td>
<td>Informações relacionadas ao cluster vSAN</td>
</tr>
<tr>
<td><strong>Get-ESXSpeculativeExecution</strong></td>
<td>Informações referentes ao Spectre and Meltdown nos hosts</td>
</tr>
<tr>
<td><strong>Get-VMSpeculativeExecution</strong></td>
<td>Informações referentes ao Spectre and Meltdown nas VMs</td>
</tr>
</tbody>
</table>
Para maiores informações sobre como utilizar os scripts, acesse <a href="https://github.com/arielsanchezmora/vDocumentation" target="_blank" rel="noopener noreferrer">https://github.com/arielsanchezmora/vDocumentation</a> e leia a documentação.
<h3>RVTools - @rvtools</h3>
<a href="https://www.robware.net/rvtools/" target="_blank" rel="noopener noreferrer">www.robware.net/rvtools/</a>

Eu já falei do RVTools algumas vezes aqui no blog e reforço que o RVTools é uma ferramenta obrigatória para todo administrador de ambiente vSphere.

<img class="aligncenter size-large wp-image-2583" src="http://homelaber.com.br/site/wp-content/uploads/2017/03/rvtools_info-1024x366.jpg" alt="" width="644" height="230" />

Com o RVTools - uma pequena aplicação para windows - você tem facilmente acesso todas as informações do seu ambiente vSphere. Você pode conectar em um host ESXi ou ao seu vCenter.

A ferramenta mostra informações de VMs, Memória, Disco, Snapshots, Datastores, VMware Tools e muito muito mais.

O RVTools é free e para usar, basta fazer o download no link abaixo e instalar no seu sistema. Mais informações sobre o RVTools <a href="https://www.robware.net/rvtools/" target="_blank" rel="noopener noreferrer">aqui</a>

RVTools <a class="ow-icon-placement-left ow-button-hover" href="https://www.robware.net/rvtools/download/">Download</a> | RVTools <a href="http://robware.net/download/RVTools.pdf" target="_blank" rel="noopener noreferrer">Documentação</a>
<h3>vCheck Daily Report for vSphere - @alanrenouf</h3>
<a href="https://github.com/alanrenouf/vCheck-vSphere" target="_blank" rel="noopener noreferrer">https://github.com/alanrenouf/vCheck-vSphere</a>

O vCheck Daily Report é mais um conjunto de scripts Powershell + PowerCLI criados inicialmente pelo Alan Renouf e mantido pela comunidade.

<img class="aligncenter size-large wp-image-5386" src="http://homelaber.com.br/site/wp-content/uploads/2019/02/vCheck-644x360.jpeg" alt="vCheck" width="644" height="360" />

A idéia por trás do vCheck Daily Report (vCDR) é que você deixe esses scripts executando diariamente no seu ambiente e receba um e-mail pela manhã (ou quando for mais conveniente para você) com um status do seu ambiente formatado bonitinho e que você pode até encaminhar para o chefe :)

Mas nada impede, de usar esses scripts para gerar uma documentação/inventário inicial do seu ambiente e você pode customizar exatamente quais informações receber/extrair.

Dentre várias informações trazidas pelo script, destaco:
<ul>
 	<li>Number of Active VMs</li>
 	<li>Number of Inactive VMs</li>
 	<li>Number of DRS Migrations for the last days</li>
 	<li>Snapshots over x Days old</li>
 	<li>Datastores with less than x% free space</li>
 	<li>VMs created over the last x days</li>
 	<li>VMs removed over the last x days</li>
 	<li>VMs with No Tools</li>
</ul>
A documentação do vCheck Daily Report é bastante completa e detalhada.

Para maiores informações sobre como utilizar os scripts, acesse <a href="https://github.com/alanrenouf/vCheck-vSphere" target="_blank" rel="noopener noreferrer">https://github.com/alanrenouf/vCheck-vSphere</a> e leia a documentação.
<h3>VMware vSphere As Built Report - @tpcarman @AsBuiltReport</h3>
Update - O As Built Report agora tem um site e um novo repositório no Github

<a href="https://github.com/AsBuiltReport" target="_blank" rel="noopener noreferrer">https://github.com/AsBuiltReport</a>

<a href="https://www.asbuiltreport.com/" target="_blank" rel="noopener noreferrer">As Build Report Home</a>

O As <a href="https://www.timcarman.net/as-built-report/" target="_blank" rel="noopener noreferrer">Built Report</a> (@AsBuiltReport) foi criado Tim Carman (@tpcarman) e é um conjunto de scripts em PowerShell e PScribo para gerar e construir documentação nos formatos HTML, XML, Texto e MS Word.

O conjunto de scripts gera um relatório bastante completo do seu ambiente vSphere com informações de Host, vCenter, Clusters, VMs, Datastore, Rede, Licenciamento, vSAN, NSX, etc.

<img class="aligncenter size-large wp-image-5404" src="http://homelaber.com.br/site/wp-content/uploads/2019/02/vSphere-As-Built-SampleReport-644x596.png" alt="" width="644" height="596" />

O As Built Report tem o seu código aberto e publicado no Github, ou seja, você pode customizá-lo para atender suas necessidades.

Para maiores informações sobre como utilizar o As Built Report, consulte a <a href="https://www.timcarman.net/as-built-report/" target="_blank" rel="noopener noreferrer">documentação no site do autor</a> ou no GitHub. BONUS: Vídeo no Youtube da apresentação do Tim na VMworld 2018
<ul>
 	<li><a href="https://github.com/tpcarman/As-Built-Report/tree/master/Reports/vSphere" target="_blank" rel="noopener noreferrer">https://github.com/tpcarman/As-Built-Report/tree/master/Reports/vSphere</a></li>
 	<li><a href="https://www.timcarman.net/2018/08/20/documenting-your-datacentre-infrastructure-with-powershell/" target="_blank" rel="noopener noreferrer">https://www.timcarman.net/2018/08/20/documenting-your-datacentre-infrastructure-with-powershell/</a></li>
 	<li><a href="https://www.youtube.com/watch?v=aQqHSEIUHl8&amp;feature=youtu.be&amp;t=1988" target="_blank" rel="noopener noreferrer">https://www.youtube.com/watch?v=aQqHSEIUHl8&amp;feature=youtu.be&amp;t=1988</a></li>
</ul>
<h3>Mas qual é o melhor?</h3>
Não existe uma ferramenta melhor ou pior, tudo vai depender das suas necessidades e quais informações você precisa, mas certamente, ter esses scripts no seu vBat-Cinto-De-Utilidades vai te ajudar bastante, seja no seu ambiente do dia a dia ou seja para fazer um levantamento em um novo ambiente.

Conhece outra ferramenta ou scripts? Deixe nos comentários para que eu possa atualizar o post!

Até a próxima!

&nbsp;