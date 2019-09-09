---
ID: 369
post_title: >
  VMware HomeLab – Parte 2 –
  Instalação VMware ESXi
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1bn2brg
published: true
post_date: 2015-04-24 09:00:16
---
Olá Homelabers!

Essa é a segunda parte da <a href="http://homelaber.com.br/serie-vmware-homelab-setup/">série VMware HomeLab</a> e vamos realizar a instalação do VMware ESXi em seu servidor.

Relembrando o nosso <a href="http://homelaber.com.br/vmware-homelab-parte-0-introducao-e-arquitetura/">cenário</a>: Você trabalha em uma empresa de pequeno/médio porte chamada <strong>FIRMALABS</strong> e seus servidores são antigos, sem garantia e suporte. Foi aprovado pela diretoria um refresh tecnológico e decidido após um estudo pela troca dos servidores físicos e a implantação de um ambiente virtualizado baseado em produtos VMware.

Você já fez a compra dos servidores, assim como de todas as licenças de software necessárias para o projeto. Os servidores foram entregues e agora o projeto começa para valer. Chegou a hora de colocar a mão na massa.

Hoje iremos realizar a instalação do servidor <strong>esx0</strong> - que se acordo com nossa arquitetura de laboratório será a base para a instalação do ambiente virtualizado do cenário da FIRMALABS.

<img class="aligncenter size-full wp-image-529" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/2015-04-25_01-02-45.png" alt="2015-04-25_01-02-45" width="690" height="437" />

<!--more-->

N<a href="http://homelaber.com.br/vmware-homelab-parte-1-preparativos/">o post anterior</a>, eu indiquei todos os downloads necessários para essa instalação. Caso ainda não tenha feito o seu registro no site da VMware e baixado as ISOs necessárias, volte ao post anterior e depois continue a partir daqui. Então vamos lá!

<strong>Pré-requisitos:</strong>

<ul style="list-style-type: square;">
    <li>Download do ISO do VMware ESXi 5.5 - veja como realizar o download no site da VMware no<a href="http://homelaber.com.br/vmware-homelab-parte-1-preparativos/"> post anterior</a></li>
    <li>Pendrive de no mínimo 8GB para criar o boot e instalar o ESXi - opcionalmente você pode criar um CD de boot com o ISO e instalar o ESXi diretamente no HD, mas eu aconselho fazer a instalação em um pendrive. Para criar um pendrive de boot, siga as instruções desse <a href="http://homelaber.com.br/criando-ubs-boot-vmware-exsi-com-rufus/">post</a></li>
    <li>Configurar seu PC para dar boot pelo USB</li>
    <li>Ativar as opções de virtualização na BIOS de seu PC.</li>
</ul>

&nbsp;

[su_note radius="0"]<strong>Atenção:</strong> Esse PC será utilizado somente para esse fim, ou seja, será o seu servidor VMware. Os dados do HD serão apagados, portanto, faça backup dos seus dados antes de começar esse passo-a-passo. Eu não me responsabilizo por qualquer dano ou perda de dados no seu computador.[/su_note]

O tempo estimado para realização de todas os passos deve ficar entre 20 e 30 minutos.

<strong>Passo a passo:</strong>

Com o pendrive de boot já criado, faça o boot pelo USB

<img class="aligncenter size-full wp-image-475" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL2.png" alt="042415_0353_VMwareHomeL2.png" width="686" height="386" />

Após o boot você verá a tela a seguir. Escolha a primeira opção para executar o instalador

<img class="aligncenter size-full wp-image-476" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL3.png" alt="042415_0353_VMwareHomeL3.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-477" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL4.png" alt="042415_0353_VMwareHomeL4.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-478" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL5.png" alt="042415_0353_VMwareHomeL5.png" width="686" height="386" />

Após o instalador carregar todos os arquivos necessários na memória, a tela inicial do instalador irá aparecer. Pressione ENTER para continuar

<img class="aligncenter size-full wp-image-479" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL6.png" alt="042415_0353_VMwareHomeL6.png" width="686" height="386" />

Pressione F11 para aceitar a licença e continuar

<img class="aligncenter size-full wp-image-480" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL7.png" alt="042415_0353_VMwareHomeL7.png" width="686" height="386" />

Na próxima tela, você deverá escolher o local de instalação. Escolha o seu Pendrive e pressione ENTER para continuar

<img class="aligncenter size-full wp-image-481" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL8.png" alt="042415_0353_VMwareHomeL8.png" width="686" height="386" />

A próxima tela apresenta a escolha do idioma do teclado. Escolha a opção que melhor te atender. Eu sempre costumo escolher US Default. Pressione ENTER para continuar

<img class="aligncenter size-full wp-image-482" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL9.png" alt="042415_0353_VMwareHomeL9.png" width="686" height="386" />

A próxima tela solicita que você informe a senha de ROOT. Escolha uma senha fácil de ser lembrada e anote em algum lugar. Para efeitos de laboratório, vou escolher a senha “install”. Pressione ENTER para continuar.

<img class="aligncenter size-full wp-image-483" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL10.png" alt="042415_0353_VMwareHomeL10.png" width="686" height="386" />

Pressione F11 para confirmar e iniciar a instalação

<img class="aligncenter size-full wp-image-485" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL12.png" alt="042415_0353_VMwareHomeL12.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-486" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL13.png" alt="042415_0353_VMwareHomeL13.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-487" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL14.png" alt="042415_0353_VMwareHomeL14.png" width="686" height="386" />

Quando a instalação finalizar, pressione ENTER para reiniciar o servidor.

<img class="aligncenter size-full wp-image-488" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL15.png" alt="042415_0353_VMwareHomeL15.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-489" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL16.png" alt="042415_0353_VMwareHomeL16.png" width="686" height="386" />

Após o boot, o servidor ESXi irá receber um IP do seu DHCP (no caso de existir um servidor DHPC na sua rede) e está pronto para ser utilizado.

<img class="aligncenter size-full wp-image-490" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL17.png" alt="042415_0353_VMwareHomeL17.png" width="686" height="386" />

Viu como é fácil? À primeira vista instalar um SERVIDOR de virtualização parece um bixo de sete cabeças.

Agora vamos as configurações:

Pressione F2 e insira o seu usuário e password, no nosso caso “root” | “install”.

<img class="aligncenter size-full wp-image-491" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL18.png" alt="042415_0353_VMwareHomeL18.png" width="686" height="386" />

Selecione a opção “Configure Management Network” e pressione ENTER

<img class="aligncenter size-full wp-image-492" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL19.png" alt="042415_0353_VMwareHomeL19.png" width="686" height="386" />

Selecione a sua placa de rede - em nosso caso só temos 1 e pressione ENTER

<img class="aligncenter size-full wp-image-493" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL20.png" alt="042415_0353_VMwareHomeL20.png" width="686" height="386" />

Selecione “Network Adapters” e pressione ENTER

<img class="aligncenter size-full wp-image-494" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL21.png" alt="042415_0353_VMwareHomeL21.png" width="686" height="386" />

Nessa tela você deverá realizar as configurações de IP. Marque a opção “Set static IP address and network configuration:”

<img class="aligncenter size-full wp-image-495" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL22.png" alt="042415_0353_VMwareHomeL22.png" width="686" height="386" />

Escolha um IP livre na sua rede e preencha os campos IP Address, Subnet Mask e Default Gateway. Pressione ENTER para confirmar e voltar a tela anterior.

Selecione “DNS Configuration” e pressione ENTER.

<img class="aligncenter size-full wp-image-496" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL23.png" alt="042415_0353_VMwareHomeL23.png" width="686" height="386" />

Selecione a opção “Use the following DNS server address and hostname:” e preencha os campos com o IP de seus servidores DNS e escolha um nome para o seu servidor. Vou utilizar “ESX0”, você pode escolher o nome que quiser. Pressione ENTER para confirmar.

<img class="aligncenter size-full wp-image-497" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL24.png" alt="042415_0353_VMwareHomeL24.png" width="686" height="386" />

Na próxima tela, pressione Y (yes) para aplicar as alterações e reiniciar o servidor.

<img class="aligncenter size-full wp-image-498" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL25.png" alt="042415_0353_VMwareHomeL25.png" width="686" height="386" />

<img class="aligncenter size-full wp-image-499" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL26.png" alt="042415_0353_VMwareHomeL26.png" width="686" height="386" />

Após o boot, você verá que ele já assumiu as novas configurações de IP. Faltam agora somente mais alguns passos e finalizaremos a instalação.

<img class="aligncenter size-full wp-image-500" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL27.png" alt="042415_0353_VMwareHomeL27.png" width="686" height="386" />

Pronto. O seu servidor ESXi está instalado e configurado. O acesso ao servidor será feito remotamente via o vSphere Client.

Vamos agora fazer o download e a instalação do vSphere Client:

Abra o browser e acesse https://ip-do-seu-servidor-esxi/ no nosso caso https://192.168.100.150/

<img class="aligncenter size-full wp-image-503" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL30.png" alt="042415_0353_VMwareHomeL30.png" width="686" height="369" />

Clique em “Download vSphere Client” e faça o download do arquivo que tem aproximadamente 350MB.

<img class="aligncenter size-full wp-image-504" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL31.png" alt="042415_0353_VMwareHomeL31.png" width="686" height="369" />

A instalação do vSphere Client é bem simples: aceite todos os defaults e next, next, finish.

<img class="aligncenter size-full wp-image-505" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL32.png" alt="042415_0353_VMwareHomeL32.png" width="686" height="369" />

<img class="aligncenter size-full wp-image-506" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL33.png" alt="042415_0353_VMwareHomeL33.png" width="686" height="369" />

<img class="aligncenter size-full wp-image-507" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL34.png" alt="042415_0353_VMwareHomeL34.png" width="686" height="369" />

<img class="aligncenter size-full wp-image-508" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL35.png" alt="042415_0353_VMwareHomeL35.png" width="686" height="369" />

<img class="aligncenter size-full wp-image-509" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL36.png" alt="042415_0353_VMwareHomeL36.png" width="686" height="369" />

Abra o vSphere Client e coloque as informações de IP, User name e Password do seu servidor ESXi.

<img class="aligncenter size-full wp-image-510" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL37.png" alt="042415_0353_VMwareHomeL37.png" width="686" height="369" />

Na tela de aviso de segurança, marque para instalar o certificado e depois clique no botão Ignore.

<img class="aligncenter size-full wp-image-511" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL38.png" alt="042415_0353_VMwareHomeL38.png" width="686" height="369" />

Clique em OK na próxima tela para aceitar a licença de avaliação.

<img class="aligncenter size-full wp-image-512" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/042415_0353_VMwareHomeL39.png" alt="042415_0353_VMwareHomeL39.png" width="686" height="369" />

Seja bem-vindo ao seu novo servidor VMware ESXi novinho em folha! :D

<img class="aligncenter size-full wp-image-527" src="http://homelaber.com.br/site/wp-content/uploads/2015/04/vmware-homelab-parte-2-instalacao-vmware-esxi-058.png" alt="vmware-homelab-parte-2-instalacao-vmware-esxi-058" width="800" height="432" />

No próximo post, iremos instalar 2 VMs com o ESXi, basicamente repetir os passos acima. Esses serão os hosts do cluster VM da FIRMALABS.

Caso você encontre alguma dificuldade ou dúvidas sobre o que foi apresentado nesse post, não deixe de comentar no post, pois faço questão de te responder a todas as suas dúvidas.

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no Twitter (@Homelaber) e curtir a nossa página no Facebook (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

Vou deixar aqui alguns links oficiais da VMware onde você poderá se aprofundar nos detalhes da instalação do ESXi.

<a href="http://pubs.vmware.com/vsphere-55/topic/com.vmware.ICbase/PDF/vsphere-esxi-vcenter-server-552-installation-setup-guide.pdf" target="_blank">VMware vSphere 5.5 Documentation Center</a> (em Inglês)  <a href="https://pubs.vmware.com/vsphere-55/topic/com.vmware.ICbase/PDF/vsphere-esxi-vcenter-server-55-installation-setup-guide.pdf" target="_blank">pdf para download</a>

<a href="http://pubs.vmware.com/vsphere-55/topic/com.vmware.vsphere.install.doc/GUID-31B6413C-E909-4F9D-9AD6-4090496B5D65.html#GUID-31B6413C-E909-4F9D-9AD6-4090496B5D65" target="_blank">Before You Install ESXi</a> (em Inglês)

<a href="http://www.vmware.com/br/products/vsphere-hypervisor/gettingstarted" target="_blank">Getting Started Guide</a>