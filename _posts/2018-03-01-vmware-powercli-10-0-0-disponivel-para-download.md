---
ID: 4569
post_title: >
  VMware PowerCLI 10.0.0 disponível para
  download
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2t6jnzh
published: true
post_date: 2018-03-01 09:00:02
---
Olá Homelabers!

Você já usa PowerCLI no seu ambiente de lab ou de produção?
<h2>O que é o VMware PowerCLI?</h2>
<blockquote>O VMware PowerCLI é uma ferramenta de script e linha de comando criada em cima do Windows PowerShell e fornece mais de 600 cmdlets para gerenciar e automatizar praticamente todos os produtos da VMware como vSphere, vCloud, vRealize Operations Manager, vSAN, NSX-T, VMware Cloud em AWS e ambientes VMware Horizon.</blockquote>
O <strong>PowerCLI</strong> é uma tremenda ferramenta para <strong>automatizar ações de produtos VMware</strong>. Você pode fazer praticamente tudo com ele, utilizando scripts e a linguagem PowerShell. É uma mão na roda e vale muito a pena conhecer, se você ainda não o utiliza no seu dia a dia. E se você já usa, atualize agora para a nova versão.

Mas vamos ao tema do post do hoje, ontem a VMware liberou para GA - General Availability - a versão 10.0.0 do VMware PowerCLI, que completa 10 anos de existência.
<h2>Novidades:</h2>
<h4>Suporte multi-plataforma</h4>
O PowerCLI 10.0.0 adiciona suporte para Mac OS e Linux! O único pré-requisito é ter o <a href="https://github.com/PowerShell/PowerShell" target="_blank" rel="noopener">PowerShell Core 6.0 instalado</a>.

Para <strong>instalar o PowerCLI</strong> 10.0 basta executar o comando:
<pre class=""><strong>Install-Module -Name VMware.PowerCLI -Scope CurrentUser</strong></pre>
Para <strong>atualizar o PowerCLI</strong> para a versão atual, execute o comando:
<pre class=""><strong>Update-Module VMware.PowerCLI</strong></pre>
<img class="aligncenter size-large wp-image-4570" src="http://homelaber.com.br/site/wp-content/uploads/2018/03/powercli-v10-1-644x357.jpg" alt="" width="644" height="357" />
<h4>Manipulação de certificados padrão</h4>
Esta versão altera a forma como os certificados são tratados quando se conecta a um servidor vCenter ou host ESXi com o cmdlet Connect-VIServer. Se o servidor estiver usando um certificado inválido (auto-assinado ou não), o PowerCLI retornaria um aviso. O PowerCLI foi atualizado para ser mais seguro.

Se você estiver usando um certificado inválido, você pode evitar o erro com o cmdlet '<strong>Set-PowerCLIConfiguration</strong>'. Basta executar o comando:
<pre class=""><strong>Set-PowerCLIConfiguration -InvalidCertificateAction Ignore</strong></pre>
<h4>Comandos e Propriedades Descontinuados</h4>
Nessa versão cinco cmdlets que se tornaram obsoletos e foram substituidos pelo cmdlet I<strong>nvoke-VMScript.</strong>

Get-VMGuestNetworkInterface
Set-VMGuestNetworkInterface
Get-VMGuestRoute
New-VMGuestRoute
Remove-VMGuestRoute
<h4>Mais informações e documentação oficial:</h4>
Para obter mais informações sobre as alterações feitas no VMware PowerCLI 10.0.0, incluindo melhorias, aprimoramentos de segurança e recursos obsoletos, consulte o <a href="https://www.vmware.com/support/developer/PowerCLI/changelog.html" target="_blank" rel="noopener" name="&amp;lpos=apps_scodevmw : 10">Change Log</a>. Para obter mais informações sobre recursos específicos do produto, consulte o <a href="https://code.vmware.com/doc/preview?id=6332" target="_blank" rel="noopener">VMware PowerCLI 10.0.0 User’s Guide</a>. Para obter mais informações sobre cmdlets específicos, consulte o <a href="https://code.vmware.com/doc/preview?id=6330" target="_blank" rel="noopener" name="&amp;lpos=apps_scodevmw : 12">VMware PowerCLI 10.0.0 Cmdlet Reference</a>.

Deixe nos comentários sua experiência com PowerCLI e se você já atualizou para a nova versão.

https://twitter.com/PowerCLI/status/969009388378836993

https://twitter.com/PowerCLI/status/968966775814619136