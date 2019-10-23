---
ID: 5890
post_title: 'Chololatey &#8211; Um gerenciador e instalador de programas para Windows'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2MDC4lI
published: true
post_date: 2019-10-23 07:00:29
---
Olá Homelabers!

Como vocês fazem para instalar seus programas e softwares prediletos em um computador novo ou recém instalado?

Hoje vou falar sobre o software <a href="https://chocolatey.org/" target="_blank" rel="noopener noreferrer">Chololatey</a>, um gerenciador e instalador de programas para Microsoft Windows.
<h2>O que é o Chocolatey?</h2>
O Chocolatey não é um produto novo, mas muita gente ainda não conhece ou se conhece não utiliza e a ideia desse post é mostrar para vocês como ele pode ser útil no seu dia a dia.

Eu confesso que por muito tempo, torci o nariz para o uso do Chocolatey, mas depois de ler bastante a documentação, vez muita gente usando e principalmente confiar inteiramente no Homebrew do MacOS, mudei minha opinião.

<img class="aligncenter size-large wp-image-5899" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/chocolate-feature-800x400-644x322.png" alt="" width="644" height="322" />Pense no Chocolatey como um <strong>apt-get</strong> ou <strong>yum</strong> do Linux ou<strong> <a href="https://brew.sh/index_pt-br" target="_blank" rel="noopener noreferrer">Homebrew</a></strong> do MacOS para Windows. Com o Chocolatey, você conseguirá <strong>instalar, atualizar e atualizar</strong> programas no Windows através da <strong>linha de comando ou scripts</strong>.

O Chocolatey é um software open source (licença <a href="https://github.com/chocolatey/choco/blob/master/LICENSE" target="_blank" rel="noopener noreferrer">Apache 2</a>) e está disponível em 3 versões:
<ul style="list-style-type: square;">
 	<li>Open Source - <strong>uso pessoal e corporativo</strong>, sem custos e limites</li>
 	<li>Pro - <strong>uso pessoa</strong>l em até 8 computadores pago anualmente.</li>
 	<li>Business (C4B) - <strong>uso empresarial</strong> pago por computador</li>
</ul>
As vantagens e o comparativo de cada versão e sua licença podem ser encontradas nesse <a href="https://chocolatey.org/compare" target="_blank" rel="noopener noreferrer">link</a>, mas basicamente com a versão paga você passa a ter acesso ao suporte, uma console central de gerenciamento, auditoria, cache, pacotes verificados, etc.
<h2>Uso corporativo</h2>
Bacana, gostei... mas eu posso utilizar o Chocolatey na minha empresa ou nos meus clientes?

<strong>A resposta é sim!</strong> Por ser um software open source você pode utilizar o Chocolatey na sua empresa ou nos seus clientes, mas o recomendado é que você utilize a versão <strong>Business</strong> onde você paga um valor anual por computador e tem todas as features da versão open source com o foco em segurança, produtividade e visibilidade (<a href="https://chocolatey.org/products#chocolatey-for-business" target="_blank" rel="noopener noreferrer">mais informações sobre a versão business aqui</a>).

Considerando o baixo valor de investimento, ganho em tempo mo gerenciamento de software e comprado com uma solução mais robusta como o Microsoft System Center, se você cuida do TI de uma empresa pequena, acredito ser um excelente investimento.
<h2>Mas e a segurança?</h2>
Como disse mais acima, eu sempre torci o nariz para o Chocolatey, principalmente para uso empresarial.

Você está instalando um software empacotado por alguém que você não conhece (a comunidade) na sua rede corporativa (seus preciosos dados). De cara existe um gap de segurança muito grande ai certo?

Pois então, pesquisando mais a fundo para escrever esse post, fui ler as <a href="https://github.com/chocolatey/choco/wiki/Security" target="_blank" rel="noopener noreferrer">políticas de segurança publicada na wiki do Chocolatey</a> (e recomendo que você também faça isso) e deu para perceber que eles levam esse assunto muito a sério. Os pacotes - mesmo os da comunidade - passam por um processo de review e moderação e são checados por antivirus para dizer o mínimo. Então minhas recomendações sobre segurança são:
<ul style="list-style-type: square;">
 	<li><strong>Se você é uma empresa PAGUE pelo software</strong> e tenha segurança e suporte. Pense no tempo economizado para instalar e principalmente atualizar os softwares.</li>
 	<li>Utilize apenas <strong>pacotes revisados e aprovados </strong>(bolinha verde)</li>
 	<li><strong>Leia as informações do pacote</strong> que irá instalar.</li>
 	<li><strong>Leia os comentários</strong></li>
 	<li><strong>Teste</strong> antes em um <strong>ambiente isolado e controlado</strong>.</li>
</ul>
Mas no final do dia, estamos CONFIANDO nos pacotes gerados e mantidos pela comunidade. Da mesma forma que confiamos em rodar um apt-get install no Ubuntu ou brew install no Mac.
<h2>No passado era assim...</h2>
No passado para instalar um software qualquer para Windows, a maneira mais comum era o famoso <strong>NNF - Next &gt;&gt; Next &gt;&gt; Finish</strong> e pronto, seu software estava instalado. Mas desse modo, você precisa estar obrigatoriamente na frente do computador, não pode estar fazendo mais nada e as opções de automatização são praticamente zero.

<img class="aligncenter wp-image-5901 size-medium" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/chocolatey-next-next-finish-300x221.jpg" alt="" width="300" height="221" />

Com o uso de ferramentas de gerenciamento de pacotes, você passa a ter possibilidade de <strong>automatizar, criar scripts para instalação, atualização e remoção de pacotes (programas)</strong>, ou seja, um mundo totalmente novo para usuários Windows.
<h2>Como instalar o Chocolatey</h2>
A instalação do Chocolatey é bastante simples e pode ser feitas de diversas maneiras. Aqui vou mostrar como eu usei no meu PC, via CMD.

Os requisitos mínimos para rodar o Chocolatey são:
<ul style="list-style-type: square;">
 	<li>Windows 7/Windows Server 2003 ou superior</li>
 	<li>Powershell v2 ou superior (não funciona com Powershell Core ainda)</li>
 	<li>.NET Framework 4 ou superior – se você não tiver instalado, o Chocolatey instala para você.</li>
</ul>
<ol>
 	<li>Abra o prompt de comando do Windows (CMD) com acesso administrativo</li>
 	<li>Execute o comando: <code>@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" &amp;&amp; SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"</code></li>
 	<li>Feito! Simples assim. A partir de agora, você já pode começar a utilizar o Chocolatey em seu computador.</li>
</ol>
Para consultar outras formas de instalar o Chocolatey no seu computador consulte a <a href="https://chocolatey.org/docs/installation" target="_blank" rel="noopener noreferrer">documentação oficial</a>
<h2>Como usar o Chocolatey</h2>
Após a instalação chegou a hora de botar a mão na massa e utilizar o Chocolatey.
O primeiro comando que você deverá usar é o <code>choco -? | more</code> que vai mostrar o help do programa e seus principais comandos.

<code>choco install "nome do pacote"</code>  Instala um programa ou pacote. Use a flag -y para não pedir confirmação

<img class="aligncenter size-large wp-image-5902" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/choco_install-644x436.gif" alt="" width="644" height="436" />

<code>choco search</code>  Lista/busca os pacotes existentes no repositório. Use a flag --local-only para listar apenas os pacotes instalados em seu sistema via Chocolatey

<img class="aligncenter size-large wp-image-5903" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/choco_search-644x436.gif" alt="" width="644" height="436" />

<code>choco uninstall "nome do pacote"</code> Remove ou desinstala um pacote previamente instalado.

<img class="aligncenter size-large wp-image-5904" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/choco_uninstall-644x436.gif" alt="" width="644" height="436" />

<code>choco upgrade "nome do pacote"</code> --&gt; Atualiza um pacote previamente instalado. Use a flag all para atualizar todos os pacotes.

<img class="aligncenter size-large wp-image-5905" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/choco_upgrade-644x436.gif" alt="" width="644" height="436" />
<h2>Pacotes</h2>
Os pacotes ou packages são de fato os programas que serão instalados em seu computador utilizando o Chocolatey. Cada pacote contém as instruções codificadas para a instalação, atualização e remoção do programa.

No site https://chocolatey.org/packages você encontrará um extenso catálogo com todos os pacotes disponíveis para instalação, assim como os comandos para instalar, atualizar e remover e ainda o status de cada pacote, o responsável pela verificação e certificação do pacote e outras informações úteis.

<img class="aligncenter size-large wp-image-5907" src="http://homelaber.com.br/site/wp-content/uploads/2019/10/chocolatey-pacotes-644x314.png" alt="" width="644" height="314" />

Você poderá fazer pesquisas pelo nome do software que precisa, filtrar por categoria, popularidade, status etc.
<h2>Como eu uso o Chocolatey</h2>
O meu uso do Chocolatey é basicamente em casa e no lab.

Eu procuro instalar todos os softwares do meu PC através do Chocolatey, facilitando assim, principalmente o upgrade/update dos softwares e sempre que possível utilizando scripts.

Aqui você poderá ver um exemplo de um script em Powershell para instalar automaticamente vários softwares utilizando o Chocolatey

https://gist.github.com/valdecircarvalho/a9c41dd716820d669fc278afd7049f29
<h2>Alternativas ao Chocolatey</h2>
Existem algumas outras soluções de gerenciamento de pacotes para Microsoft Windows, mas pelo que pesquisei, nenhuma é tão robusta, sólida e madura quanto o Chocolatey. Vou deixar aqui algumas opções, mas deixo claro que ainda não cheguei a testar pessoalmente nenhuma delas.
<ul style="list-style-type: square;">
 	<li>Scoop - <a href="https://scoop.sh/" target="_blank" rel="noopener noreferrer">https://scoop.sh/</a></li>
 	<li>Just-Install - <a href="https://just-install.github.io/" target="_blank" rel="noopener noreferrer">https://just-install.github.io/</a></li>
 	<li>Appget - <a href="https://appget.net/" target="_blank" rel="noopener noreferrer">https://appget.net/</a></li>
</ul>
Se você conhece e/ou usa alguma das ferramentas acima ou alguma outra que deixei de fora, deixei sua opinião nos comentários no meu Twitter
<h2>O que mais pode ser feito?</h2>
O céu e sua imaginação são o limite. Após conhecer e testar o feijão-com-arroz do Chocolatey que é a instalação/atualização/remoção de softwares, você pode passar a olhar a ferramenta com outros olhos.
<ul style="list-style-type: square;">
 	<li>Automatize o processo de deploy de suas máquinas com scripts</li>
 	<li>Automatize o upgrade do seu parque com tarefas do windows ou psexec</li>
 	<li>Crie um repositório interno com os softwares homologados para sua empresa</li>
 	<li>Automatize o processo de instalação do seu ambiente de DevOps com suas ferramentas preferidas</li>
 	<li>Explore as opções de <a href="https://chocolatey.org/docs/features-infrastructure-automation" target="_blank" rel="noopener noreferrer">integração com ferramentas de gerenciamento de configuração</a> como Ansible, Chef, Puppet, etc.</li>
 	<li>Aprenda a <a href="https://chocolatey.org/docs/create-packages" target="_blank" rel="noopener noreferrer">criar pacotes</a> com aquele software especifico que só a sua empresa usa</li>
</ul>
Recursos:

No site do Chocolatey, você irá encontrar diversos recursos disponíveis para seguir com seus estudos sobre a ferramenta.
<ul style="list-style-type: square;">
 	<li>Documentação oficial - <a href="https://chocolatey.org/docs" target="_blank" rel="noopener noreferrer">https://chocolatey.org/docs</a></li>
 	<li>Wiki - <a href="https://github.com/chocolatey/choco/wiki" target="_blank" rel="noopener noreferrer">https://github.com/chocolatey/choco/wiki</a></li>
 	<li>Github - <a href="https://github.com/chocolatey/choco" target="_blank" rel="noopener noreferrer">https://github.com/chocolatey/choco</a></li>
 	<li>Cursos - <a href="https://chocolatey.org/courses" target="_blank" rel="noopener noreferrer">https://chocolatey.org/courses</a></li>
 	<li>Estudo de casos - <a href="https://chocolatey.org/resources" target="_blank" rel="noopener noreferrer">https://chocolatey.org/resources</a></li>
 	<li>Pacotes - <a href="https://chocolatey.org/packages" target="_blank" rel="noopener noreferrer">https://chocolatey.org/packages</a></li>
 	<li>Reddit - <a href="https://www.reddit.com/r/chocolatey/" target="_blank" rel="noopener noreferrer">https://www.reddit.com/r/chocolatey/</a></li>
 	<li>Twitter - <a href="https://twitter.com/chocolateynuget" target="_blank" rel="noopener noreferrer">https://twitter.com/chocolateynuget</a></li>
 	<li>Canal Youtube - <a href="https://www.youtube.com/chocolateysoftware" target="_blank" rel="noopener noreferrer">https://www.youtube.com/chocolateysoftware</a></li>
</ul>
E por ser uma ferramenta já bastante sólida, você irá encontrar muitas informações e artigos pela internet.
<h2>Considerações finais</h2>
Recentemente eu migrei do MacOS para o Windows e tive que fazer o setup do meu novo computador (mais sobre isso em outro post onde vou contar sobre a migração). A primeira coisa que eu fiz, foi tentar automatizar ao máximo o processo para evitar ter que fazer tudo manualmente e acabei resgatando e olhando com mais carinho para o Chocolatey - que me ajudou muito no processo.

Para pessoas comuns e pequenas empresas, acredito que seja uma excelente opção de gerenciamento de software - principalmente para instalações e updades/upgrades - por facilita muito o processo de setup de uma nova máquina e na minha visão é bem melhor do que usar imagens.

Para empresas grandes, mesmo a versão Enterprise não vejo muito como uma solução a ser adotada - existem vários cases - por diversos fatores, principalmente porque esse é um terreno já dominado pelo Microsoft System Center.

Eu já entrei em contato com o pessoal Chocolatey pedindo uma licença NFR da versão Business para testar no lab, estudar e escrever um artigo, vamos ver no que vai dar!

Se você já usa o Chocolatey em casa, na sua empresa ou nos seus clientes, deixe nos comentários a sua opinião, quero muito saber como outras pessoas estão usando o produto.

Até a próxima!