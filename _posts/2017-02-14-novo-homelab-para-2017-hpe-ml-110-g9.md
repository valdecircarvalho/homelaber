---
ID: 2495
post_title: 'Novo Homelab para 2017 &#8211; HPE ML 110 G9'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2lbgzvm
published: true
post_date: 2017-02-14 07:00:05
---
Olá Homelabers!!

Quem acompanha o blog há algum tempo, deve ter visto que no <a href="http://homelaber.com.br/homelab-movel-thinkpad-w510/" target="_blank" rel="noopener">começo do ano passado</a> eu consegui um Laptop para usar como lab remoto. Um Lenovo Thinkpad W510 Intel Core i7 com 32GB de RAM, 2 SSDs, etc, etc. Um maquinão que eu acabei usando pouco. No final de novembro pintou uma oportunidade de vendê-lo e com a grana da venda e mais uns trocados, consegui comprar um servidor novinho para o meu lab.

<img class="size-medium wp-image-2532 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2017/02/hp-proliant-ml110-gen9-server_09rb__34880.1449015387.1280.1280-154x300.png" alt="" width="154" height="300" /> Depois de muito pesquisar acabei optando pelo <strong>HPE ProLiant ML110 G9</strong>
<ul style="list-style-type: square;">
 	<li>Intel® Xeon® <strong>E5-1600 v3</strong></li>
 	<li><strong>64GB RAM</strong> (non-ECC) - <a href="https://www.corsair.com/pt/pt/Categorias/Produtos/Mem%C3%B3ria/Mem%C3%B3ria-tradicional/Corsair-Memory-%E2%80%94-16GB-%281x16GB%29-DDR4-2133MHz-CL15-DIMM/p/CMV16GX4M1A2133C15" target="_blank" rel="noopener">Corsair DDR4 (4X pentes de 16GB)</a></li>
 	<li>2X HDs 2TB 7200 RPM</li>
 	<li>2X SSD 256GB</li>
 	<li><del>1X HD 1TB 10K RPM</del></li>
</ul>
Em breve, pretendo fazer um upgrade no meu servidor para deixa-lo com 128GB de RAM e 2X SSDs 500GB, mas por enquanto ele está me servindo MUITO BEM!

Todas as especificações desse servidor podem ser vistas <a href="https://www.hpe.com/br/pt/product-catalog/servers/proliant-servers/pip-404.html" target="_blank" rel="noopener">aqui</a>. Na configuração padrão ele vem com 8GB e 1X HD de 1TB.

Estou gostando bastante da performance desse servidor. A primeiro momento pode parecer um pouco overkill para um lab, mas para rodar NSX com menos de 64GB fica bastante complicado.

<!--more-->Como disse, eu pesquisei bastante antes de fazer a compra. Hoje os 3 maiores players (Dell, HPE e Lenovo) oferecem servidores de entrada e com basicamente as mesmas especificações (8GB RAM e 1X HD 1TB) e entre eles, o HPE ML110 G9 foi o que mais se destacou. Veja porque:

Meus pré-requistos eram:
<ul style="list-style-type: square;">
 	<li>Suportar pelo menos 256GB de RAM</li>
 	<li>Suportar memória NON-ECC</li>
 	<li>Suportar mínimo de 4 discos</li>
 	<li>Baixo consumo de energia</li>
 	<li>Silencioso</li>
 	<li>Torre</li>
 	<li>Processador Xeon mais novo possível</li>
 	<li>Mínimo de 64GB de RAM</li>
 	<li>Budget R$5000,00</li>
</ul>
<h3>Servidores Candidatos:</h3>
<a href="http://www.dell.com/br/empresa/p/poweredge-t130/pd?oc=ent-bpt130iibpt3&amp;model_id=poweredge-t130" target="_blank" rel="noopener"><img class="size-full wp-image-2538 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2017/02/dell-logo.jpg" alt="" width="150" height="50" /></a>

&nbsp;

&nbsp;
<h4><a href="http://www.dell.com/br/empresa/p/poweredge-t130/pd?oc=ent-bpt130iibpt3&amp;model_id=poweredge-t130" target="_blank" rel="noopener">Dell PowerEdge T130</a></h4>
Essa máquina tem um processador <a href="http://ark.intel.com/PT-BR/products/88172/Intel-Xeon-Processor-E3-1220-v5-8M-Cache-3_00-GHz" target="_blank" rel="noopener">Intel® Xeon® Processor E3-1220 v5</a> (2015) e suporta no máximo 64GB de memória RAM

<img class="size-full wp-image-2540 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2017/02/lenovo-logo.png" alt="" width="150" height="50" />

&nbsp;

&nbsp;
<h4><a href="http://shop.lenovo.com/br/pt/servers/thinkserver/towers/ts140/" target="_blank" rel="noopener">Lenovo ThinkServer TS140</a></h4>
Essa máquina tem um processador <a href="http://ark.intel.com/Pt-Br/products/75052/Intel-Xeon-Processor-E3-1220-v3-8M-Cache-3_10-GHz" target="_blank" rel="noopener">Intel® Xeon® E3-1200 v3</a> que é antigo (2013) e suporta no máximo de 32GB de memória RAM.

<img class="size-full wp-image-2539 alignleft" src="http://homelaber.com.br/site/wp-content/uploads/2017/02/hpe-logo.png" alt="" width="150" height="50" />

&nbsp;

&nbsp;
<h4><a href="https://www.hpe.com/br/pt/product-catalog/servers/proliant-servers/pip-404.html" target="_blank" rel="noopener">HPE ProLiant ML110 G9</a></h4>
Essa máquina tem um processador <a href="http://ark.intel.com/pt-br/products/82761/Intel-Xeon-Processor-E5-1603-v3-10M-Cache-2_80-GHz" target="_blank" rel="noopener">Intel® Xeon® E5-1600 v3</a> (2014) e suporta no máximo 256GB de memória RAM, ou seja, perfeito para o que eu preciso e o que me garante bastante espaço para upgrades.
<h3>Valores:</h3>
Falando de valores, esses servidores são bastante acessíveis em sua <strong>configuração básica</strong> (8GB RAM) e o seu preço varia <strong>em torno</strong> de <strong>R$2500,00 e R$3000,00</strong>. Você consegue encontrar esses servidores em todos os maiores sites de e-commerce e também no Mercado Livre. Eu paguei nessa configuração pouco mais de R$4500,00 em uma loja de Campinas (SP) que recomendo, pois os caras foram muito atenciosos. Vou deixar o contato deles aqui embaixo, procure pelo Rodrigo Caseiro.

Depois que eu comprei esse servidor, mais dois amigos aqui do blog e vExperts (Fernando Silva @vmnetbrasil do <a href="http://vmnetbrasil.com.br/" target="_blank" rel="noopener">VMNetBrasil</a> e Ricardo Conzatti @ricardoconzatti do <a href="http://solutions4crowds.com.br/" target="_blank" rel="noopener">Solutions4Crowds</a>) também acabaram comprando e pelo que tenho conversado com eles, estão bastante satisfeitos. Se vocês não acreditam em mim, conversem com eles :)
<h3>Considerações finais:</h3>
<ul style="list-style-type: square;">
 	<li>Esse servidor não faz barulho nenhum. O meu switch faz mais barulho do que ele.</li>
 	<li>Ele fica ligado 24X7 e não notei nenhum aumento significativo na conta de luz</li>
 	<li>Montar ou Comprar novo - HOJE eu acho mais vantagem comprar um novo, você tem garantia, sabe que vai funcionar, não precisa ficar correndo atrás de peças E pelas contas que eu fiz, acaba saindo mais barato! Mas pesquise antes!</li>
</ul>
Até mais pessoal! Se você quiser saber mais alguma informação sobre o servidor que eu não coloquei aqui, escreva nos comentários.
<p class="">[su_box title="TNT INFO" box_color="#fffb82" title_color="#000000"]<a href="http://www.tntinfoloja.com.br/" target="_blank" rel="noopener">http://www.tntinfoloja.com.br/</a>
Rodrigo Caseiro
(19) 98239-5449 (Oi) / (19) 3307-5263 (Fixo)
rdgcaseiro@gmail.com / tntinfo@tntinfo.com.br[/su_box]</p>