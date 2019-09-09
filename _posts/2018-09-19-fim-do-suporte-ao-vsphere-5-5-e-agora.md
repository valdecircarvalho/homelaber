---
ID: 5206
post_title: Fim do suporte ao vSphere 5.5 e agora?
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2DdidHd
published: true
post_date: 2018-09-19 07:00:15
---
Olá Homelabers!

Hoje, dia <strong>19/09/2018</strong> marca a data do <strong>fim do suporte a versão 5.5 do VMware vSphere</strong>  mas e agora?

Se você ainda não fez o upgrade do seu ambiente 5.5 para outras versões como 6.0, 6.5 ou 6.7, não precisa ficar MUITO preocupado.
<h2>E agora?</h2>
<img class="aligncenter size-large wp-image-5214" src="http://homelaber.com.br/site/wp-content/uploads/2018/09/yeaaaahhhh-were-going-to-need-to-upgrade-644x346.jpg" alt="" width="644" height="346" />

O seu ambiente não vai parar, suas VMs continuarão funcionando normalmente e tecnicamente nada muda. O único ponto é que se você precisar de suporte, não vai conseguir ajuda da GSS (Global Support Services).

<img class="aligncenter size-large wp-image-5224" src="http://homelaber.com.br/site/wp-content/uploads/2018/09/VMware-vsphere-55-technical_guidance-644x119.png" alt="" width="644" height="119" />

<strong>Editado: 19/09 - 16:00 - O texto abaixo foi adicionado ao post para complementar as informações escritas por mim anteriormente.</strong> Fonte: <a href="https://blogs.vmware.com/vsphere/2018/09/end-of-general-support.html" target="_blank" rel="noopener">https://blogs.vmware.com/vsphere/2018/09/end-of-general-support.html</a>
<h2>A realidade do suporte ao vSphere 5.5</h2>
Os engenheiros de suporte são humanos, assim como nossos clientes, e há limitações para o conhecimento que uma equipe de técnicos pode manter em suas fileiras.

O vSphere 5.5 foi lançado em 2013 e, desde então, foram lançados mais três grandes lançamentos do produto. Muitos engenheiros de suporte entraram na era do 6.x e o volume do vSphere 5.5 tem diminuído constantemente durante os anos. Isso significa que pode ser difícil e demorado responder perguntas complexas sobre a linha de produtos 5.5. Além disso, quando o vSphere 6.x foi lançado, ele mudou bastante o jogo em termos de arquitetura e técnicas de solução de problemas. Isso é muito importante para o suporte a que se acostumam a ver quando ajudam os clientes e, à medida que o volume de casos do vSphere 5.5 diminui, o mesmo acontece com o conhecimento geral do suporte.
<blockquote>É importante saber que, se você estiver fazendo upgrade do vSphere 5.5, o suporte da VMware ainda estará aqui para ajudar caso ocorra algum problema. Estamos preparados para lidar com os casos de Orientação Técnica que entram, mas torna-se mais difícil fazê-lo à medida que nos aprofundamos no período de Orientação Técnica - e as perguntas levam mais tempo para serem respondidas.</blockquote>
<h2>Orientação Técnica (Technical Guidance)</h2>
Primeiro, vamos esclarecer um equívoco comum sobre orientação técnica. Especificamente, isso <strong>não significa que o produto se torne imediatamente sem suporte</strong>. Eu ouço essa palavra muito usada para produtos fora da fase de suporte geral, mas é enganoso fazê-lo. O suporte VMware ainda ajudará no caso de um problema em um ambiente executando esses produtos. Há, no entanto, algumas limitações sérias para até onde isso vai agora que está fora do Suporte Geral. Muitas vezes, esses casos acabam exigindo uma atualização de qualquer maneira.

<strong>Fim do update</strong>
<h2>Contrato de Suporte:</h2>
Se você <strong>tem um Contrato de Suporte Válido</strong> mas por qualquer motivo ainda está rodando a versão 5.5 no seu ambiente, o que vai acontecer é que em caso de algum problema, a VMware não irá mais suportar o seu ambiente, o suporte será feito na base do melhor esforço e o suporte irá apenas apontar KBs existentes, mas você ainda poderá fazer o upgrade posteriormente.

Se você ainda <strong>não migrou e tem o suporte válido</strong>, planeje e <strong>execute a migração o quanto antes</strong>, para não correr riscos com um sistema sem suporte.

Se você <strong>NÃO tem um Contrato de Suporte Válido</strong> e quer fazer o upgrade, será necessário legalizar o seu ambiente, adquirindo uma nova licença + suporte e ainda pagar o retroativo do tempo que você ficou sem suporte.

Veja a informação descrita no site da VMware:
<blockquote>Caso você não consiga fazer a atualização antes do Fim do Suporte Geral (EOGS) e estiver ativo no Suporte e na Assinatura, você terá a opção de comprar o suporte estendido em incrementos de um ano por até dois anos além da data do EOGS. Visite o <a href="https://www.vmware.com/support/services/extended.html" target="_blank" rel="noopener">VMware Extended Support</a> para mais informações.

A <strong>orientação técnica para o vSphere 5.5 está disponível até 19 de setembro de 2020</strong>, principalmente por meio do portal de autoajuda. Durante a fase de Orientação Técnica, a VMware não oferece suporte a novo hardware, atualizações do sistema operacional do servidor / cliente / guests, novos patches de segurança ou correções de bugs, a menos que observado de outra forma. Para obter mais informações, visite as <a href="https://www.vmware.com/support/policies/lifecycle.html" target="_blank" rel="noopener">Fases de suporte do ciclo de vida do VMware</a>.</blockquote>
<h2>Lista de produtos que alcançam o Fim do Suporte Geral em 2018</h2>
E não é só o vSphere 5.5 que tem o fim do suporte hoje, veja abaixo a lista de outros produtos afetados.

<img class="aligncenter size-full wp-image-5216" src="http://homelaber.com.br/site/wp-content/uploads/2018/09/contagem.gif" alt="" width="480" height="320" />
<ul>
 	<li>AirWatch Console 9.1</li>
 	<li>AirWatch Learn 1.0</li>
 	<li>AirWatch Teach 1.0</li>
 	<li>AirWatch Video for Android and iOS 1.0</li>
 	<li>AppVolumes 2.11, 2.12 and 3.0</li>
 	<li><strong>Cisco Nexus 1000V</strong></li>
 	<li><strong>ESXi 5.5</strong></li>
 	<li>Horizon DaaS Bundle and Horizon DaaS On Prem Platform 6.1</li>
 	<li>Identity Manager 2.9</li>
 	<li>Integrated OpenStack 3.0 and 3.1</li>
 	<li>Mirage 5.8</li>
 	<li>NSX for vSphere 6.2</li>
 	<li>NSX-T 1.0 and 1.1</li>
 	<li>SDDC Manager 2.0, 2.1 and 2.2</li>
 	<li>Site Recovery Manager 5.5 and 5.8</li>
 	<li>User Environment Manager 9.0 and 9.1</li>
 	<li><strong>vCenter Server 5.5</strong></li>
 	<li>vCenter Server Heartbeat 6.6</li>
 	<li><strong>vCenter Update Manager 5.5</strong></li>
 	<li>vCloud Availability for vCloud Director 1.0</li>
 	<li>vCloud Director for Service Providers 8.10</li>
 	<li>vCloud Usage Meter 3.5.0, 3.6.0 and 3.6.1</li>
 	<li>vRealize Automation 6.2.5 Standard/Advanced/Enterprise</li>
 	<li>vRealize Automation DevKit 6.2.2</li>
 	<li>vRealize Automation 7.0, 7.1 and 7.2</li>
 	<li>vRealize Business for Cloud 7.0, 7.1 and 7.2</li>
 	<li>vRealize Code Stream 2.0, 2.1, 2.2 and 2.3</li>
 	<li>vRealize Hyperic 5.8.4 through 5.8.6</li>
 	<li>vRealize Log Insight 4.0, 4.3, and 4.5</li>
 	<li>vRealize Network Insight 3.0 through 3.6</li>
 	<li>vRealize Operations for Horizon 6.4</li>
 	<li>vRealize Operations for Published Applications 6.1 and 6.4</li>
 	<li>vRealize Operations Manager 6.3, 6.4, and 6.5</li>
 	<li>vRealize Orchestrator 7.0, 7.1, 7.2, and 7.3</li>
 	<li><strong>vSAN 5.5</strong></li>
 	<li>vSphere Big Data Extensions 2.3</li>
 	<li><strong>vSphere Data Protection 5.5 and 5.8</strong></li>
 	<li>vSphere Data Protection Advanced 5.5 and 5.8</li>
 	<li>vSphere Integrated Containers 1.x</li>
 	<li>vSphere Replication 5.5, 5.6 and 5.8</li>
 	<li>vSphere Storage Appliance 5.5</li>
</ul>
Para mais informações, consulte a <a href="https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/support/product-lifecycle-matrix.pdf" target="_blank" rel="noopener"><strong>Matrix de Ciclo de Vida dos Produtos VMware</strong></a> e <a href="http://homelaber.com.br/politica-de-cliclo-de-vida-dos-produtos-vmware-vmware-lifecycle-matrix/" target="_blank" rel="noopener">leia esse post</a> que eu publiquei aqui no blog, onde explico todo o ciclo de vida dos produtos VMware.

https://twitter.com/VMware/status/1042482976045637632

&nbsp;

Deixe nos comentários como está a sua situação. Você já migrou seu ambiente? Está migrando? Não vai migrar?

&nbsp;