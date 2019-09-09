---
ID: 574
post_title: >
  Como instalar VMware Tools em um
  servidor ESXi (nested)
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1OTwM1C
published: true
post_date: 2015-05-04 09:00:03
---
Olá Homelabers!

Neste post vamos instalar o VMware Tools em um servidor ESXi.

Uma instalação "nested" é quando você instalar um virtualizador em cima de outro virtualizador, ou seja,  instalar o VMware ESXi como uma VM de um outro servidor ESXi. Vale lembrar que <strong>essa função não é suportada pela VMware</strong> e deve ser utilizada <strong>somente em laboratório</strong>, <strong>NUNCA em produção</strong>.

<img class="aligncenter size-full wp-image-578" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/nested-esxi.png" alt="" width="520" height="366" />

<!--more-->

<blockquote><em><b>Visão geral do VMware Tools (fonte: <a href="http://vmw.re/1I19cdH" target="_blank">http://vmw.re/1I19cdH</a>)</b></em>

<em>O VMware Tools é um conjunto de utilitários que melhora o desempenho da máquina virtual do sistema operacional convidado e aprimora o gerenciamento da máquina virtual. Sem o VMware Tools instalado no sistema operacional convidado, o desempenho do sistema convidado pode sofrer com a falta de funcionalidades importantes. A instalação do VMware Tools elimina ou soluciona os seguintes problemas:</em>
<ul type="disc">
    <li><em>Baixa resolução de vídeo</em></li>
    <li><em>Profundidade de cor inadequada</em></li>
    <li><em>Exibição da velocidade de rede incorreta</em></li>
    <li><em>Movimento limitado do mouse</em></li>
    <li><em>Incapacidade de copiar, colar, arrastar e soltar arquivos</em></li>
    <li><em>Som ausente</em></li>
</ul>
</blockquote>

Instalar o VMware Tools em um servidor ESXi irá facilitar bastante o gerenciamento do seu home lab.

Então vamos lá:

A primeira coisa que você deve fazer é configurar o seu servidor ESXi para aceitar conexões via SSH, para isso vá até a aba "Configuration".

<img class="aligncenter wp-image-586" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-13-38.png" alt="2015-05-01_20-13-38" width="800" height="432" />

Depois clique em "Properties..."

<img class="aligncenter wp-image-594" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-14-00.png" alt="2015-05-01_20-14-00" width="800" height="432" />

Na tela "Service Properties" verifique se o serviço SSH está"Running". Se estiver, basta voltar para a tela anterior.

<img class="aligncenter size-full wp-image-595" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-14-13.png" alt="2015-05-01_20-14-13" width="658" height="694" />

Caso contrário, clique em "Options..." e selecione a opção "Start and stop with host". Depois clique em "Start" e "OK".

<img class="aligncenter size-full wp-image-596" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-14-26.png" alt="2015-05-01_20-14-26" width="505" height="340" />

Agora abra o seu software de terminal para acessar o servidor via SSH. Se você não tiver um software de terminal instalado, recomendo utilizar o <a href="http://pt.wikipedia.org/wiki/PuTTY" target="_blank">Putty</a>. Você pode fazer o download do Putty <a href="http://bit.ly/1OOWapi" target="_blank">aqui</a>. É um arquivinho com pouco mais de 500kb.

Feito isso, abra o Putty e coloque o IP do seu servidor ESXi e clique "Open".

<img class="aligncenter size-full wp-image-597" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-14-51.png" alt="2015-05-01_20-14-51" width="466" height="449" />

Faça o login com o seu usuário e senha (se você estiver aplicando essa configuração no servidor que configuramos no último post da série, o usuário é root e a senha install).

<img class="aligncenter wp-image-589" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-18-17.png" alt="2015-05-01_20-18-17" width="800" height="267" />

Digite a linha de comando :

<pre class="lang:default decode:true ">esxcli software vib install -v http://download3.vmware.com/software/vmw-tools/esxi_tools_for_guests/esx-tools-for-esxi-9.7.1-0.0.00000.i386.vib -f</pre>

Só lembrando que o seu servidor deve ter acesso a internet para funcionar.

<img class="aligncenter wp-image-590" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-18-50.png" alt="2015-05-01_20-18-50" width="800" height="267" />

Após algum tempo, a instalação estará completa. Faça um reboot no servidor e pronto!

<img class="aligncenter size-full wp-image-591" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-19-52.png" alt="2015-05-01_20-19-52" width="427" height="273" />

<img class="aligncenter size-full wp-image-592" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-30-12.png" alt="2015-05-01_20-30-12" width="352" height="293" />

Mais informações podem ser encontradas no site <a href="https://labs.vmware.com/flings/vmware-tools-for-nested-esxi" target="_blank">VMware Flings</a>

<img class="aligncenter wp-image-587" src="http://homelaber.com.br/site/wp-content/uploads/2015/05/2015-05-01_20-17-21.png" alt="2015-05-01_20-17-21" width="800" height="416" />

Até a próxima!

Não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no<a title="@Homelaber" href="https://twitter.com/homelaber" target="_blank">Twitter</a> (@Homelaber) e curtir a nossa página no <a title="Facebook HomeLaber Brasil" href="https://www.facebook.com/homelaber" target="_blank">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidade do blog.