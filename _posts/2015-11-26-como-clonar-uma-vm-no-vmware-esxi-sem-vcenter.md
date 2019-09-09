---
ID: 995
post_title: >
  Como clonar uma VM no VMware ESXi sem
  vCenter
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1NRNPLs
published: true
post_date: 2015-11-26 21:00:00
---
Olá Homelabers! Nesse post rapidinho vou mostrar como clonar uma VM no VMware ESXi sem vCenter.

Essa dica é util e ajuda bastante se você tiver um host ESXi sem vCenter (a versão free) e precisa clonar uma vm como por exemplo um template Linux que você montou. Na verdade, o que faremos é uma "cópia" do disco da VM e criaremos uma nova VM apontando para esse disco.

Com isso, todo o trabalho da instalação do SO será poupado.

Vamos lá?

<img class="aligncenter size-full wp-image-996" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/dolly_2019167c.jpg" alt="dolly_2019167c" width="460" height="287" /><!--more-->

O primeiro passo é logar no ESXi via SSH, mas para isso, você precisa habilitar o acesso SSH ao host.

Aba "Configuration" --&gt; Menu "Security Profile" --&gt; Services Properties...

<img class="aligncenter wp-image-999" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-003.png" alt="clonar-vm-sem-vcenter-003" width="850" height="357" />

<img class="aligncenter size-full wp-image-997" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-001.png" alt="clonar-vm-sem-vcenter-001" width="505" height="340" />

<img class="aligncenter size-full wp-image-998" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-002.png" alt="clonar-vm-sem-vcenter-002" width="658" height="694" />

Após isso devemos encontrar o diretório onde a VM original se encontra.

O diretório padrão onde o as vms ficam armazenadas é /vmfs/volumes///, navegue entre os diretórios com o comando CD

<img class="aligncenter wp-image-1004" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-008.png" alt="clonar-vm-sem-vcenter-008" width="850" height="255" />

Agora vamos criar um diretório para a nova vm:

mkdir &lt;novavm&gt;

O comando para copiar a vm é o <a href="https://pubs.vmware.com/vsphere-55/index.jsp?topic=%2Fcom.vmware.vsphere.storage.doc%2FGUID-A5D85C33-A510-4A3E-8FC7-93E6BA0A048F.html" target="_blank">vmkfstools</a>

<pre class="lang:default decode:true">vmkfstools -d thin -i /vmfs/volumes/54023ae9-989b9114-f653-001b21267170/linux-ubuntu-template/linux-ubuntu-template.vmdk /vmfs/volumes/56512cb8-3b202810-c2c8-001b21267170/syslog-ng/syslog-ng.vmdk</pre>

<img class="aligncenter wp-image-1003" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-007.png" alt="clonar-vm-sem-vcenter-007" width="850" height="78" />

<img class="aligncenter wp-image-1002" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-006.png" alt="clonar-vm-sem-vcenter-006" width="850" height="50" />

Assim que a cópia for finalizada, você pode fechar o ssh e voltar para o vSphere Client para criar uma nova VM.

Os passos são os mesmos o que muda é na hora de criar o disco, você vai escolher o disco clonado.

<img class="aligncenter size-full wp-image-1001" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-005.png" alt="clonar-vm-sem-vcenter-005" width="728" height="692" />

<img class="aligncenter size-full wp-image-1000" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/clonar-vm-sem-vcenter-004.png" alt="clonar-vm-sem-vcenter-004" width="728" height="692" />

Dependendo do SO que você clonou, será necessário fazer algumas configurações - no caso do Windows rodar o Sysprep e no Linux mudar o hostname, ip, etc.

É isso pessoal! Espero que essa dica seja útil e qualquer dúvida é só deixar um recado aqui nos comentários do post.

<img class="size-full wp-image-1006 aligncenter" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/gloc-like-e1448594746803.jpg" alt="Designed by Joel Jordan for GlockStore" width="450" height="154" />