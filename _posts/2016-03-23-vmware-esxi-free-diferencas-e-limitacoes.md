---
ID: 1208
post_title: 'VMware ESXi FREE &#8211; Diferenças e Limitações'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1SgTzDe
published: true
post_date: 2016-03-23 02:48:17
---
Olá Homelabers!

Hoje vou falar sobre as principais diferenças e limitações entre a versão FREE do VMware ESXi e a versão paga.

<img class="aligncenter size-full wp-image-1215" src="http://homelaber.com.br/site/wp-content/uploads/2016/03/oh-yeah-its-free.png" alt="oh-yeah-its-free" width="400" height="318" />

Muitas pessoas ao ter o primeiro contato o mundo da virtualização descobrem que existe uma <strong>versão FREE do VMware ESXi</strong> e logo surge uma dúvida:
<blockquote>
<h3><em>"Quais são as diferenças entre a versão FREE e a versão paga?"</em></h3>
</blockquote>
<!--more-->

De uma forma bem resumida, as principais limitações são:
<ul>
 	<li>Não existe suporte para a versão FREE</li>
 	<li>A versão FREE do VMware ESXi não pode ser adicionada a um servidor vCenter</li>
 	<li>Limite de 2 CPUs físicas por host</li>
 	<li>Máximo de 8 vCPUs (virtual CPUs) por VM</li>
 	<li>Número ilimitado de Cores por CPU</li>
 	<li>Número ilimitado de Memória por host.</li>
</ul>
A versão FREE do VMware ESXi é o mesmo download da versão FULL que fica "desbloqueada" por 60 dias. Se você não inserir o Serial Number da versão free, o produto funciona com a versão FULL por 60 dias.

Após o período de trial (60 dias) o produto perde as funcionalidades da versão FULL, bloqueando as funcionalidades adicionais e se torna a versão FREE. Mesmo assim, entrar com o Serial Number que é disponibilizado quando você opta pela versão FREE no site da VMware.

Os principais cenários de uso da versão FREE do VMware ESXi são:
<ul>
 	<li>Primeiros contatos com a ferramenta</li>
 	<li>Laboratório simples</li>
 	<li>Testes de validação</li>
 	<li>Pequenas empresas que querem "testar" virtualização sem um grande investimento.</li>
</ul>
<h3>Usar a versão FREE para estudos e Labs, minha opinião:</h3>
<em><strong>Não vale a pena investir TEMPO e subir um lab na versão FREE do ESXi.</strong></em> Você acaba perdendo muitas funcionalidades e essas funcionalidades são as mais legais do produto: vMotion, Fault Tolerance, High Availability, Cluster, Shared Storage, só para citar algumas.

Para um LAB VMware ser bacana, você deve ter no mínimo o vCenter instalado e 2-3 hosts ESXi, mesmo que rodando nested. Sem isso, você não conseguirá simular o "mundo real" de qualquer empresa.

Minha recomendação é sempre baixar a versão TRIAL que da suporte FULL a todas as funcionalidades por 60 dias. Após esse período, você pode - e deve - desmontar o seu LAB e configurar novamente. Pode parecer "um saco" a primeira vista, mas depois que você aprende e "pega as manhas" todo o processo não leva mais do que algumas horas. E com o tempo, você vai desenvolvendo scripts, criando templates, etc. Essa repetição vale a pena.
<h3>Como obter a versão FREE do VMware ESXi (6.x).</h3>
<ul style="list-style-type: square;">
 	<li>Acessar o site <a href="https://my.vmware.com/web/vmware/evalcenter?p=free-esxi6">VMware vSphere Hypervisor (ESXi) 6.0 Download Page</a></li>
</ul>
<img class="aligncenter wp-image-1209" src="http://homelaber.com.br/site/wp-content/uploads/2016/03/como-obter-versão-free-vmware-esxi-000.png" alt="" width="600" height="286" />
<ul style="list-style-type: square;">
 	<li>Fazer o login no site ou criar a sua conta. Se você não tiver uma conta no my.vmware.com, basta criar clicando em “Create an Account” e seguir o passo-a-passo no site</li>
 	<li>Fazer o registro para a versão do ESXi FREE</li>
</ul>
<img class="aligncenter wp-image-1210" src="http://homelaber.com.br/site/wp-content/uploads/2016/03/como-obter-versão-free-vmware-esxi-001.png" alt="como-obter-versão-free-vmware-esxi-001" width="600" height="151" />
<ul style="list-style-type: square;">
 	<li>Você irá receber uma chave única e ter acesso ao download do software</li>
 	<li>Após isso, é só fazer o download do software</li>
</ul>
<img class="aligncenter wp-image-1211" src="http://homelaber.com.br/site/wp-content/uploads/2016/03/como-obter-versão-free-vmware-esxi-002.png" alt="como-obter-versão-free-vmware-esxi-002" width="600" height="248" />
<h3>Como registrar a versão FREE do VMware ESXi (6.x):</h3>
<ul style="list-style-type: square;">
 	<li><a href="http://homelaber.com.br/vmware-homelab-parte-2-instalacao-vmware-esxi-2/" target="_blank" rel="noopener">Instalar o ESXi</a></li>
 	<li>Fazer o login com o vSphere Client</li>
 	<li>Navegar até a aba "Configuration" &gt;&gt; "Licenced Features"</li>
 	<li>Clicar em "Edit..." e digitar a sua chave de licença.</li>
</ul>
<img class="aligncenter wp-image-1216" src="http://homelaber.com.br/site/wp-content/uploads/2016/03/free-esxi-60-enter-license.png" alt="free-esxi-60-enter-license" width="600" height="130" />

&nbsp;

Por hoje é isso pessoal!

Deixe o seu comentário ou opinião aqui no post e nos siga nas redes sociais:

Twitter (<a href="http://twitter.com/homelaber" target="_blank" rel="noopener">@Homelaber</a>)

Facebook (<a href="http://fb.com/homelaber" target="_blank" rel="noopener">fb.com/homelaber</a>)

Youtube (<a href="http://bit.ly/youtubehomelaber" target="_blank" rel="noopener">http://bit.ly/youtubehomelaber</a>).