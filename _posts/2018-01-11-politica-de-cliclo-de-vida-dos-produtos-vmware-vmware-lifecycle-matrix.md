---
ID: 1512
post_title: >
  Política de Cliclo de Vida dos Produtos
  VMware (VMware Lifecycle Matrix)
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2ExdBYb
published: true
post_date: 2018-01-11 12:43:47
---
Olá Homelabers!

<strong>Qual versão do vSphere vocês estão utilizando em produção ou em seus labs?</strong>

Particularmente, ainda estou rodando meu lab na versão 6.0.X, mas estou planejando um upgrade para o 6.5 em breve - com posts, aguarde! :)

Outro dia vi um tweet do Emad Younis (@emad_younis) sobre o fim do suporte geral do vSphere 5.5 (caramba já!!!) em Setembro/2018 e resolvi resgatar esse post e que estava nos rascunhos do blog.

https://twitter.com/emad_younis/status/950820777674158081

Hoje quero falar sobre a <strong>Política de Ciclo de Vida dos produtos VMware</strong> (<strong>Lifecycle Matrix</strong>), um ponto super importante, mas que vejo pouca gente falando sobre.

Em linhas gerais, a política do ciclo de vida dos produtos VMware é a seguinte:
<blockquote>A VMware suportará a versão atual do software de acordo com os Termos e Condições de Suporte e Subscrição. <strong>Após</strong> a disponibilidade geral (<strong>GA</strong>) <strong>do próximo lançamento principal</strong>, a VMware <strong>suportará o lançamento principal imediatamente anterior</strong> e seus lançamentos menores <strong>por mais 18 meses.</strong></blockquote>
<div class="paragraphText parbase section">
<div class="section-custom ">
<div class="container-fluid">
<div class="row">
<div class="col-md-12">

Os produtos da VMware tem <strong>um ciclo de vida de 7 anos</strong>, sendo <strong>5 anos de General Support</strong> a partir do GA (General Availability) e mais<strong> dois anos de Technical Guidance</strong>.

<img class="size-full wp-image-4295 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2018/01/vmware-lifecycle-police-matrix.jpg" alt="" width="568" height="95" />
<h3></h3>
<h2><span class="notranslate">Fase geral de suporte (General Support Phase)</span></h2>
<span class="notranslate">A fase de suporte geral começa na data de disponibilidade geral de uma versão principal ("GA") e tem uma duração fixa.</span> <span class="notranslate">Durante a fase de Suporte geral, para os clientes que compraram o suporte da VMware, a VMware oferece atualizações, correções de erros e segurança e assistência técnica, de acordo com os Termos e Condições de Suporte e Subscrição.</span>
<blockquote><strong>End of General Support não significa NÃO SUPORTADO!</strong></blockquote>
</div>
</div>
</div>
</div>
</div>
<div class="paragraphText parbase section">
<div class="section-custom ">
<div class="container-fluid">
<div class="row">
<div class="col-md-12">
<h2><span class="notranslate">Fase de orientação técnica (</span>Technical Guidance Phase)</h2>
<span class="notranslate">A <strong>orientação técnica</strong>, se disponível, <strong>é fornecida a partir do final da fase de suporte geral</strong> e tem uma duração fixa.</span> <span class="notranslate">A orientação técnica <strong>está disponível principalmente através do portal de auto-ajuda</strong> e o <strong>suporte por telefone não é fornecido</strong>.</span> <span class="notranslate">Os clientes também podem abrir um pedido de suporte on-line para <strong>receber suporte e soluções alternativas</strong> para problemas de baixa gravidade <strong>apenas nas configurações suportadas</strong>.</span> <span class="notranslate">Durante a fase de Orientação Técnica, a VMware <strong>não oferece suporte</strong> a novo hardware, atualizações do servidor / cliente / host, novos patches de segurança ou correções de erros.</span> <span class="notranslate">Esta fase destina-se a ser <strong>utilizada por clientes que operam em ambientes estáveis</strong> ​​com sistemas que operam sob cargas razoavelmente estáveis.</span>

</div>
</div>
</div>
</div>
</div>
<div class="paragraphText parbase section">
<div class="section-custom ">
<div class="container-fluid">
<div class="row">
<div class="col-md-12">
<h2><span class="notranslate">Fim da Vida de Suporte (End Of Support Life)</span></h2>
<span class="notranslate">Um <strong>produto atingiu o fim da vida de suporte</strong> (EOSL) quando já <strong>não é </strong>geralmente<strong> suportado pela VMware</strong>.</span> <span class="notranslate">O fim da vida de suporte para um produto específico é o final do suporte geral ou final da orientação técnica, se disponível para esse produto específico.</span>

</div>
</div>
</div>
</div>
</div>
<div class="paragraphText parbase section">
<div class="section-custom ">
<div class="container-fluid">
<div class="row">
<div class="col-md-12">
<h2><span class="notranslate">Fim da Disponibilidade (EOA) / Fim da Distribuição (EOD)</span></h2>
<span class="notranslate">Um produto <strong>chegou ao fim da disponibilidade quando já não está disponível para compra da VMware</strong>.</span> <span class="notranslate">Um produto chegou ao fim da distribuição quando a VMware não pode mais disponibilizá-la como download da vmware.com ou distribuir o produto de outras maneiras.</span> <span class="notranslate">O <strong>fim da disponibilidade e o final da distribuição podem coincidir</strong>.</span>

</div>
</div>
</div>
</div>
</div>
<h2><span class="notranslate">Resumo do suporte ao ciclo de vida</span></h2>
<table width="997">
<tbody>
<tr>
<td width="548">Características</td>
<td style="text-align: center;" width="125">Fase geral de suporte</td>
<td style="text-align: center;" width="132">Fase de orientação técnica</td>
<td style="text-align: center;" width="192">Fim da sustentação Fase de vida Fim da disponibilidade</td>
</tr>
<tr>
<td>Atualizações e atualizações de manutenção</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Novos patches de segurança</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Novas correções de erros</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Novo suporte de hardware</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Atualizações do Servidor, Cliente e Convidado OS</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Arquivar um pedido de suporte</td>
<td style="text-align: center;">Telefone e Web</td>
<td style="text-align: center;">Apenas na Web</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Correções de segurança existentes</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Correções de erros existentes</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Soluções alternativas para problemas de baixa gravidade (gravidade 2, 3 e 4)</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Suporte baseado em auto-ajuda na web</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;"></td>
</tr>
<tr>
<td>Acesso à Base de Conhecimento</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
<td style="text-align: center;">X</td>
</tr>
</tbody>
</table>
<h2>VMware Lifecycle Product Matrix</h2>
Como comentei no começo do post, o vSphere 5.5 está chegando ao fim do suporte em setembro desse ano (2018). A VMware publica uma planilha com o ciclo de vida de todos os seus produtos e essa planilha pode ser encontrada nesse <a href="https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/support/product-lifecycle-matrix.pdf" target="_blank" rel="noopener">link</a> (pdf)
<table width="665">
<tbody>
<tr>
<td style="text-align: center;" width="220"><strong>PRODUCT RELEASE</strong></td>
<td style="text-align: center;" width="123"><strong>GENERAL AVAILABILITY</strong></td>
<td style="text-align: center;" width="167"><strong>END OF GENERAL SUPPORT</strong></td>
<td style="text-align: center;" width="155"><strong>END OF TECHINICAL GUIDANCE</strong></td>
</tr>
<tr>
<td>ESXi 5.5 / VCENTER SERVER 5.5</td>
<td style="text-align: center;">19/09/13</td>
<td style="text-align: center;"><strong>19/09/18</strong></td>
<td style="text-align: center;">19/09/20</td>
</tr>
<tr>
<td>ESXi 6.0 / VCENTER SERVER 6.0</td>
<td style="text-align: center;">21/03/15</td>
<td style="text-align: center;">12/03/20</td>
<td style="text-align: center;">12/03/22</td>
</tr>
<tr>
<td>ESXi 6.5 / VCENTER 6.5</td>
<td style="text-align: center;">15/11/16</td>
<td style="text-align: center;">15/11/21</td>
<td style="text-align: center;">15/11/23</td>
</tr>
</tbody>
</table>
É importante ficar de olho nos anúncios dos fabricantes - não só da VMware - para se planejar e não ser pego de surpresa e ficar sem suporte.

Deixe ai nos comentários, qual o software mais antigo que você tem em produção hoje?

Mais informações aqui &gt;&gt; <a href="https://www.vmware.com/support/policies/lifecycle.html" target="_blank" rel="noopener">https://www.vmware.com/support/policies/lifecycle.html</a>

&nbsp;

Um abraço e até o próximo post!

--VC