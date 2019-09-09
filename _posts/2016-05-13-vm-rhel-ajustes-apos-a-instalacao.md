---
ID: 1536
post_title: 'VM RHEL &#8211; Ajustes após a instalação'
author: Alexandre Parreira
post_excerpt: ""
layout: post
permalink: http://bit.ly/1XoUvsT
published: true
post_date: 2016-05-13 10:52:32
---
<strong><img class="alignnone size-medium wp-image-1527" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/open-source-300x209.jpg" alt="ale-open-source" width="300" height="209" /></strong>

Olá Homelabers!

Neste post vamos ver alguns ajustes pós instalação da VM RHEL para Desenvolvimento.

<strong>Nível</strong>: <strong><span style="text-decoration: underline; color: #0000ff;">Fácil</span>.</strong>

<!--more-->

Este artigo se baseia na VM criada no artigo anterior da série:

<a href="http://homelaber.com.br/preparando-uma-vm-red-hat-enterprise-linux-para-desenvolvimento/">Preparando uma VM Red Hat Enterprise Linux para Desenvolvimento</a>.

Após a instalação inicial do RHEL na VM temos alguns ajustes que são importantes e alguns que são meros caprichos, mas por que não...

<h3>Conexão com a Internet</h3>

Confirme se a conexão com a internet está ativa.

Clique na setinha para baixo no canto superior direito e verifique se está conectado.

<img class="alignnone wp-image-1538 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/rede-1.png" alt="ale-vm-rede-1" width="479" height="411" />

<h3>Ativação do RHEL</h3>

Como utilizamos uma versão de desenvolvedor do Linux Red Hat Enterprise vamos ativar a instalação e assim usufruir das atualizações e repositórios oficiais da Red Hat.

<img class="alignnone wp-image-1539 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/vm-rede-2.png" alt="vm-rede-2" width="728" height="441" />

Informe a senha do <em><strong>root</strong></em>.

<img class="alignnone wp-image-1541 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-register.png" alt="ale-vm-register" width="737" height="597" />

Clique em <em><strong>Registrar</strong></em>.

<img class="alignnone wp-image-1542 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-register-2.png" alt="ale-vm-register-2" width="737" height="597" />

Verifique se precisa inserir informações do proxy e autenticação.

Clique em <em><strong>Próximo</strong></em>.

Informe o usuário e senha utilizados para acessar sua conta de desenvolvedor em <a href="http://developers.redhat.com">http://developers.redhat.com</a>.

Clique em <em><strong>Registrar</strong></em>.

Confirme a subscrição clicando em <em><strong>Conectar</strong></em>.

<img class="alignnone wp-image-1543 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-register-3.png" alt="ale-vm-register-3" width="737" height="597" />

Pronto seu sistema deve estar registrado.

<img class="alignnone wp-image-1544 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-register-4.png" alt="ale-vm-register-4" width="737" height="597" />

<em><strong>Registrando seu usuário no grupo de sudoers</strong></em>

No Linux diversas tarefas demandam que sejam executadas com privilégios elevados. É uma das proteções mais famosas do sistema que, em conjunto com diversas outras definições e arquitetura, tornam o sistema muito seguro (não totalmente, isso não existe).

Então, quando formos executar tarefas com esta demanda, podemos utilizar o <em><strong>sudo</strong> </em>para conferir temporariamente estes privilégios ao nosso user. Ao término, os privilégios normais do usuário voltam ao normal.

No RHEL, para que nosso usuário possa utilizar este comando e executar as tarefas com privilégios elevados, precisamos incluí-lo no arquivo <em><strong>/etc/sudoers.</strong></em>

Existem formas diferentes de fazer isto. Aqui vamos usar o programa <em><strong>visudo</strong></em>.

Abra um janela do terminal e digite o texto abaixo seguido <em><strong>ENTER</strong></em>:

<pre class="lang:default decode:true">sudo visudo</pre>

Informe a <em><strong>senha do root</strong></em> definida no processo de instalação.

o aplicativo visudo é uma versão especial do vim que permite editar o arquivo <em><strong>/etc/sudoers</strong></em> de forma segura e evita termos que mexer nas permissões originais do arquivo.

Localize a linha contando o texto <em><strong>root   ALL=(ALL)   ALL</strong></em>.

Aperte a letra<em><strong> i</strong></em> no teclado para inserir novo texto. Insera uma linha logo abaixo de root contendo o nome de seu usuário e o restante permanece igual ao configurado para o root.

Veja como deve ficar abaixo.

<img class="alignnone wp-image-1546 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-sudoers-1.png" alt="ale-vm-sudoers-1" width="711" height="653" />

Após terminar a edição aperte <em><strong>ESC</strong></em>. O programa sairá do modo de edição.

Aperte <em><strong>:</strong></em> para entrar no modo de comando e digite <em><strong>wq</strong></em> e pressione <em><strong>ENTER</strong></em>. O arquivo será salvo e o programa encerrado.

Pronto. Agora sempre que precisarmos de permissões elevados podemos utilizar o seguinte formado de comando:

<pre class="lang:default decode:true">sudo [comando]</pre>

Sempre informando a senha do root a cada execução.

<h3>Atualizando o sistema</h3>

Mesmo após uma instalação nova é recomendável fazer uma atualização no sistema.

É importante que o passo de registro da instalação tenha sido efetuado para podermos utilizar os repositórios oficiais da Red Hat.

Para atualizar o sistema utilize o seguinte comando:

<pre class="lang:default decode:true ">sudo yum update</pre>

Serão atualizadas todas as informações dos pacotes e atualizações serão automaticamente selecionadas conforme suas dependências.

O programa pedirá sua confirmação antes de atualizar. Digite <em><strong>Y</strong></em> quando solicitado seguido de <em><strong>ENTER</strong></em>.

Aguarde pois o processo todo pode demorar um pouco.

<h3>Criando um atalho de teclado para abrir uma janela do terminal</h3>

Frequentemente utilizamos o terminal para executar diversas tarefas. É mais rápido, prático e eficiente.

Vamos criar um atalho de teclado para tornar a tarefa de abrir uma nova janela mais fácil do que ter que navegar no menu até o aplicativo do terminal.

Clique no menu <em><strong>Aplicativos &gt; Sistema &gt; Configurações</strong></em>.

<img class="alignnone wp-image-1549 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-hotkey-1.png" alt="ale-vm-hotkey-1" width="711" height="653" />

Localize o ítem <em><strong>Teclado</strong> </em>e clique duas vezes para abrir.

Na janela selecione a aba <em><strong>Atalhos</strong></em>.

Clique na sinal de <em><strong>+</strong></em> mais abaixo na janela para adicionar um novo atalho.

De o nome de <em><strong>Terminal</strong> </em>e em comando coloque <em><strong>/usr/bin/gnome-terminal</strong></em>.

<img class="alignnone wp-image-1550 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-hotkey-2.png" alt="ale-vm-hotkey-2" width="711" height="653" />

Clique em <em><strong>Adicionar</strong></em>.

Após adicionar o atalho ele aparecerá no final da lista da esquerda, em <em><strong>atalhos personalizados</strong></em>.

Selecione o atalho criado e vamos agora definir a combinação de teclas para ativação.

Clique uma vez sobre o texto <em><strong>Desativado </strong></em>para iniciar o modo de captura de teclas.

Agora você pode definir a combinação que desejar. Uma combinação muito usada para abertura rápida de terminal é CTRL+ALT+T, porém eu prefiro usar SUPER+T (ou WIN+T ou CMD+T).

Execute a combinação de teclas e ela será armazenada automaticamente.

<img class="alignnone wp-image-1551 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-hotkey-3.png" alt="ale-vm-hotkey-3" width="690" height="588" />

Pode fechar a janela e teste o comando pressionando <em><strong>SUPER+T</strong></em> no teclado.

<h3>Instale o Google Chrome.</h3>

O Firefox já vem instado como navegador padrão. Para quem prefere o Chrome segue o passo a passo:

Para instalar abra uma janela do terminal usando <strong><em>SUPER+T</em></strong>.

Adicione o repositório da Google usando o comando abaixo:

<pre class="lang:default decode:true ">sudo vim /etc/yum.repos.d/google-chrome.repo</pre>

Aperte i para acionar o modo inserção e copie e cole usando <em><strong>CTRL+SHIFT+V</strong></em> o código abaixo:

<pre class="lang:default decode:true">[google-chrome]
name=google-chrome
baseurl=http://dl.google.com/linux/chrome/rpm/stable/$basearch
enabled=1
gpgcheck=1
gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub</pre>

Aperte <strong>ESC</strong> para sair do modo de inserção. Tecle <em><strong>:wq</strong></em> para salvar e sair.

Utilize o comando a seguir para instalar o Chrome:

<pre class="">sudo yum install google-chrome-stable</pre>

Confirme com <em><strong>s</strong></em> ou <em><strong>y</strong></em> em todas as perguntas.

Ao término o Chome deve estar disponível no menu em <em><strong>Aplicativos &gt; Internet</strong></em>.

<h3>Instale o repositório EPEL</h3>

O EPEL - Extra Packages for Enterprise Linux - é um repositório repleto de pacotes extras mantidos pela comunidade. É muito grande a chance de quando estiver testando e estudando algumas coisas no futuro você precise de algo que esteja disponível neste repositório.

Para instalar utilize o terminal (SUPER+T) e insira os seguintes comandos:

<pre class="lang:default decode:true"># crie uma pasta em sua home
cd ~
mkdir tmp
cd tmp
# baixe o RPM
sudo wget http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-6.noarch.rpm
# instale
sudo rpm -ivh epel-release-7-6.noarch.rpm
# remova a pasta temporaria
rm -rf tmp</pre>

<h3>Configure uma pasta compartilhada com o Host (Shared Folder)</h3>

A configuração de uma pasta compartilhada com o Host permite a troca de arquivos entre o Host e o Guest. Isto é muito útil quando estamos estudando e precisamos trocar arquivos entre VMs específicas.

Para configurar a pasta compartilhada vá nas configurações da VM (<em><strong>VM &gt; Settings</strong></em>), na aba <em><strong>Options</strong> </em>e selecione o ítem <em><strong>Shared Folders</strong></em>.

Na direita selecione <strong><em>Always enabled</em></strong> e clique em <em><strong>Add</strong></em>.

<img class="alignnone wp-image-1558 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-shared-folder1.png" alt="ale-vm-shared-folder1" width="625" height="558" />

Selecione <em><strong>Next</strong> </em>e após clique em <em><strong>Browse </strong></em>para selecionar a pasta no Host que será compartilhada.

<img class="alignnone wp-image-1559 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-shared-folder2.png" alt="ale-vm-shared-folder2" width="432" height="375" />

Clique em <em><strong>Next</strong> </em>e deixe marcado <em><strong>Enable this share</strong></em>.

Clique em <em><strong>Finish</strong></em>.

<img class="alignnone wp-image-1560 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/ale-vm-shared-folder3.png" alt="ale-vm-shared-folder3" width="432" height="375" />

Dependendo do estado da máquina e do Guest SO instalado você pode obter um erro pois o VMware vai tentar "montar" a pasta automaticamente.

<em><strong>Fim</strong></em>

Por enquanto é só pessoal. Irei atualizar este post conforme outros ítens forem necessários / indicados.

Paz e sucesso a todos!