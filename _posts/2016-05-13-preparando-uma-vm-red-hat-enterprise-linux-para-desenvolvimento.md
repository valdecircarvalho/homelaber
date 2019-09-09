---
ID: 1425
post_title: >
  Preparando uma VM Red Hat Enterprise
  Linux para Desenvolvimento
author: Alexandre Parreira
post_excerpt: ""
layout: post
permalink: http://bit.ly/1TaobKC
published: true
post_date: 2016-05-13 00:36:09
---
<strong><img class="alignnone size-medium wp-image-1527" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/open-source-300x209.jpg" alt="ale-open-source" width="300" height="209" /></strong>

Olá Homelabers!

Neste artigo de estréia pretendo apresentar um guia para a preparação de uma VM com o Red Hat para desenvolvimento em múltiplas plataformas.

Esta VM deve servir de base para outros artigos onde entraremos nos detalhes mais específicos no desenvolvimento de aplicações.

<strong>Nível</strong>: <strong><span style="text-decoration: underline; color: #0000ff;">Fácil</span>.</strong>

<!--more-->

A idéia a produzir uma série modular de artigos de forma que, dependendo do objetivo de utilização, somente os componentes necessários sejam abordados.

Não poderia deixar de agradecer e cumprimentar o Valdecir Carvalho pelo convite e iniciativa.

<h3>Sobre o RHEL</h3>

Escolhi utilizar o RHEL pois é uma das distribuições mais sólidas e utilizadas no ambiente corporativo. Algumas plataformas estão homologadas para rodarem sobre ele o que garante um suporte adequado. É claro que podemos sempre usar outras distribuições porém, por experiência, algumas precisam de alguns truques extras para executar adequadamente alguns componentes.

Com a liberação de uma versão gratuita para desenvolvedores pela Red Hat, conforme publicado <a href="http://homelaber.com.br/red-hat-lanca-versao-de-desenvolvedor-do-rhel-gratis/">aqui</a> neste blog, não vejo motivos para não se aprofundar na sua utilização, agora de maneira bem legal.

<h3>Virtual Machine</h3>

Utilizarei neste artigo o <a href="https://www.vmware.com/products/workstation/">VMware</a> que é um produto de ponta no mercado de virtualização. No entanto a VM pode também ser criada utilizando <a href="https://www.virtualbox.org/">Oracle VM VirtualBox</a>.

<h3>Recursos do Host</h3>

Estou utilizando um notebook Lenovo T430 com windows 7 conforme abaixo:

<img class="alignnone wp-image-1430 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/espec-lenovo-t430.png" width="493" height="119" />

É importante também saber quantos cores possui seu processador para poder dimensionar melhor a utilização de recursos na VM. No caso do Windows 7 podemos utilizar o aplicativo <em><strong>msinfo32.exe</strong> </em>e obter a informação conforme abaixo:

<img class="alignnone wp-image-1435 " src="http://homelaber.com.br/site/wp-content/uploads/2016/05/espec-lenovo-t430-2-1.png" alt="ale-espec-lenovo-t430-2" width="722" height="203" />

Neste caso temos 2 núcleos (cores).

Dependendo do objetivo da VM pode ser necessário consumir mais ou menos recursos do Host. Neste cenário o Host é o SO instalado na máquina (Windows 7) e o Guest é o que será instalado na VM (RHEL).

<h3>Començando</h3>

Vamos criar uma nova VM:

<img class="alignnone wp-image-1438 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-1.png" alt="ale-new-vm-1" width="564" height="310" />

No diálogo Escolha <em><strong>Custom </strong></em>e clique em <em><strong>Next</strong></em>.

Deixe <em><strong>Hardware compatibility</strong></em> na opção default selecionada e clique em <em><strong>Next</strong></em>.

Após vamos selecionar a última opção para instalar o SO depois evitando que o VMware tome algumas decisões importantes por nós.

<img class="alignnone wp-image-1463 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-15.png" alt="ale-new-vm-15" width="432" height="398" />

Clique em <strong><em>Next</em></strong>.

Escolha um nome e local onde serão armazenados os arquivos da VM.

<img class="alignnone wp-image-1450 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-4-1.png" alt="ale-new-vm-4" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Vamos agora escolher o número de CPU disponibilizados para o Guest SO. Para mais informações sobre vCPUs acesse este <a href="http://pubs.vmware.com/fusion-6/index.jsp#com.vmware.fusion.help.doc/GUID-065E8496-4320-4A54-B1B8-F40C84CA8DAF.html">link</a>.

<img class="alignnone wp-image-1451 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-4b.png" alt="ale-new-vm-4b" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Agora vamos definir a quantidade de memória RAM estará disponível para o Guest. No meu caso vou utilizar o mais recomendado de 8 GB. Novamente esta quantidade pode variar conforme o objetivo da VM. E isto pode ser modificado futuramente.

<img class="alignnone wp-image-1453 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-6.png" alt="ale-new-vm-6" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Deixaremos as configurações de rede no default. Futuramente, se tivermos necessidades específicas para o Guest como por exemplo possuir endereço de IP específico permitindo funcionar como servidor e até mesmo consumir serviços do Host, podemos mudar para o modo Bridged por exemplo.

<img class="alignnone wp-image-1455 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-8.png" alt="ale-new-vm-8" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Nos dois próximos passos vamos também deixar o default.

<img class="alignnone wp-image-1456 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-9.png" alt="ale-new-vm-9" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

<img class="alignnone wp-image-1457 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-10.png" alt="new-vm-10" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Agora vamos criar um novo disco virtual. Obviamente caso tivéssemos um disco criado e se estivemos movendo imagens de uma máquina para outra poderíamos utilizar as outras opções.

<img class="alignnone wp-image-1458 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-11.png" alt="ale-new-vm-11" width="432" height="398" />

Vamos agora escolher o tamanho do disco que estará disponível para a VM. Como eu tenho uma idéia de minhas necessidades futuras eu vou começar com <em><strong>50 GB</strong></em> mas o default é <em><strong>20 GB</strong></em>. Dependendo da distribuição Linux sendo instalada a necessidade de espaço em disco pode ser muito menor.

Vamos também optar por armazenar em um único arquivo. No cenário projetado não há motivo por dividir em múltiplos arquivos. Casos específicos indicados para a divisão seriam os quais se está utilizando um sistema com limitação no tamanho máximo dos arquivos, como FAT32, ou se projetarmos discos a partir de 100 GB onde poderíamos começar a visualizar uma melhoria na performance.

Um outro ponto importante é que vamos escolher já alocar todo o espaço em disco informado (50 GB) para a VM. Por experiência posso dizer que alguns SO instalam corretamente porém, algumas instalações de componentes falham ao detectar o tamanho total do disco. Por isso é <span style="text-decoration: underline;"><strong>muito importante</strong></span> já alocar o espaço total do disco.

Há um post aqui no blog falando sobre estas opções <a href="http://homelaber.com.br/back-to-basics-diferencas-entre-tipos-de-disco-em-uma-vm-thin-vs-thick-provision/">aqui</a>.

<img class="alignnone wp-image-1459 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-12.png" alt="ale-new-vm-12" width="432" height="398" />

Clique em <em><strong>Next</strong></em>.

Depois confirme o nome do arquivo a ser criado e clique em <em><strong>Next</strong></em>.

<img class="alignnone wp-image-1460 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-13.png" alt="ale-new-vm-13" width="432" height="398" />

Pronto as configurações da nova VM estão definidas e vamos agora avançar para a instalação do RHEL como Guest SO na VM. Como definimos para alocar todo o tamanho do disco na criação o processo irá demorar um pouco mais.

<img class="alignnone wp-image-1461 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/new-vm-14.png" alt="ale-new-vm-14" width="432" height="398" />

Clique em <em><strong>Finish</strong></em>.

<h3>Instalando o RHEL</h3>

Após a criação da VM estaremos com ela limpa para iniciar a instalação do RHEL.

No lado direto da janela clique em <em><strong>CD/DVD (SATA)</strong></em>.

<img class="alignnone wp-image-1468 " src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-1.png" alt="ale-install-vm-1" width="702" height="444" />

Agora vamos marcar a opção <em><strong>Use ISO image file</strong></em> e vamos selecionar a ISO que baixamos do site da Red Hat.

<img class="alignnone wp-image-1470 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-2.png" alt="ale-install-vm-2" width="694" height="620" />

Clique em <em><strong>OK</strong></em>.

Vamos iniciar a VM clicando em <em><strong>Power on this virtual machine</strong></em>.

A VM irá inicializar a partir da imagem ISO montada na unidade de CD/DVD. Vamos selecionar a primeira opção para instalar o RHEL na VM. Para direcionar o input para a janela da VM basta clicar dentro da janela ou pressionar CTRL + G.

<img class="alignnone wp-image-1471 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-3.png" alt="ale-install-vm-3" width="660" height="608" />

Pressione <em><strong>Enter</strong> </em>para começar o processo de instalação.

Vamos manter a linguagem selecionada em <em><strong>English (United States)</strong></em>. Esta é uma preferência pessoal e vocês podem ajustar conforme sua preferência.

<img class="alignnone wp-image-1472 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-4.png" alt="ale-install-vm-4" width="738" height="655" />

Vamos diretamente configurar a <em><strong>Network &amp; Host Name</strong></em> para permitirmos que a definição dos parâmetros de instalação possa já obter dados da internet.

<img class="alignnone wp-image-1476 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-5.png" alt="ale-install-vm-5" width="795" height="657" />

Dependendo do hardware que está disponível estas opções podem ser diferentes. Porém, em um ambiente básico estará disponível um adaptador de rede selecionado e vamos ativá-lo clicando no botão <em><strong>ON/OFF</strong></em> no canto superior direito.

<img class="alignnone wp-image-1477 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-6.png" alt="ale-install-vm-6" width="795" height="657" />

Após a ativação do adaptador de rede a VM deverá receber um endereço de IP e estar conectada à rede e internet.

Clique em <em><strong>Done</strong> </em>no campo superior esquerdo da janela.

Vamos clicar em <em><strong>Date &amp; Time</strong></em>.

Nesta janela selecione a posição de seu fuso horário clicando no posição no mapa e se necessário selecionando nas caixas superiores a região e cidade exatas. Vamos ativar também a opção Network Time para manter o horário atualizado com os servidores mundiais.

<img class="alignnone wp-image-1479 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-7.png" alt="ale-install-vm-7" width="795" height="657" />

Vamos agora configurar o teclado. Para tanto clique em <em><strong>Keyboard</strong></em>.

Na janela seguinte vamos clicar no símbolo <em><strong>+</strong></em> no canto inferior esquerdo para adicionar um novo layout.

Na lista busque por <em><strong>Portuguese (Brazil)</strong></em> e clique em Add.

Remova o layout <em><strong>English (US)</strong></em> clicando no sinal de <em><strong>-</strong></em> no canto inferior esquerdo.

<img class="alignnone wp-image-1487 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-8.png" alt="ale-install-vm-8" width="795" height="657" />

Sugiro testar o layout escolhido para evitar alguma dor de cabeça e trabalho adicional logo de início. Utilize a caixa <em><strong>Test...</strong></em> no canto superior direito para testar especialmente as teclas <strong>/ \ . : | - _ ?</strong>

Clique em <em><strong>Done</strong> </em>após terminar.

Vamos agora definir os softwares a serem instalados.

Cliquem em <em><strong>Software Selection</strong></em>.

Na caixa da esquerda, <em><strong>Base Environment</strong></em>, selecione <em><strong>Server with GUI</strong></em>. Desta forma teremos um sistema gráfico para trabalhar com o desenvolvimento de softwares.

Após selecionar a opção acima, na caixa da direita <em><strong>Add-Ons for Selected Environment</strong></em>, localize e marque a opção KDE. Assim terá a opção de usar o Gnome ou KDE, duas interfaces gráficas diferentes, conforme sua preferência.

<img class="alignnone wp-image-1489 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-9.png" alt="ale-install-vm-9" width="795" height="657" />

Clique em <em><strong>Done</strong></em>.

Vamos por fim definir as configurações de particionamento dos discos.

Clique em <em><strong>Installation Destination</strong></em>.

Basta clicar em <em><strong>Done</strong> </em>para confirmar o particionamento automático do disco.

<img class="alignnone wp-image-1490 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-10.png" alt="ale-install-vm-10" width="795" height="657" />

Após todos estas definições estamos prontos para prosseguir com instalação.

Clique em <em><strong>Begin Installation</strong></em>.

Enquanto o sistema é instalado vamos aproveitar e definir as senhas de Root e um usuário para acesso.

Clique em <em><strong>ROOT PASSWORD</strong></em> para definir a senha do <em><strong>ROOT</strong></em>.

<img class="alignnone wp-image-1491 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-11.png" alt="ale-install-vm-11" width="795" height="657" />

Clique em <em><strong>Done</strong></em>. Talvez seja necessário clicar 2 vezes para confirmar caso a senha seja considerada fraca.

Clique em <em><strong>USER CREATION</strong></em> para criar o seu usuário para acesso.

<img class="alignnone wp-image-1492 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-12.png" alt="ale-install-vm-12" width="795" height="657" />

Clique em <em><strong>Done</strong></em>. Talvez seja necessário clicar 2 vezes para confirmar caso a senha seja considerada fraca.

Vamos aguardar o término da instalação.

<h3>Iniciando o Sistema</h3>

Ao término da instalação clique em <em><strong>Reboot</strong> </em>no canto inferior esquerdo para reinicializar o sistema.

<img class="alignnone wp-image-1494 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-13.png" alt="ale-install-vm-13" width="795" height="657" />

Após a reinicialização o sistema nos solicita a escolher a opção de inicialização.

Vamos escolher a <em><strong>primeira opção</strong></em> e teclar <em><strong>Enter</strong></em>.

<img class="alignnone wp-image-1495 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-14.png" alt="ale-install-vm-14" width="740" height="528" />

Após a inicialização será necessário ainda informar a informações de licença.

Clique em <em><strong>LICENSE INFORMATION</strong></em>.

<img class="alignnone wp-image-1496 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-15.png" alt="ale-install-vm-15" width="772" height="474" />

Recomendamos analisar as informações quanto as direitos e deveres estabelecidos e contratados.

Quando estiver ponto marque a caixa <em><strong>I accept the license agreement</strong></em> no canto inferior esquerdo para aceitar os termos apresentados, caso esteja de acordo. Após, clique em <em><strong>Done</strong> </em>no canto superior direito.

Deixaremos o ítem <em><strong>Subscription Manager</strong></em> não registrado por enquanto pois precisaremos efetuar alguns ajustes mais a frente para realizar o assinatura e usufruir do suporte e atualizações oficiais.

Clique em <em><strong>Finish Configuration</strong></em> no canto inferior direito para prosseguir.

Neste momento devemos ser levados à tela inicial de login. Clique no nome de seu usuário, informe a senha cadastrada.

<img class="alignnone wp-image-1497 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-17.png" alt="ale-install-vm-17" width="765" height="414" />

Já na área de trabalho  serão apresentados informativos educativos porém, podemos fechar e acessar estas informações a qualquer momento posteriormente para aprender mais sobre o ambiente e sua operação.

<img class="alignnone wp-image-1498 size-full" src="http://homelaber.com.br/site/wp-content/uploads/2016/05/install-vm-18.png" alt="install-vm-18" width="788" height="610" />

Pronto, nossa instalação básica está completa.

Foi um longo caminho até aqui. Temos agora um ambiente inicial para começar a desenvolver nossos projetos sobre uma plataforma robusta, aceita e certificada pelo mercado.

<em><strong>Considerações Finais</strong></em>

Temos alguns ajustes pós instalação que serão importantes para uma melhor usabilidade do ambiente. Estes serão apresentados em um novo artigo.

Gostaria de agradecer a todos por acompanharem aqui.

Dúvidas e questionamentos não hesitem em postar no comentários que na medida do possível tentarei responder a todas ou buscar mais informações no intuito de ajudar na resolução.

Desejo desde já paz e sucesso a todos em suas jornadas de estudos e evolução.

Grande abraço.