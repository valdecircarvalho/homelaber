---
ID: 2363
post_title: 'VMware vSphere 6.5 &#8211; Lançamento oficial'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2eh04rv
published: true
post_date: 2016-10-18 07:08:43
---
Olá Homelabers!

<em>Update 1</em> - O Pedro do blog Pedro Calixo fez um post bem bacana sobre o lançamento do vSphere 6.5. <a href="http://pedrocalixto.com/blog/2016/10/18/vsphere-6-5-e-anunciado-na-vmworld-barcelona/" target="_blank">Confira aqui</a>

Update 2 - O Thiago do Blog VMware Brasil fez uma série super completa sobre o lançamento do vSphere 6.5. <a href="http://vmwarebrasil.blogspot.com.br/2016/10/o-que-ha-de-novo-no-vsphere-65-vcsa.html" target="_blank">Confira aqui</a>

A nova versão do <strong>VMware vSphere 6.5</strong> foi oficialmente <strong>anunciada</strong> hoje na <strong>VMworld de Barcelona</strong>.

Vou destacar aqui algumas das novidades. Nos próximos dias pretendo fazer um review mais completo.

<img class="aligncenter wp-image-2373 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/introducing-vSphere-65.png" alt="introducing-vsphere-65" width="745" height="422" />

<!--more-->

<h3>Migration</h3>

<img class="aligncenter wp-image-2366" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-migration-300x171.png" alt="_vmware-vsphere-65-migration" width="800" height="456" />A migração para o vCSA (vCenter Server Appliance) ficou simples.

A ferramenta permite a migração de vCenter rodando em Windows para as versões 5.5 e 6.0

<h3>VMware Update Manager (VUM)</h3>

Agora o VMware Update Manager (VUM) é parte do vCenter Server Appliance, isso significa que não é mais necessário uma VM rodando apenas para fazer os updates.

<h3>Improved Appliance Management</h3>

<img class="aligncenter wp-image-2364" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-app-management-300x144.png" alt="_vmware-vsphere-65-app-management" width="800" height="384" />

Melhorias na interface de gerenciamento - A nova interface mostra informações de rede, estatísticas do banco de dados, espaço em disco, saúde do ambiente, cpu, memória em uma interface única, facilitando a monitoração e as tarefas operacionais

<h3><strong>Native High Availability</strong></h3>

<img class="aligncenter wp-image-2367" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-vcenterHA-300x118.png" alt="_vmware-vsphere-65-vcenterha" width="800" height="316" />

vCenter Server High Availability
A versão 6.5 apresenta uma nova feature nativa de alta disponibilidade (exclusiva do vCSA).
Agora o vCenter deixa de ser um ponto único de falha e tem integrado HA (Ativo, Passivo e Witness)

<h3><strong>Backup and Restore</strong></h3>

Nova funcionalidade interna de backup e restore para o vCSA.
Permite realizar backups e restore do vCenter Server Appliance (vCSA)

<h3><strong>vSphere Web Client</strong></h3>

<img class="aligncenter wp-image-2368" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-web-client-300x73.png" alt="_vmware-vsphere-65-web-client" width="800" height="194" />

Houveram melhorias na UI do vSphere Web Client, mas INFELIZMENTE continua baseada no Adobe Flex e Adobe Flash (Shame on you VMware).

<h3><strong>vSphere Client</strong></h3>

<img class="aligncenter wp-image-2365" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-h5-client-300x235.png" alt="_vmware-vsphere-65-h5-client" width="800" height="625" />

Foi totalmente redesenhado e é o que já vimos pelos Flings lançados anteriormente

É uma versão com HTML5 que vai rodar junto com o vSphere web client e essa versão está embutida no vCenter Server 6.5 Windows e vCSA

<img class="aligncenter wp-image-2370" src="http://homelaber.com.br/site/wp-content/uploads/2016/10/vmware-vsphere-65-VCSA-highlights-300x79.png" alt="_vmware-vsphere-65-vcsa-highlights" width="800" height="210" />

Mais informações aqui nos blogs oficiais:

<a href="http://blogs.vmware.com/vsphere/launch" target="_blank">http://blogs.vmware.com/vsphere/launch</a>

<a href="http://blogs.vmware.com/vsphere/2016/10/introducing-vsphere-6-5.html" target="_blank">http://blogs.vmware.com/vsphere/2016/10/introducing-vsphere-6-5.html</a>

<a href="http://blogs.vmware.com/vsphere/2016/10/whats-new-in-vsphere-6-5-vcenter-server.html" target="_blank">http://blogs.vmware.com/vsphere/2016/10/whats-new-in-vsphere-6-5-vcenter-server.html</a>

<a href="http://www.vmware.com/company/news/releases/vmw-newsfeed.VMware-Advances-Cross-Cloud-Architecture-with-New-Releases-of-vSphere,-Virtual-SAN-and-vRealize-Solutions-to-Drive-IT-and-Developer-Productivity.2104600.html" target="_blank">http://www.vmware.com/company/news/releases/vmw-newsfeed.VMware-Advances-Cross-Cloud-Architecture-with-New-Releases-of-vSphere,-Virtual-SAN-and-vRealize-Solutions-to-Drive-IT-and-Developer-Productivity.2104600.html</a>

&nbsp;

&nbsp;