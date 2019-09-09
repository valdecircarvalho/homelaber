---
ID: 4678
post_title: 'Série Upgrade VMware ESXi &#8211; Parte 1 &#8211; Cenários de atualização'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2IS999s
published: true
post_date: 2018-03-26 15:00:01
---
Olá Homelabers,

Qual versão do VMware ESXi vocês estão rodando em seus ambientes de produção ou lab?

Eu já fiz um post há algum tempo sobre o <a href="http://homelaber.com.br/como-atualizar-vmware-vcenter-6-0-para-6-5/">upgrade do vCenter da versão 6.0 para 6.5</a> e você pode conferir esse post aqui. O upgrade foi bastante tranquilo e desta vez eu quero trazer a vocês uma série mostrando os cenários de upgrade do ESXi.

Lembrando que o <a href="http://homelaber.com.br/politica-de-cliclo-de-vida-dos-produtos-vmware-vmware-lifecycle-matrix/" target="_blank" rel="noopener">ESXi 5.5 está em sua fase final de suporte</a> - vai até Setembro/18 - então está mais do que na hora de começar a pensar e se preparar para fazer o upgrade o quanto antes.

Nesta série vou abordar <strong>3 cenários para a atualização do ESXi</strong>, acredito que esses são os cenários mais comuns para a nossa realidade, com destaque para o upgrade do vSphere 5.5 para vSphere 6.0.

Importante dizer que essa <strong>série vai cobrir apenas as formas de upgrade do ESXi</strong> e não vai cobrir o vCenter Server ok?

https://youtu.be/cveSppGBcsY
<h2>Cenários de Atualização:</h2>
<h3><strong>Cenário 1: Atualizando do vSphere 5.5 para vSphere 6.0</strong></h3>
<h3>Cenário 2: Atualizando do vSphere 5.5 para vSphere 6.5</h3>
<h3>Cenário 3: Atualizando do  vSphere 6.0 para vSphere 6.5</h3>
<h2>Dicas e Melhores Práticas para um upgrade sem Stress</h2>
<ul style="list-style-type: square;">
 	<li>Consulte a HCL (Hardware Compatibility List para se certificar que o seu hardware suporta a atualização</li>
 	<li>Leia o Release Note e a Documentação da versão escolhida</li>
 	<li>Consulte o VMware vSphere Upgrade Guide</li>
 	<li>Se for utilizar um ISO, lembre-se de baixar e testar antes de iniciar a janela. Pode parecer obvio mas…</li>
 	<li>Documente o seu ambiente atual, será mais fácil caso haja a necessidade de um rollback</li>
 	<li>Tenha em mãos a senha de root do ESXi</li>
 	<li>Atualize primeiro o vCenter</li>
 	<li>Você pode ter um ambiente com Hosts ESXi com versões diferentes</li>
</ul>
<h2>VMware vSphere 6.5 Upgrade eBook</h2>
Aproveito para deixar uma dica para vocês, o Emad Younis (@emad_younis) do time de engenharia do vSphere da VMware publicou um e-book com dicas, técnicas e recomendação para quem vai fazer upgrade para o vSphere 6.5

O e-book ficou super bacana e tem várias dicas legais e úteis que vou acabar usando nesse série de posts. Visite o<a href="http://emadyounis.com/upgrade/new-resource-vmware-vsphere-6-5-upgrade-ebook/" target="_blank" rel="noopener"> site do Emad</a> para baixar o e-book.

http://emadyounis.com/upgrade/new-resource-vmware-vsphere-6-5-upgrade-ebook/

Os vídeos da série já estão prontos, mas vou disponibilizá-los em doses para facilitar a vida de vocês :)

Deixe ai nos comentários a sua opinião. Devo cobrir outros cenários? Esses cenários atendem às suas necessidades?