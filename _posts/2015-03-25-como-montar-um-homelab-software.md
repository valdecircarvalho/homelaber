---
ID: 114
post_title: 'Como montar um Homelab &#8211; Software'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1HsHnbR
published: true
post_date: 2015-03-25 09:00:08
---
Olá Homelabers! Nesse post vou falar sobre algumas das maneiras de se conseguir o software para o seu HomeLab.

<blockquote>
<p style="text-align: center;">Hardware é o que você chuta! Software é o que você xinga</p>
</blockquote>

<p style="text-align: left;">Primeiro você entendeu <a title="Porque ter um HomeLab?" href="http://homelaber.com.br/porque-ter-um-homelab/">por que ter um Homelab VMware em sua casa</a>, depois você <a title="Como montar um HomeLab – Hardware" href="http://homelaber.com.br/como-montar-um-homelab-o-hardware/">escolheu o Hardware</a> e agora é a vez do Software.</p>

Basicamente, existem 3 maneiras de você conseguir software para o seu Homelab. Sendo que por software vou considerar o Hypervisor e o Sistema Operacional para as VMs que irão rodar no seu lab.

<ul>
    <li>Comprando</li>
    <li>Software de avaliação</li>
    <li>Software Free/OpenSource</li>
</ul>

<!--more-->

<strong>Comprando o seu Software</strong>

Já estou imaginando a nuvenzinha na sua cabeça: - Esse cara é louco. Ele acha que sou rico para comprar o software para rodar no meu HomeLab? Está maluco!

Não é bem assim. A maioria dos fabricantes dispõe de programas para profissionais por um preço bastante atraente. A Microsoft por exemplo, possui o programa MSDN, onde você pagando um valor anual, tem direito a “todos” os softwares para avaliação e laboratório.

Para softwares da VMware, existem 2 opções: o programa <a title="vEXPERT" href="https://communities.vmware.com/community/vmtn/vexpert" target="_blank">vEXPERT</a> e o <a title="VMUG Advantage" href="http://www.vmug.com/Advantage" target="_blank">VMUG:Advantage</a> (depois eu falo mais sobre esses dois programas). De qualquer maneira, a grande vantagem em comprar o software para seu HomeLab é ter suporte do fabricante e não precisar ficar remontando/reinstalando o seu lab sempre que o período de avaliação expirar.

<strong>Software de Avaliação</strong>

Todos os fabricantes tem disponível em seus sites downloads de versões de avaliação de seus softwares. Essas versões costumam não ter limitações e funcionam por geralmente 60 dias (esse periodo pode ser extendido em alguns casos e variam de fornecedor para fornecedor).

A grande desvantagem é ter de reinstalar o lab sempre que o período de avaliação expirar. Costumo utilizar as versões de avaliação para aqueles softwares que sei que não vou utilizar por um longo tempo ou que irei apenas fazer um teste rápido.

<strong>Software Free/OpenSource</strong>

Alguns fabricantes dispõe de versões free de seus softwares mas com algumas limitações. A VMware por exemplo, disponibiliza a versão freeware do ESXi (hypervisor) mas sem as principais funções de vMotion, HA, etc.

Existem diversas outras opções de virtualizadores que são Free, inclusive para uso comercial - como não existe almoço grátis, a pegadinha aqui é que você tem de pagar o suporte anual que costuma ser bastante caro - que podem ser instalados no seu lab sem a necessidade de reinstalação e/ou renovação de licença. O foco desse blog é falar de produtos VMware, mas pretendo fazer alguns posts sobre Hyper-V, <a href="http://xenserver.org/open-source-virtualization-download.html" target="_blank">Oracle VM</a>, <a href="http://xenserver.org/open-source-virtualization-download.html" target="_blank">XEN Server</a>, etc.

<strong>BONUS</strong>: Existe uma outra opção para você conseguir softwares para seu Homelab. Se você já trabalha na área e tem contato com o gerente de contas do que atende a sua empresa, converse com ele sobre o seu projeto de HomeLab (aproveite para mostrar esse blog hahaha) e peça para ele te fornecer uma licença para uso exclusivo no seu lab. Não é 100% de certesa que você vai conseguir, mas vale tentar. Eu já consegui alguns trials “eternos” de fornecedores camaradas por ai!

<blockquote><span style="color: #808080;">PS - Não citei e não citarei nenhum link de pirataria nesse blog. Por favor, não solicitem. Peço que não me julguem como falso moralista, mas esse espaço é meu e essas são as minhas regras. Tenho bons motivos para seguir com essa diretriz. Eu, você, o fabricante, enfim, todo mundo sabe como e onde conseguir softwares e licenças piratas pela infernet, mas esse não é o lugar. Obrigado.</span></blockquote>

Links para download:

<strong>Microsoft</strong>

<p style="text-align: center;"><img class="aligncenter size-medium wp-image-208" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/TechNet-Evaluation-Center-300x176.jpg" alt="TechNet Evaluation Center" width="300" height="176" /></p>

<pre><strong>Programa Microsoft TechNet Evaluation Center</strong> ou <strong>MSDN Evaluation Center</strong> 
Versões de avaliação por 180 dias
<a href="http://bit.ly/MicrosoftTechNetEvalCenter">http://bit.ly/MicrosoftTechNetEvalCenter</a> ou <a href="https://msdn.microsoft.com/pt-br/evalcenter/default.aspx">http://bit.ly/MSDNEvalCenter
</a>Necessita registro (grátis)</pre>

<strong>VMware</strong>

<p style="text-align: center;"><img class="aligncenter size-medium wp-image-209" src="http://homelaber.com.br/site/wp-content/uploads/2015/03/Evaluate-and-Download-VMware-Products-for-a-Virtual-Infrastructure-VMware-300x146.jpg" alt="Evaluate and Download VMware Products for a Virtual Infrastructure - VMware" width="300" height="146" /></p>

<pre><strong>Download direto do site da VMware</strong> 
Versão de avaliação por 60 dias
Produtos VMware - Trial - <a href="http://bit.ly/tryvmware">http://bit.ly/tryvmware</a> | ESXi 6.0 Free - <a href="http://bit.ly/dlvmwareesxifree">http://bit.ly/dlvmwareesxifree</a> | vCloud Suite 5.5 - Trial - <a href="http://bit.ly/dlvmware55">http://bit.ly/dlvmware55</a>
Necessita registro (grátis)</pre>

No proximo post da série vou começar com a instalação do VMware ESXi 5.5 que será a base do seu Homelab.

É isso Homelabers! Fico por aqui e espero que vocês tenham gostado. Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado com as novidades do blog.

VC