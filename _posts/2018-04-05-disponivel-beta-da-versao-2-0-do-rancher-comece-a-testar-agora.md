---
ID: 4850
post_title: 'Disponível Beta da Versão 2.0 do Rancher &#8211; Comece a testar agora'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2EnYYG6
published: true
post_date: 2018-04-05 17:37:46
---
Olá Homelabers,

Uma das minhas metas para esse ano é me tornar proficiente em Docker e Kubernetes. E por isso, venho estudando bastante sobre essas tecnologias.

O Rancher é um <strong>painel de controle</strong> e gerenciamento para sua infraestrutura de containers. Eu já falei sobre Rancher <a href="http://bitly.com/rancher-lab" target="_blank" rel="noopener">aqui</a> no blog, em uma série de 3 posts bem bacana.

E hoje vou falar sobre a <a href="https://rancher.com/rancher-2-0-now-feature-complete-enters-final-beta-phase/?utm_campaign=Rancher%202.0%20Beta%20Launch%20-%20April%202018&amp;utm_source=hs_email&amp;utm_medium=email&amp;utm_content=61874117&amp;_hsenc=p2ANqtz-8Sn40l2qeAqm5j7LxB7SbgE2e0MlW5kTrj3JVrDTKgZqXrtoZp6K6u--tPA3JU7ORZPUsKl6JnmPihTqgBiaWxh0D8Kg&amp;_hsmi=61873884" target="_blank" rel="noopener"><strong>versão 2.0 do Rancher que entrou em beta oficial</strong></a>.

<em>Construído com base no Kubernetes, o Rancher 2.0 fornece um único ponto de gerenciamento para qualquer cluster Kubernetes em execução, independentemente de onde ele for executado. Você pode implantar novos clusters com o Rancher em qualquer host, lançar clusters hospedados na nuvem no Google, Azure ou AWS e importar facilmente os seus clusters existentes. Trouxemos a interface intuitiva e a facilidade de uso do Rancher para o Kubernetes.</em>

O Rancher 2.0 é uma plataforma empresarial do Kubernetes que permite gerenciar todas as distribuições do Kubernetes, todos os clusters do Kubernetes, em todas as nuvens.

O Rancher 2.0 tem três componentes principais:
<ul style="list-style-type: square;">
 	<li>Mecanismo de Kubernetes Rancher (Rancher Kubernetes Engine - RKE),</li>
 	<li>Gerenciamento de Cluster Unificado (Unified Cluster Management) e</li>
 	<li>Gerenciamento de Carga de Trabalho (Workload Management).</li>
</ul>
<h2>Mecanismo de Kubernetes Rancher - Rancher Kubernetes Engine - RKE</h2>
<ol>
 	<li><strong>Instalador do Kubernetes Simplificado</strong>. O Rancher 2.0 incorpora o RKE para instalar clusters do Kubernetes em clusters do VMware vSphere, servidores bare-metal e provedores de nuvem que ainda não suportam um serviço gerenciado do Kubernetes.</li>
 	<li><strong>Operações Simplificadas do Kubernetes</strong>. O Rancher suporta operações contínuas de clusters Kubernetes, incluindo, por exemplo, atualização de cluster e backup etcd.</li>
 	<li><strong>Servidor Rancher HA</strong>. O Rancher 2.0 pode ser instalado em um cluster existente do Kubernetes, que pode ser um pequeno cluster RKE criado com o único propósito de executar o servidor Rancher.</li>
</ol>
<h2>Gerenciamento de Cluster Unificado - Unified Cluster Management</h2>
<ol>
 	<li><strong>Clusters e gerenciamento de nós (Clusters and Node Management)</strong>. O Rancher suporta a capacidade de provisionar clusters do Kubernetes hospedados por um provedor de nuvem (GKE, AKS e, em breve, EKS), criados usando RKE ou importados de um cluster existente que você já possui.</li>
 	<li><strong>Autenticação</strong>. O Rancher suporta autenticação local, Github e AD / LDAP para todos os clusters GKE, AKS, EKS, RKE e importados.</li>
 	<li><strong>Gerenciamento de usuários</strong>. O Rancher suporta dois tipos de usuário padrão, admin e usuário, e a capacidade de definir tipos de usuários personalizados.</li>
 	<li><strong>Controle de Acesso Baseado em Função (RBAC)</strong>. - O Rancher permite que você crie suas próprias funções de cluster globais que podem ser facilmente atribuídas a qualquer usuário para gerenciar clusters e projetos do Kubernetes. O Rancher inclui todas as funções do Kubernetes prontas para uso e a capacidade de personalizar suas próprias funções. Cada função personalizada pode ser atribuída em nível global, de cluster ou de projeto.</li>
 	<li><strong>Gerenciamento de Projetos e Namespace</strong>. - Os usuários podem criar namespaces e atribuí-los a projetos. Projetos são um novo conceito do Rancher que permite agrupar um conjunto de namespaces e atribuir um conjunto de permissões de usuário a esses namespaces.</li>
 	<li><strong>Políticas de segurança de Pods</strong>. O Rancher 2.0 permite que os usuários criem suas próprias políticas ou políticas de segurança de pods que podem ser aplicadas a funções.</li>
 	<li><strong>CLI do Rancher</strong>. O CLI suporta todos os principais conjuntos de recursos do Rancher 2.0.</li>
</ol>
<h2>Gerenciamento de carga de trabalho - Workload Management</h2>
<ol>
 	<li><strong>Interface de carga de trabalho (Workload UI)</strong>. O Rancher está introduzindo uma nova UI de carga de trabalho (workloads) que permitirá aos usuários aproveitar a simplicidade da interface do usuário do Rancher para criar e gerenciar suas cargas de trabalho do Kubernetes.</li>
 	<li><strong>Suporte ao Catálogo de Helm</strong>. O catálogo do Rancher 2.0 é construído em Helm charts.</li>
 	<li><strong>Gerenciamento de alertas</strong>. O Rancher 2.0 utiliza o <strong>AlertManage</strong>r do Prometheus para enviar alertas de nível do sistema e do usuário para vários sistemas (incluindo o Slack, Email, PagerDuty e Webhooks.)</li>
 	<li><strong>Logging</strong>. O Rancher 2.0 utiliza o Fluentd para coletar a saída stdout / err ou os logs gravados em diretórios específicos. Uma variedade de destinos de log podem ser utilizados, incluindo ElasticSearch, Splunk, Syslog e Kafka.</li>
 	<li><strong>Pipelines CI / CD</strong>. O Rancher 2.0 inclui um recurso de pipeline integrado simples que permite aos usuários criar pipelines dentro de projetos para integração contínua.</li>
</ol>
<h2>Migração do Rancher 1.6 para 2.0</h2>
De acordo com o anúncio oficial, o Rancher 2.0 foi totalmente reescrito para suportar a plataforma Kubernetes.

O Rancher 2.0 vai suportar apenas os modelos YAML do Kubernetes e ferramentas e melhores práticas para migração da versão 1.6 serão desenvolvidas para ajudar a comunidade que usa Catle a migrar para o Kubernetes. O suporte ao Rancher 1.6 vai durar por pelo menos mais um ano.

O Rancher 2.0 está previsto para ser <strong>lançado oficialmente no final de Abril de 2018.</strong>
<h2>Instalando o Rancher 2.0</h2>
Gostou da notícia e quer testar a versão 2.0 do Rancher?

A instalação da versão Beta do Rancher 2.0 é muito simples e requer apenas 2 passos:

<strong>1: Configuração Host Linux com Docker</strong>
Prepare um host Linux com o Ubuntu 16.04 64 bits, com pelo menos 4 GB de memória.

Instale o Docker no host, as versões suportadas do Docker são 1.12.6, 1.13.1 ou 17.03.2.

<strong>2: Iniciar do servidor do Rancher</strong>
Para instalar e executar o servidor Rancher, execute o seguinte comando do Docker no seu host:
<pre class="">$ sudo docker run -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/server:preview</pre>
Em menos de um minuto o Rancher estará iniciado e a UI pode ser acessada em https:// . Uma vez que o Rancher foi instalado com sucesso, a interface do usuário irá guiá-lo através da adição de seu primeiro cluster.

<img class="aligncenter size-large wp-image-4851" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/18-jGNyiQ9-644x300.png" alt="" width="644" height="300" />
<h2>Meet-Up Online - Managing Workloads on Kubernetes with the Rancher 2.0 Beta</h2>
E para finalizar, no próximo dia 11 de abril às 14:00hs (de Brasília) vai acontecer um Meet-Up Online sobre essa nova versão. Para participar, basta se cadastrar no link <a href="http://info.rancher.com/april-2018-online-meetup" target="_blank" rel="noopener">http://info.rancher.com/april-2018-online-meetup</a>

O Rancher 2.0 já está disponível na versão Beta, e os usuários notarão uma tonelada de novos recursos que realmente melhoram como os usuários implantam e gerenciam seus aplicativos. Neste encontro, vamos percorrer como implantar aplicativos no Rancher 2.0, bem como usar os novos recursos de monitoramento, registro e pipeline.

Durante o Meetup, estaremos demonstrando o novo Beta, incluindo todos os recursos no nível do usuário. Os co-fundadores do Rancher Darren Shepherd (@ibuildthecloud) e Shannon Williams (@smw355) discutirão e demonstrarão:
<ul style="list-style-type: square;">
 	<li>Implantando aplicativos do Kubernetes no Rancher</li>
 	<li>Automatizando o gerenciamento de log</li>
 	<li>Configurando Monitoramento e Alertas</li>
 	<li>Usando o Catálogo do Rancher com Helm</li>
 	<li>Usando o pipeline Rancher.</li>
</ul>
Como sempre, todas as demonstrações serão ao vivo. Nós responderemos a todas e quaisquer perguntas que você possa ter sobre contêineres, Kubernetes e Rancher! Registre-se agora para o seu link pessoal para o encontro.

Detalhes:

Data: quarta-feira, 11 de abril de 2018
Horário: 1:00 PM (horário da costa leste dos EUA)

Mais informações sobre a instalação em: <a href="https://rancher.com/quick-start/" target="_blank" rel="noopener">https://rancher.com/quick-start/</a>

Mais detalhes sobre o Rancher 2.0 podem ser encontrados no Guithub <a href="https://github.com/rancher/rancher/wiki/Rancher-2.0" target="_blank" rel="noopener">https://github.com/rancher/rancher/wiki/Rancher-2.0</a>