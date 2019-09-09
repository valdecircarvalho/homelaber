---
ID: 711
post_title: 'AutoLab &#8211; O script que facilita o setup do seu HomeLab'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1L22XUy
published: true
post_date: 2015-11-06 20:59:01
---
Olá Homelabers!

Nesse post vou mostrar a vocês uma "coleção de scripts" que automatiza a criação de um lab VMware completo. Esse "produto" se chama <a href="http://www.labguides.com/autolab/" target="_blank">AutoLab</a> e foi criado pelo <a href="http://nickmarshall.com.au/about/" target="_blank">Nick Marshall</a> - autor dos melhores livros sobre VMware que eu já li até hoje - <a href="http://www.amazon.com/Mastering-VMware-vSphere-Nick-Marshall/dp/1118925157/ref=asap_bc?ie=UTF8" target="_blank">Mastering VMware vSphere 5.5</a> e  <a href="http://www.amazon.com/Mastering-VMware-vSphere-Scott-Lowe/dp/1118661141/ref=asap_bc?ie=UTF8" target="_blank">Mastering VMware vSphere 6</a> (assunto para um outro post).

<img class="aligncenter wp-image-883" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/logo-long-autolabs.png" alt="logo-long-autolabs" width="900" height="169" />

Com o AutoLab é possível subir um ambiente completo de VMware - ESXi, vCenter, etc em questão de 2 ou 3 horas e com um esfoço mínimo. É uma ferramenta excelente para a criação de um PoC (Prova de Conceito) onde se precisa subir um Lab para demostração de alguma feature do produto e depois destruí-lo.

<!--more-->

No site do AutoLab existe uma documentação super bem escrita e com todo o passo-a-passo para a instalação e deploy completo, links para download dos software necessários, etc.

O Autolab está disponível para ESXi, VMware Fusion (Mac) e VMware Workstation (Windows) e também para um serviço de núvem chamado <a href="https://www.ravellosystems.com/" target="_blank">Ravello</a> e o script instala as versões 5, 5.5 e 6.0 do vSphere. Na data de publicação desse post, o AutoLab está na versão 2.6

<img class="aligncenter size-full wp-image-884" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/AutoLab-color-leftside-72-dpi.png" alt="AutoLab-color-leftside-72-dpi" width="300" height="74" />

<blockquote><strong>Eu não recomendo usar o AutoLab para montar o seu primeiro laboratório ou o seu HomeLab</strong>, pois como ele automatiza o processo por inteiro, você acaba não aprendendo como realizar a instalação, não passa pelas dificuldades e não erra - <em><strong>errar é a melhor forma de aprender</strong></em>.</blockquote>

De qualquer maneira, sugiro que você teste o script, faça uma instalação e se necessário use no seu trabalho, na sua monografia - olha ai a idéia, fazer uma monografia sobre virtualização, etc. :)

Para baixar o Autolab, acesse o <a href="http://www.labguides.com/autolab/" target="_blank">link</a> e faça o seu registro. O projeto AutoLab é patrocinado pela empresa <a href="http://www.infinio.com/" target="_blank">Infinio</a> e seus dados serão repassados a eles - EU não vejo problema nisso, pois é uma troca, seu e-mail pelo AutoLab.

Após o registro, você será redirecionado para a página de <a href="http://www.labguides.com/autolab/autolab-download/?submissionGuid=0f0f0893-7dfd-4d36-b08e-6ece790f0191" target="_blank">Download</a>. A <strong>primeira coisa que você deve baixar</strong> é o <strong><a href="http://www.labguides.com/downloads/AutoLab%202.6%20vSphere%20Deployment%20Guide.pdf" target="_blank">Deployment Guide</a></strong>. Leia todo o documento - está em Inglês - e a partir dai comece a baixar os pacotes necessários. Preparação é a chave para o sucesso  8-O

Requisitos de Hardware:

Os requisitos de hardware para subir esse lab não são muito exigentes. A documentação fala em um Intel i7, mas eu acredito que deva subir e rodar (não espere aqueeeeela performance) em um Intel i5 e 16Gb RAM. Se você não tiver 16GB, tente subir em 8GB mesmo. Deve funcionar.

<table border="1" cellspacing="2" cellpadding="2">
<tbody>
<tr>
<td><strong>Hardware</strong></td>
<td><strong>Minimum</strong></td>
<td><strong>Great Choice</strong></td>
<td><strong>Used to build the lab</strong></td>
</tr>
<tr>
<td><strong>CPU</strong></td>
<td>Dual Core, 64Bit</td>
<td>Quad Core, i7</td>
<td>i7 Quad Core</td>
</tr>
<tr>
<td><strong>RAM</strong></td>
<td>16GB</td>
<td>How much can you afford?</td>
<td>32GB</td>
</tr>
<tr>
<td><strong>Hard Disk</strong></td>
<td>120GB free space</td>
<td>200GB SSD free space</td>
<td>240 GB SSD</td>
</tr>
<tr>
<td><strong>Operating System</strong></td>
<td>64 Bit</td>
<td>ESXi 5</td>
<td>Windows 7 64Bit</td>
</tr>
<tr>
<td><strong>Virtualization Software</strong></td>
<td>VMware Player (untested)</td>
<td>ESXi 5</td>
<td>VMware Workstation 10</td>
</tr>
</tbody>
</table>

Vamos lá... tente fazer a instalação do Autolab e volte aqui para deixar o seu comentário! Se conseguiu, se teve dificuldades. Compartilhe conosco o resultado.

Eu pretendo fazer um post sobre a instalação do Autolab em um futuro não muito distante.

Links:

<a href="https://www.facebook.com/labguides/" target="_blank">Facebook da LabGuides</a> - Acesse a página e deixe o seu joinha

<a href="https://twitter.com/nickmarshall9/" target="_blank">Twitter do Nick @nickmarshall9</a>

<a href="http://nickmarshall.com.au/" target="_blank">Blog do Nick Marshall</a>

<a href="http://www.labguides.com/autolab/" target="_blank">AutoLab</a>

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

&nbsp;