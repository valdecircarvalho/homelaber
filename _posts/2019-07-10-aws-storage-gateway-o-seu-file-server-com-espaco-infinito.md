---
ID: 5574
post_title: 'AWS Storage Gateway &#8211; O seu file server com espaço infinito'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2LKOCHW
published: true
post_date: 2019-07-10 07:30:31
---
Olá Homelabers!

Hoje vou falar sobre um produto da Amazon AWS que tenho estudado recentemente para resolver um problema na FIRMA, o<strong> AWS Storage Gateway</strong>, um serviço de armazenamento híbrido que permite que aplicativos locais tenham acesso - transparente - aos serviços de armazenamento na nuvem da AWS.

Nesse post vou mostrar <strong>como instalar e configurar um gateway no seu ambiente VMware vSphere para ser usado como um File Server</strong>.
<h2>AWS Storage Gateway</h2>
<strong>O AWS Storage Gateway pode ser usado, basicamente de 3 maneiras diferentes</strong>:

<strong>File Gateway</strong> - Na modalidade File Gateway, você tem disponível um share NFS/SMB onde pode salvar e compartilhar seus arquivos de uma forma transparece. Os arquivos "quentes" ficam gravados em um cache local - com tamanho mínimo de 250GB - e os arquivos são automaticamente enviados para um bucket S3 na AWS. Dessa maneira, você tem disponível um File Server com espaço "INFINITO".

<strong>Volume Gateway</strong> - Na modalidade Volume Gateway, você tem disponível um volume iSCSI como se fosse um storage normal, esse volume pode ser apresentado para suas aplicações - hypervisor, VM, etc ou mesmo para um storage. O Volume Gateway mantém um cache dos dados acessados recentemente ou uma cópia completa do volume no local.

<strong>Tape Gateway</strong> - Na modalidade Tape Gateway, você tem disponível um sistema de BIBLIOTECA DE FITAS VIRTUAIS, ou seja, você pode aposentar o seu robô de fita LTO e passar a usar o Tape Gateway como um target no seu sistema de backup.

Para testar alguns cenários, eu subi uma instância do AWS Storage Gateway no meu lab e vou mostrar a vocês, como é simples de configurar e usar.
<h2>Como instalar e configurar AWS Storage Gateway no VMware vSphere</h2>
<h3><img class="aligncenter size-large wp-image-5579" src="http://homelaber.com.br/site/wp-content/uploads/2019/07/file-gateway-concepts-diagram-644x176.png" alt="" width="644" height="176" /></h3>
<h3>O que você vai precisar:</h3>
<ul style="list-style-type: square;">
 	<li>Ambiente Virtualizado - Você pode utilizar o VMware vSphere ou o Microsoft Hyper-V ou até mesmo o Virtualbox =)</li>
 	<li>Conta na AWS</li>
 	<li>Virtual Appliance do AWS Storage Gateway</li>
</ul>
<h3>Criando o Storage Gateway na AWS:</h3>
<ul style="list-style-type: square;">
 	<li>Acesse o console da AWS e procure o serviço AWS Storage Gateway - https://console.aws.amazon.com/storagegateway/</li>
 	<li>Clique em Get Started</li>
 	<li>Selecione File Gateway</li>
 	<li>Seleciona a sua plataforma, no nosso caso vamos utilizar o VMware vSphere</li>
 	<li>Faça o Download do Virtual Appliance</li>
</ul>
Agora vamos deixar o console da AWS e fazer o deploy do Virtual Appliance no VMware vSphere. O deploy é bastante simples, como qualquer outro OVA, mas existe um ponto de atenção: O Virtual Appliance é criado com apenas um disco de sistema, e você vai precisar de outro disco para ser o cache. Adicione esse disco ANTES de criar o gateway na console AWS. O tamanho mínimo do cache é 150GB.

<em>Lembrando que esse cache é onde ficarão seus arquivos "hot", enquanto tiver espaço, os arquivos permanecerão no appliance local - acesso mais rápido. Você deve desenhar a solução pensando no seu ambiente, quanto você quer ter de arquivos no seu cache. </em>

Após o deploy do virtual appliance e adicionar o disco, ligue a VM e anote o endereço IP, você vai precisar disso na configuração da console AWS.

Você pode acessar a console do virtual appliance e alterar o endereço IP - o default é DHCP - o DNS, etc. A usuário e senha do virtual appliance do AWS Storage Gateway é <strong>admin:password</strong>.

Agora vamos voltar ao console da AWS para terminar a configuração.
<ul style="list-style-type: square;">
 	<li>Selecione Public no Service End Point. Você pode utilizar uma VCP, mas o processo é um pouco mais complicado.</li>
 	<li>Digite o endereço IP do virtual appliance que você acabou de instalar e clique em Connect to Gateway</li>
 	<li>Na tela Activate Gateway, selecione o seu Time Zone e dê um nome para o gateway. e clique em Activate</li>
 	<li>O próximo passo é a preparação dos discos. O gateway vai formatar e prepar o disco extra (cache) que você adicionou ao appliance e você vai escolher CACHE na opção. Ao finalizar, clique SAVE and CONTINUE.</li>
</ul>
Pronto, o seu AWS Storage Gateway está criado, agora vamos para as configurações.
<ul style="list-style-type: square;">
 	<li>O primeiro passo é criar um Bucket S3 onde os arquivos serão armazenados. Na console AWS, abra o serviço S3 e crie o bucket.</li>
 	<li>Volte para o Storage Gateway que você acabou de criar e clique em CREATE FILE SHARE.</li>
 	<li>Aqui podemos escolher entre um share NFS ou SMB. Agora vamos trabalhar com NFS. Preencha o nome do Bucket S3 que você acabou de criar e clique em NEXT</li>
 	<li>Nessa tela deixe tudo como padrão e clique NEXT</li>
 	<li>Na tela de review, na sessão Allowed Clients, o padrão de acesso é 0.0.0.0/0, ou seja, todas as redes podem acessar esse share, mas não é isso que queremos. Vamos informar aqui a rede ou os endereços de rede - no formato CDIR - que poderão ter acesso a esse share. Após isso, clique em CREATE FILE SHARE.</li>
 	<li>Pronto, o seu share está criado. Você pode repetir esse processo e criar quantos shares desejar.</li>
</ul>
Caso você queira criar um share SMB, você vai precisar colocar o Storage Gateway no seu domínio, as instruções são bem simples de seguir.

Agora é só você apresentar esse novo share para suas máquinas windows ou linux e aproveitar o <strong>STORAGE INFINITO da AWS</strong>.
<h3>Mas e quanto custa?</h3>
Para usar o AWS Storage Gateway como File Gateway ou Gateway de Arquivos, você vai pagar apenas o que consumir de armazenamento S3 e o que transferir PARA FORA da AWS.

<a href="https://aws.amazon.com/pt/storagegateway/pricing/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/pricing/</a>
<h3>Mais informações sobre o AWS Storage Gateway</h3>
<ul style="list-style-type: square;">
 	<li><a href="https://aws.amazon.com/pt/storagegateway/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/</a></li>
 	<li><a href="https://aws.amazon.com/pt/storagegateway/features/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/features/</a></li>
 	<li><a href="https://aws.amazon.com/pt/storagegateway/file/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/file/</a></li>
 	<li><a href="https://aws.amazon.com/pt/storagegateway/vtl/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/vtl/</a></li>
 	<li><a href="https://aws.amazon.com/pt/storagegateway/volume/" target="_blank" rel="noopener noreferrer">https://aws.amazon.com/pt/storagegateway/volume/</a></li>
</ul>
É isso pessoal, deixe nos comentários se você usa o AWS Storage Gateway hoje e como você usa. E se você não usa, esse post te deu alguma idéia de uso no futuro?

Até o próximo post!