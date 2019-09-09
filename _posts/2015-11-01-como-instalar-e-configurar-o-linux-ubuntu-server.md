---
ID: 743
post_title: >
  Como instalar e configurar o Linux
  Ubuntu Server
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1Q6U2be
published: true
post_date: 2015-11-01 10:00:39
---
Olá Homelabers!

Neste post vou mostrar como criar e instalar uma VM com o Ubuntu Server. Será uma instalação básica que será a base para várias outras instalações. Aliás eu já deveria ter feito esse post há bastante tempo.

Em um primeiro momento, para quem nunca instalou um servidor Linux, pode parecer coisa de outro mundo, mas o processo de instalação é bastante fácil e rápido.

<img class="aligncenter size-full wp-image-816" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/logo-ubuntu_su-black_orange-hex.png" alt="logo-ubuntu_su-black_orange-hex" width="425" height="210" />

Vamos lá?

<!--more-->

Antes de mais nada, esse post pode parecer a primeira vista bastante longo, mas ele está "recheado" de telinhas com <em>todos</em> os passos para a instalação do Linux Ubuntu Server, tentei ser o mais didático e detalhista possível.

A primeira coisa a se fazer é baixar a ISO do Ubuntu server no site<a href="http://www.ubuntu.com/download/server" target="_blank"> http://www.ubuntu.com/download/server</a>. O ISO tem pouco menos de 600MB.

<a href="http://www.ubuntu.com/download/server" target="_blank"><img class="aligncenter size-full wp-image-805" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-000.png" alt="homelaber-instalacao-ubuntu-server-homelab-000" width="982" height="334" /></a>

O próximo passo é logar no vSphere e criar uma nova VM

<img class="aligncenter size-full wp-image-749" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-001.png" alt="homelaber-instalacao-ubuntu-server-homelab-001" width="430" height="533" />

Antes de criar a VM, vamos fazer o upload do arquivo ISO do Ubuntu.

Selecione o seu datastore, clique com o botão direito e selecione "Browse Datastore..."

<img class="aligncenter size-full wp-image-811" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-079.png" alt="homelaber-instalacao-ubuntu-server-homelab-079" width="930" height="411" />

Para manter tudo organizado, eu costumo criar uma pasta chamada "ISO" e nela guardar todos os ISOs que irei usar. Fica ao eu critério.

Clique no icone com uma setinha verde para cima, depois "Upload File..."

<img class="aligncenter size-full wp-image-810" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-082.png" alt="homelaber-instalacao-ubuntu-server-homelab-082" width="888" height="405" />

Selecione o arquivo .ISO do ubuntu server que acabamos de fazer o download e clique em "Open".

<img class="aligncenter size-full wp-image-809" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-081.png" alt="homelaber-instalacao-ubuntu-server-homelab-081" width="888" height="511" />

Aguarde o upload do arquivo para prosseguir com a instalação.

&nbsp;

<img class="aligncenter size-full wp-image-808" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-080.png" alt="homelaber-instalacao-ubuntu-server-homelab-080" width="400" height="200" />

Pronto, agora que temos o arquivo ISO já armazenado em nosso datastore, chegou a hora de criar uma nova VM.

Selecione File --&gt; New --&gt; Virtual Machine... ou Ctrl+N se você for um viciado em teclas de atalho como eu :)

<img class="aligncenter size-full wp-image-750" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-002.png" alt="homelaber-instalacao-ubuntu-server-homelab-002" width="574" height="257" />

Selecione "Custom"

<img class="aligncenter size-full wp-image-751" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-003.png" alt="homelaber-instalacao-ubuntu-server-homelab-003" width="728" height="692" />

De um nome para a sua VM. Eu usei "ubuntuserver"

<img class="aligncenter size-full wp-image-752" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-004.png" alt="homelaber-instalacao-ubuntu-server-homelab-004" width="728" height="692" />

Escolha o Datastore

<img class="aligncenter size-full wp-image-753" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-005.png" alt="homelaber-instalacao-ubuntu-server-homelab-005" width="728" height="692" />

Selecione a versão da maquina virtual

<img class="aligncenter size-full wp-image-754" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-006.png" alt="homelaber-instalacao-ubuntu-server-homelab-006" width="728" height="692" />

Selecione o sistema operacional, em nosso caso, Ubuntu Linux 64 bits

<img class="aligncenter size-full wp-image-755" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-007.png" alt="homelaber-instalacao-ubuntu-server-homelab-007" width="728" height="692" />

Para essa VM iremos utilizar 1vCPU e 1 Core. Essas configurações poderão ser alteradas posteriormente. Caso você esteja criando uma VM para alguma finalidade específica, mude as configurações aqui.

<img class="aligncenter size-full wp-image-756" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-008.png" alt="homelaber-instalacao-ubuntu-server-homelab-008" width="728" height="692" />

O mesmo vale para a quantidade de memória da VM. Caso você esteja criando uma VM para alguma finalidade específica, mude as configurações aqui.

<img class="aligncenter size-full wp-image-757" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-009.png" alt="homelaber-instalacao-ubuntu-server-homelab-009" width="728" height="692" />

Selecione a interface de rede.

<img class="aligncenter size-full wp-image-758" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-010.png" alt="homelaber-instalacao-ubuntu-server-homelab-010" width="728" height="692" />

Selecione a controladora SCSI. Deixe a opção default (LSI Logic Parallel). Mais informações <a href="https://blogs.vmware.com/vsphere/2014/02/vscsi-controller-choose-performance.html" target="_blank">aqui</a>

<img class="aligncenter size-full wp-image-759" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-011.png" alt="homelaber-instalacao-ubuntu-server-homelab-011" width="728" height="692" />

Selecione "Create a new virtual disk" para criar um novo disco (HD).

<img class="aligncenter size-full wp-image-760" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-012.png" alt="homelaber-instalacao-ubuntu-server-homelab-012" width="728" height="692" />

Defina do tamanho e o tipo. Nesse caso, defini um disco pequeno de 20 GB que é mais do que suficiente para a instalação do Ubuntu.

Outra escolha importante é o tipo de provisionamento de disco. Aqui vale um parenteses com a explicação de cada tipo de disco.

<img class="aligncenter size-full wp-image-761" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-013.png" alt="homelaber-instalacao-ubuntu-server-homelab-013" width="728" height="692" />

[su_box title="Diferenças entre tipos de disco em uma VM"]

<b> Thick Provision Lazy Zeroed </b> – é um disco “thick” padrão, ou seja, <i>todo o espaço é alocado no momento da sua criação</i>. Neste formato de disco virtual, qualquer dado que exista no dispositivo físico é mantido no momento da criação, e só são “zerados” no momento em que a máquina virtual vai escrevendo seus dados.

<b>Thick Provision Eager Zeroed</b> – é um disco “thick” que possui suporte a alguns recursos de cluster, como FT. Também aloca todo o espaço necessário no momento da sua criação. A diferença para o formato “lazy” (ou flat) é que os dados existentes no dispositivo físico são todos zerados no momento da criação. O tempo de criação deste tipo de disco pode demorar mais que os demais.

<b>Thin Provision</b> – neste tipo de disco <i>apenas um espaço mínimo é utilizado no momento da sua criação</i>. A medida que mais espaço físico for sendo necessário, o disco “thin” vai aumentando o seu tamanho, podendo chegar até o tamanho alocado inicialmente.

fonte: <a href="http://vmwarebrasil.blogspot.com.br/2013/04/qual-diferenca-entre-discos-thick-thin.html" target="_blank">http://vmwarebrasil.blogspot.com.br/2013/04/qual-diferenca-entre-discos-thick-thin.html</a>
[/su_box]

<img class="aligncenter size-full wp-image-762" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-014.png" alt="homelaber-instalacao-ubuntu-server-homelab-014" width="728" height="692" />

Selecione a opção "Edit the virtual machine..." e clique em Continue para iniciar o processo de criação da VM.

<img class="aligncenter size-full wp-image-763" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-015.png" alt="homelaber-instalacao-ubuntu-server-homelab-015" width="728" height="692" />

Remova o "New Floppy" selecionando a opção e clicando no botão "Remove". Não precisamos de um drive de disket em nossa VM certo?

<img class="aligncenter size-full wp-image-764" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-016.png" alt="homelaber-instalacao-ubuntu-server-homelab-016" width="708" height="632" />

Selecione New CD/DVD e marque a opção "Connect at power on" e em seguida selecione "Datastore ISO file" e clique em Browse e selecione o aquivo ISO que você baixou do site e subiu para o datastore.

<img class="aligncenter size-full wp-image-765" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-017.png" alt="homelaber-instalacao-ubuntu-server-homelab-017" width="728" height="692" />

Clique na aba "Options", selecione "Memory/CPU Hotplug e marque as opções destacadas na figura abaixo.

<img class="aligncenter size-full wp-image-766" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-018.png" alt="homelaber-instalacao-ubuntu-server-homelab-018" width="708" height="632" />

Clique em Finish e acompanhe a criação de nossa VM.
<img class="aligncenter size-full wp-image-767" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-019.png" alt="homelaber-instalacao-ubuntu-server-homelab-019" width="873" height="41" /> <img class="aligncenter size-full wp-image-768" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-020.png" alt="homelaber-instalacao-ubuntu-server-homelab-020" width="402" height="103" />

&nbsp;

Abra a console da VM e clique em Power On para "ligar a maquina" e iniciar o boot.<img class="aligncenter size-full wp-image-769" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-021.png" alt="homelaber-instalacao-ubuntu-server-homelab-021" width="905" height="666" />

Aqui começa de fato a instalação do sistema operacional. Selecione a lingua. Eu prefiro sempre instalar e utilizar o SO (seja ele qual for) em Inglês - mas isso é coisa de velho.

<img class="aligncenter size-full wp-image-770" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-022.png" alt="homelaber-instalacao-ubuntu-server-homelab-022" width="905" height="666" />

Selecione "Install Ubuntu Server" e clique ENTER.

<img class="aligncenter size-full wp-image-771" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-023.png" alt="homelaber-instalacao-ubuntu-server-homelab-023" width="905" height="666" />

Selecione a lingua do SO e clique Enter

<img class="aligncenter size-full wp-image-772" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-024.png" alt="homelaber-instalacao-ubuntu-server-homelab-024" width="905" height="666" />

Selecione a sua localização e tecle Enter.
<img class="aligncenter size-full wp-image-773" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-025.png" alt="homelaber-instalacao-ubuntu-server-homelab-025" width="905" height="666" />

Selecione o layout do seu teclado. Aqui você pode escolher a opção default, pois na próxima tela o sistema irá fazer a identificação automática.

<img class="aligncenter size-full wp-image-774" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-026.png" alt="homelaber-instalacao-ubuntu-server-homelab-026" width="905" height="666" />

Selecione YES e clique enter.

<img class="aligncenter size-full wp-image-775" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-027.png" alt="homelaber-instalacao-ubuntu-server-homelab-027" width="905" height="666" />

Digite as teclas informadas para que o sistema identifique o layout do seu teclado.
<img class="aligncenter size-full wp-image-776" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-028.png" alt="homelaber-instalacao-ubuntu-server-homelab-028" width="905" height="666" />

<img class="aligncenter size-full wp-image-777" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-029.png" alt="homelaber-instalacao-ubuntu-server-homelab-029" width="905" height="666" />

Selecione "Continue" e aperte ENTER.

<img class="aligncenter size-full wp-image-778" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-030.png" alt="homelaber-instalacao-ubuntu-server-homelab-030" width="905" height="666" />

A instalação de fato irá iniciar... seja paciente :)

<img class="aligncenter size-full wp-image-779" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-031.png" alt="homelaber-instalacao-ubuntu-server-homelab-031" width="905" height="666" />

Chegou a hora de configurar a rede. Digite o hostname desejado. Esse será o nome da sua maquina.

<img class="aligncenter size-full wp-image-780" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-032.png" alt="homelaber-instalacao-ubuntu-server-homelab-032" width="905" height="666" />

Digite no nome do administrador do sistema. Pode ser qualquer nome. Eu costumo usar um padrão "administrator" - original não? :)

<img class="aligncenter size-full wp-image-781" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-033.png" alt="homelaber-instalacao-ubuntu-server-homelab-033" width="905" height="666" />

Digite o nome do usuário. Aqui vai uma vez a critividade impera e uso "administrator".

<img class="aligncenter size-full wp-image-782" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-034.png" alt="homelaber-instalacao-ubuntu-server-homelab-034" width="905" height="666" />

Chegou a hora de escolher a senha do usuário administrador. Escolha uma senha que você irá se lembrar ou anote. Depois para recuperar da um trabalho enorme.

<img class="aligncenter size-full wp-image-783" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-035.png" alt="homelaber-instalacao-ubuntu-server-homelab-035" width="905" height="666" />

Repita a senha do administrador.

<img class="aligncenter size-full wp-image-784" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-036.png" alt="homelaber-instalacao-ubuntu-server-homelab-036" width="905" height="666" />

Nessa tela é feita a pergunta se você quer encriptar o diretório home. Eu sempre respondo "Não".

<img class="aligncenter size-full wp-image-785" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-037.png" alt="homelaber-instalacao-ubuntu-server-homelab-037" width="905" height="666" />

Aguarde a instalação...

<img class="aligncenter size-full wp-image-786" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-038.png" alt="homelaber-instalacao-ubuntu-server-homelab-038" width="905" height="666" />

Selecione a sua localização para ajustes do relógio.

<img class="aligncenter size-full wp-image-787" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-039.png" alt="homelaber-instalacao-ubuntu-server-homelab-039" width="905" height="666" />

Essa é a hora de escolher o tipo de partição do disco. Escolha a opção selecionada na figura abaixo.

<img class="aligncenter size-full wp-image-788" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-040.png" alt="homelaber-instalacao-ubuntu-server-homelab-040" width="905" height="666" />

&nbsp;

<img class="aligncenter size-full wp-image-789" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-041.png" alt="homelaber-instalacao-ubuntu-server-homelab-041" width="905" height="666" />

Selecione YES e clique ENTER para prosseguir.

<img class="aligncenter size-full wp-image-790" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-042.png" alt="homelaber-instalacao-ubuntu-server-homelab-042" width="905" height="666" />

Selecione "Continue" e tecle ENTER.

<img class="aligncenter size-full wp-image-791" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-044.png" alt="homelaber-instalacao-ubuntu-server-homelab-044" width="905" height="666" />

Selecione YES para escrever as alterações no disco e continuar com a instalação.

<img class="aligncenter size-full wp-image-792" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-045.png" alt="homelaber-instalacao-ubuntu-server-homelab-045" width="905" height="666" />

Aguarde o particionamento dos discos...

<img class="aligncenter size-full wp-image-793" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-046.png" alt="homelaber-instalacao-ubuntu-server-homelab-046" width="905" height="666" />

E agora mais uma vez... a instalação dos arquivos!

<img class="aligncenter size-full wp-image-794" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-047.png" alt="homelaber-instalacao-ubuntu-server-homelab-047" width="905" height="666" />

Se você utilizar um servidor Proxy para saída de internet (provavelmente não), coloque as informações aqui. Caso contrário, deixe em branco, selecione "Continue" e aperte ENTER.

<img class="aligncenter size-full wp-image-795" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-048.png" alt="homelaber-instalacao-ubuntu-server-homelab-048" width="905" height="666" />

Mais um pouquinho....

<img class="aligncenter size-full wp-image-796" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-049.png" alt="homelaber-instalacao-ubuntu-server-homelab-049" width="905" height="666" />

Nessa tela, selecione "No automatic updates" Dessa forma o servidor não irá fazer updates de software automaticamente, o que pode ser um problema caso você vá rodar uma versão especifica de um sistema. O melhor é atualizar manualmente.

<img class="aligncenter size-full wp-image-797" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-050.png" alt="homelaber-instalacao-ubuntu-server-homelab-050" width="905" height="666" />

Nessa tela, você tem a opção de selecionar quais softwares ou sistemas deseja instalar. Marque apenas a opção "OpenSSH Server". Dessa forma você poderá acessar o sistema remotamente via <a href="http://www.putty.org/" target="_blank">Putty</a> e posteriormente instalar o software que desejar.

<img class="aligncenter size-full wp-image-798" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-051.png" alt="homelaber-instalacao-ubuntu-server-homelab-051" width="905" height="666" />

Aguarde a instalação dos pacotes...

<img class="aligncenter size-full wp-image-799" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-052.png" alt="homelaber-instalacao-ubuntu-server-homelab-052" width="905" height="666" />

Na próxima tela, selecione YES e tecle ENTER. Você irá instalar o GRUB, o sistema de boot do Linux.

<img class="aligncenter size-full wp-image-800" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-053.png" alt="homelaber-instalacao-ubuntu-server-homelab-053" width="905" height="666" />

Pronto! A instalação terminou. Selecione "Continue" e clique enter. A VM irá reiniciar e o seu servidor Linux Ubuntu estará instalado.
<img class="aligncenter size-full wp-image-802" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-055.png" alt="homelaber-instalacao-ubuntu-server-homelab-055" width="905" height="666" />

Esse é o prompt inicial do Linux. Entre com o seu login e senha (o qual você definiu durante a instalação - eu falei para guardar!).

<img class="aligncenter size-full wp-image-803" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-056.png" alt="homelaber-instalacao-ubuntu-server-homelab-056" width="905" height="666" />

Ai está! Você acabou de criar e instalar uma VM com o sistema operacional Linux Ubuntu Server. A partir de agora, você poderá instalar outros softwares como um webserver, um proxy (veja como no post) e muito mais.

<img class="aligncenter size-full wp-image-804" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/homelaber-instalacao-ubuntu-server-homelab-057.png" alt="homelaber-instalacao-ubuntu-server-homelab-057" width="905" height="666" />

Minhas recomendações a partir daqui são

<ol>
<li>Executar o comandos abaixo para atualizar o sistema</li>
</ol>

<pre class="lang:default decode:true ">sudo su - para ganhar acesso root na máquina
apt-get update - para fazer o check dos repositórios
apt-get upgrade - para fazer a atualização dos pacotes instalados.</pre>

<ol>
<li>Instalar o VMware Tools para Linux seguindo esse post</li>
</ol>

Viu só... não doeu nada :). Hoje em dia, instalar o Linux Ubuntu Server em uma VMware é super rápido e fácil. Se você NUNCA mexeu com Linux antes, vou deixar alguns links com comandos básicos para você ir treinando. Recomendo muito, buscar mais informações, tutoriais no Youtube, livros, etc. O Google é o seu melhor amigo :).

Nos próximos posts, irei mostar como instalar alguns sistemas e servidores e esse post é a base para isso.

Referências:

[su_note radius="0"]

<a href="http://www.ic.unicamp.br/~mc102/aulas/laboratorio/comandos_basicos_linux.pdf" target="_blank">Comandos básicos do Linux - via Instituto Computação Unicamp</a>

<a href="http://www.vivaolinux.com.br/dica/Comandos-basicos-para-iniciantes" target="_blank">Comandos básicos para iniciantes - via Viva o Linux</a>

<a href="http://wiki.ubuntu-br.org/ComandosBasicos" target="_blank">Comandos Básicos - via Wiki Ubuntu.org</a>

[/su_note]

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.

Estamos participando do desafio <a href="http://homelaber.com.br/desafio-vdm30in30/">#vDM30in30</a>. Acompanhe no <a href="https://twitter.com/search?q=%23vDM30in30">twitter</a>.