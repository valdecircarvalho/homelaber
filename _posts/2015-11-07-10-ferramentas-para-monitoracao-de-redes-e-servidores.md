---
ID: 890
post_title: >
  10 ferramentas para monitoração de
  redes e servidores
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/1Nl5N8Y
published: true
post_date: 2015-11-07 15:00:13
---
Olá Homelabers!

Nesse post vou apresentar a vocês 10 ferramentas - Open Source e Comerciais - para monitoração de redes e servidores.

<img class="aligncenter size-full wp-image-891" src="http://homelaber.com.br/site/wp-content/uploads/2015/11/noc.jpg" alt="noc" width="736" height="368" />

Algumas dessas ferramentas eu utilizo no dia-a-dia lá na FIRMA e também as tenho instaladas em meu Homelab. Essas ferramentas são amplamente utilizadas em empresas de todos os tamanhos e você pode aproveitar o que vai conhecer aqui para implantar uma delas em sua empresa, facilitar a sua vida e impressionar o seu chefe :)

<!--more-->

A principio todas as ferramentas de monitoração de compartilham de features (caracteristicas) básicas como:
- Monitoramento de CPU, Disco, Memória, Temperatura, etc
- Monitoramento de Interfaces - Volume de tráfego, utilização, etc.
- Avisos e alarmes baseados em Thresholds
- Notificação por e-mail
- Dashboards para apresentação dos dados
- Histórico de eventos

E por tras dos panos, todos eles utilizam as mesmas técnicas e protocolos para capturar informações sobre os sistemas : SNMP, WMI, SSH, Monitores de Performance do Windows.

A minha experiência do dia-a-dia é com a ferramenta da ManageEngine - OpManager que já roda no meu ambiente há mais de 2 anos. J[a cheguei a trabalhar também com o Nagios e com o Zabbix, mas o OpManager, na minha opinião é imbatível.

Nagios
<a href="https://www.nagios.com/products/nagios-core/" target="_blank">https://www.nagios.com/products/nagios-core/</a>

Zabbix
<a href="http://www.zabbix.com/" target="_blank">http://www.zabbix.com/</a>

Moniti
<a href="https://mmonit.com/monit/" target="_blank">https://mmonit.com/monit/</a>

SolarWinds
<a href="http://www.solarwinds.com/network-performance-monitor.aspx" target="_blank">http://www.solarwinds.com/network-performance-monitor.aspx</a>

OpManager
<a href="https://www.manageengine.com/network-monitoring/" target="_blank">https://www.manageengine.com/network-monitoring/</a>

OpenNMP
<a href="http://www.opennms.org/" target="_blank">http://www.opennms.org/</a>

Pandora FMS
<a href="http://pandorafms.com/" target="_blank">http://pandorafms.com/</a>

Zenoss
<a href="http://www.zenoss.org/" target="_blank">http://www.zenoss.org/</a>

PRTG
<a href="http://www.paessler.com/prtg" target="_blank">http://www.paessler.com/prtg</a>

Icinga
<a href="https://www.icinga.org/download/" target="_blank">https://www.icinga.org/download/</a>

Observium
<a href="http://www.observium.org/" target="_blank">http://www.observium.org/</a>

SpiceWorks
<a href="http://www.spiceworks.com/" target="_blank">http://www.spiceworks.com/</a>

BONUS:
Cacti
<a href="http://www.cacti.net/index.php" target="_blank">http://www.cacti.net/index.php</a>

Ntop
<a href="http://www.ntop.org/" target="_blank">http://www.ntop.org/</a>

Aqui no meu HomeLab eu tenho instalado o Cacti, o NTOP e o OpManager, mas pretendo fazer instalações de outros sistemas para ganhar conhecimento, ter uma opinião e postar aqui para vocês. Aguardem os próximos posts.

Até o próximo post e não se esqueça de deixar o seu comentário no post, seguir o HomeLaber no <a href="https://twitter.com/homelaber">Twitter</a> (@Homelaber) e curtir a nossa página no <a href="https://www.facebook.com/homelaber">Facebook</a> (fb.com/homelaber) para ficar sempre atualizado das novidades do blog.