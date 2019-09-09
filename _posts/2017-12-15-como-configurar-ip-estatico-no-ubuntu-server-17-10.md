---
ID: 4122
post_title: >
  Como configurar IP estático no Ubuntu
  Server 17.10
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2q4OSrM
published: true
post_date: 2017-12-15 08:00:14
---
Olá Homelabers!

Vocês sabiam que o <strong>Ubuntu Server</strong> mudou a<strong> forma de configurar IP estático</strong> na <strong>versão 17.10</strong>?

Pois então, eu não sabia. Esses dias, fui subir uma VM com a nova versão do Ubuntu Server e fiquei quebrando a cabeça para configurar um IP estático, pois estava fazendo da maneira antiga - editar o arquivo /etc/network/interfaces

Depois de muito procurar, encontrei uma documentação, onde diz que agora o Ubuntu Server utiliza <a href="https://pt.wikipedia.org/wiki/YAML" target="_blank" rel="noopener">YAML</a> para configuração de rede via um utilitário chamado <a href="https://wiki.ubuntu.com/Netplan" target="_blank" rel="noopener">NETPLAN</a>. Esta nova ferramenta substitui o arquivo de interfaces estáticas (<strong>/etc/network/interfaces</strong>). Agora você deve usar <strong>/etc/netplan/*.yaml</strong> para configurar as interfaces de rede do Ubuntu Server.
<blockquote>O Ubuntu 17.10 introduz um novo método de configuração padrão para dispositivos de rede, usando o utilitário netplan em vez do utilitário ifupdown. A configuração agora está escrita como arquivos YAML <strong>/etc/netplan</strong> em vez de <strong>/etc/network/interfaces</strong>.</blockquote>
Bom, vou deixar aqui uma receitinha de bolo para configurar um IP estático no Ubuntu Server 17.10.

O novo arquivo de configuração de interfaces agora está no diretório <strong>/etc/netplan</strong>. Um arquivo chamado <strong>01-netcfg.yaml</strong> é usado para configurar a primeira interface. Abaixo está a configuração padrão para uma interface usando DHCP.
<pre class=""># This file describes the network interfaces available on your system
# For more information, see netplan(5).
network:
 version: 2
 renderer: networkd
 ethernets:
   ens160:
     dhcp4: yes
     dhcp6: yes</pre>
Para salvar suas alterações, execute o comando abaixo:

<code>sudo netplan apply</code>
<h2>CONFIGURANDO ENDEREÇOS IP ESTÁTICOS:</h2>
Para configurar um endereço de IP estático usando a nova ferramenta NetPlan, o arquivo deve ser assim: endereço IPv4 (192.168.1.40), Gateway (192.168.1.1), Servidores DNS (192.168.1.2).

Conteúdo original do arquivo <strong>/etc/netplan/01-netcfg.yaml</strong>

<img class="aligncenter size-full wp-image-4124" src="http://homelaber.com.br/site/wp-content/uploads/2017/12/configurar-ip-estatico-ubuntu-server-17_01.jpg" alt="" width="1661" height="533" />

Editar o arquivo <strong>/etc/netplan/01-netcfg.yaml </strong>com o comando <code>sudo nano <strong>/etc/netplan/01-netcfg.yaml</strong> </code>

<img class="aligncenter size-full wp-image-4125" src="http://homelaber.com.br/site/wp-content/uploads/2017/12/configurar-ip-estatico-ubuntu-server-17_02.jpg" alt="" width="1663" height="439" />
<pre class=""># This file describes the network interfaces available on your system
# For more information, see netplan(5).
network:
 version: 2
 renderer: networkd
 ethernets:
   ens160:
     dhcp4: no
     dhcp6: no
     addresses: [192.168.1.40/24]
     gateway4: 192.168.1.1
     nameservers:
       addresses: [192.168.1.2]
</pre>
Salve o arquivo, e execute o comando:

<code>sudo netplan apply</code>

<img class="aligncenter size-full wp-image-4126" src="http://homelaber.com.br/site/wp-content/uploads/2017/12/configurar-ip-estatico-ubuntu-server-17_03.jpg" alt="" width="1662" height="512" />

Veja que agora o comendo ifconfig mostra as novas configurações de IP para a interface ens160. Fácil não?

*** Atenção para o nome da sua placa de rede, no meu exemplo, a placa tem o nome de <strong>ens160</strong>. ***

Mais informações sobre como usar o utilitário NETPLAN <a href="https://wiki.ubuntu.com/Netplan" target="_blank" rel="noopener">aqui</a> e <a href="https://wiki.ubuntu.com/MigratingToNetplan" target="_blank" rel="noopener">aqui</a>

<strong>UPDATE</strong>: Depois que publiquei esse post, encontrei na internet um artigo no site <a href="https://sempreupdate.com.br/linux-basico-defina-um-ip-estatico-no-ubuntu-17-10-com-netplan/" target="_blank" rel="noopener">Sempre Update com mais detalhes para configurar o Ubuntu 17.10 com o Netplan </a>

Bom, pessoal, é isso! Deixe nos comentários, se você já sabia dessa nova forma de configurar o IP estático no Ubuntu Server ou se foi uma novidade para você também!

Um abraço e até a próxima!

Valdecir