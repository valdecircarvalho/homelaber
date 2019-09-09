---
ID: 1327
post_title: 'Back-to-Basics: Diferenças entre tipos de disco em uma VM (Thin vs Thick Provision)'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/26qG0Zt
published: true
post_date: 2016-04-26 06:00:54
---
<div class="su-box-title">Olá Homelabers!</div>

<div class="su-box-title"></div>

<div class="su-box-title">Hoje vou começar uma série de artigos chamada Back-To-Basics (ou De volta ao básico em bom Português). Nessa série vou escreve sobre aspectos básicos referente a virtualização. Geralmente serão posts curtos, explicando o conceito de uma determinada tecnologia;</div>

<div class="su-box-title"></div>

<div class="su-box-title">No artigo de hoje, vou esclarecer diferença entre: Thick Provision vs Thin Provision</div>

<div class="su-box-title"></div>

<div class="su-box-title"><img class="aligncenter size-full wp-image-1333" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/thin-vs-thick.jpg" alt="thin-vs-thick" width="640" height="335" /></div>

<div class="su-box-title"></div>

<!--more-->

<div class="su-box-title">Em resumo:</div>

<div class="su-box-content su-clearfix">

<b>Thick Provision Lazy Zeroed </b>– é um disco “thick” padrão, ou seja, <i>todo o espaço é alocado no momento da sua criação</i>. Neste formato de disco virtual, qualquer dado que exista no dispositivo físico é mantido no momento da criação, e só são “zerados” no momento em que a máquina virtual vai escrevendo seus dados.

<b>Thick Provision Eager Zeroed</b> – é um disco “thick” que possui suporte a alguns recursos de cluster, como FT. Também aloca todo o espaço necessário no momento da sua criação. A diferença para o formato “lazy” (ou flat) é que os dados existentes no dispositivo físico são todos zerados no momento da criação. O tempo de criação deste tipo de disco pode demorar mais que os demais.

<b>Thin Provision</b> – neste tipo de disco <i>apenas um espaço mínimo é utilizado no momento da sua criação</i>. A medida que mais espaço físico for sendo necessário, o disco “thin” vai aumentando o seu tamanho, podendo chegar até o tamanho alocado inicialmente.

Na imagem abaixo, podemos ver e entender com facilidade a diferença entre Thick Provisioning e Thin Provisioning

[caption id="attachment_1331" align="aligncenter" width="800"]<img class="wp-image-1331 size-full" title="diferença entre Thick Provisioning e Thin Provisioning" src="http://homelaber.com.br/site/wp-content/uploads/2016/04/Diferenças-entre-tipos-de-disco-em-uma-VM-Thin-vs-Thick-Provision-e1461636326617.png" alt="Diferenças entre tipos de disco em uma VM Thin vs Thick Provision" width="800" height="358" /> <strong>Diferença entre Thick Provisioning e Thin Provisioning</strong>[/caption]

Portanto, se você tem pouco espaço em disco no seu lab, o caminho a seguir é sempre usar Thin Provision. Mas o esquema (mesmo em produção) é sempre ficar de olho na utilização e monitorar o crescimento de suas VMs.

No meu trabalho, todas as VMs que utilizamos, são criadas como Thin Provision e temos um monitoramento super bacana e em cima, para não termos surpresas.

Na minha opinião (totalmente pessoal), trabalhar com Thick Provision é a mesma coisa que trabalhar com storage no século passado. Você vai lá, compra discos projetando um crescimento de 3 anos e aloca disco para cada servidor. Mesmo se o servidor em questão não utilize aquele espaço provisionado, o disco já foi alocado, desperdiçando disco. Com o Thin Provision, você "tecnicamente economiza disco".

Outro ponto importante: PERFORMANCE. Eu li dezenas de artigos (vou deixar os links aqui no post) sobre isso e no final não consegui chegar a nenhuma conclusão. Uns dizem que disco Thin Provision é mais performático do que disco Thick, outros dizem o contrário. Aqui, o que vale é testar no seu ambiente para tomar a decisão.

É isso ai.. Vou deixar alguns links, onde vocês podem pesquisar mais informações (todos em Inglês).

Até a próxima pessoal!

Links:

<a href="http://www.vmware.com/br/products/vsphere/features/storage-thin-provisioning" target="_blank">http://www.vmware.com/br/products/vsphere/features/storage-thin-provisioning</a>

<a href="http://pubs.vmware.com/vsphere-60/topic/com.vmware.ICbase/PDF/vsphere-esxi-vcenter-server-60-storage-guide.pdf" target="_blank">http://pubs.vmware.com/vsphere-60/topic/com.vmware.ICbase/PDF/vsphere-esxi-vcenter-server-60-storage-guide.pdf</a>

<a href="http://blogs.vmware.com/vsphere/2012/03/thin-provisioning-whats-the-scoop.html" target="_blank">http://blogs.vmware.com/vsphere/2012/03/thin-provisioning-whats-the-scoop.html</a>

<a href="https://www.vmware.com/pdf/vsp_4_thinprov_perf.pdf" target="_blank">https://www.vmware.com/pdf/vsp_4_thinprov_perf.pdf</a>

<a href="http://www.storagecraft.com/blog/virtualization-thin-provisioning-better/" target="_blank">http://www.storagecraft.com/blog/virtualization-thin-provisioning-better/</a>

<a href="http://www.storagecraft.com/blog/top-3-limitations-thin-provisioning/" target="_blank">http://www.storagecraft.com/blog/top-3-limitations-thin-provisioning/</a>

<a href="http://www.techrepublic.com/blog/the-enterprise-cloud/what-is-thin-provisioning/" target="_blank">http://www.techrepublic.com/blog/the-enterprise-cloud/what-is-thin-provisioning/</a>

</div>