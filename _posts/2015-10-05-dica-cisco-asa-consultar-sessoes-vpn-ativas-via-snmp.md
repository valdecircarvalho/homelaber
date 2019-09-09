---
ID: 669
post_title: 'Dica: Cisco ASA &#8211; Consultar sessões VPN ativas via SNMP'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1ja8oeD
published: true
post_date: 2015-10-05 21:06:54
---
Olá Homelabers,

Vou começar a postar mais coisas sobre o meu dia-a-dia na FIRMA. É uma forma de guardar a informação para consultas futuras e ainda ajudar quem está passando pelo mesmo problema agora ou em um futuro distante.

<blockquote><em>Qual é a OID do Cisco ASA para consultar o número de sessões (usuários) ativos via SNMP?</em></blockquote>

Hoje precisei fazer um monitor no <a href="https://www.manageengine.com/network-monitoring/" target="_blank">OpManager</a> (a ferramenta de monitoração que utilizamos na firma) que mostrasse o número de sessões VPN ativas no Cisco ASA (Firewall). A idéia é monitorar de uma forma fácil e gráfica quantos usuários estão utilizando a VPN, determinar horários de pico para otimizar a banda de internet, etc.

No ASA para apresentar essa informação utilizamos o comando:

<pre class="lang:vim decode:true">sh vpn-sessiondb summary</pre>

<img class="aligncenter size-full wp-image-671" src="http://homelaber.com.br/site/wp-content/uploads/2015/10/cisco-asa-sh-vpn-sessiondb-summary.png" alt="cisco-asa-sh-vpn-sessiondb-summary" width="612" height="221" />

Depois de muito quebrar a cabeça, descobri que a OID SNMP que retorna essa informação é a "<strong>.1.3.6.1.4.1.9.9.392.1.3.1</strong>" ou "crasNumSessions" e que a MIB onde está localizada essa informação é a CISCO-REMOTE-ACCESS-MONITOR-MIB (que pode ser baixada <a href="http://tools.cisco.com/Support/SNMP/do/BrowseMIB.do?local=en&amp;step=2&amp;submitClicked=true&amp;mibName=CISCO-REMOTE-ACCESS-MONITOR-MIB#dependencies" target="_blank">aqui no site da Cisco</a>). Vale lembrar que essa OID funciona tanto no OPManager quanto em outras ferramentas de monitoração como o Cacit, Zabbix, etc.

Por fim, foi só importar as MIBs no OpManager, criar um novo monitor e voilá: Um gráfico bonitinho com o número de usuários VPN ativos.

<img class="aligncenter size-full wp-image-670" src="http://homelaber.com.br/site/wp-content/uploads/2015/10/vpn-sessions-opmanager.png" alt="vpn-sessions-opmanager" width="669" height="401" />

É isso ai pessoal! Se essa informação foi útil para você, deixe um comentário no post!

Edit: Vou deixar o<a href="http://1drv.ms/1j1AVlX" target="_blank"> link do meu One Drive com todas as MIBs do Cisco ASA para Download</a>. Assim, caso eu ou você precisar novamente, não precisaremos ficar "caçando" pela internet.

&nbsp;