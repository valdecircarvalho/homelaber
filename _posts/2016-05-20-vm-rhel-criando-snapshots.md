---
ID: 1587
post_title: 'VM RHEL &#8211; Criando Snapshots'
author: Alexandre Parreira
post_excerpt: ""
layout: post
permalink: http://bit.ly/1RdWwAO
published: true
post_date: 2016-05-20 17:09:02
---
<strong><img class="alignnone size-medium wp-image-1527" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/open-source-300x209.jpg" alt="ale-open-source" width="300" height="209" /></strong>

Olá Homelabers!

Vamos ver como criar Snapshots de nossa VM para termos pontos de restauração do estado da máquina em caso de problemas ou mesmo se estivermos testando novos componentes ou funcionalidades temporariamente.

<strong>Nível</strong>: <strong><span style="text-decoration: underline; color: #0000ff;">Fácil</span>.</strong>

<!--more-->

Este artigo se baseia na VM criada no artigo anterior da série:

<a href="http://homelaber.com.br/preparando-uma-vm-red-hat-enterprise-linux-para-desenvolvimento/">Preparando uma VM Red Hat Enterprise Linux para Desenvolvimento</a>.

Para criar Snapshots acessamos o menu VM &gt; Snapshot &gt; Take Snapshot.

<img class="alignnone wp-image-1588 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-snapshot-1.png" alt="ale-snapshot-1" width="771" height="343" />

Na passo seguinte fornecemos um nome e descrição. É importante dar um nome e descrição detalhados para nos lembramos o melhor possível do estado da VM e a finalidade do Snapshot. Por vezes trabalhamos por um bom tempo no ambiente e é possível esquecer o estado do snapshot e o impacto de se retornar a este snapshot.

<img class="alignnone wp-image-1589 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-snapshot-2.png" alt="ale-snapshot-2" width="360" height="227" />

Clique em <em><strong>Take a Snapshot</strong></em>.

Para visualizar e voltar a um Snapshot específico acesse <em><strong>VM &gt; Snapshot &gt; Snapshot Manager</strong></em>.

<img class="alignnone wp-image-1591 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-snapshot-3.png" alt="ale-snapshot-3" width="670" height="515" />

Agora podemos virar do avesso a instalação e fazer diversos testes que estamos seguros para retornar o ambiente ao estado original.

Por fim sempre podemos descartar Snapshots passados para liberar espeaço em disco.

Basta clicar com o botão direito no Snapshot e selecionar Delete.

Um abraço! Paz e sucesso a todos!

<strong>Fim</strong>.

&nbsp;