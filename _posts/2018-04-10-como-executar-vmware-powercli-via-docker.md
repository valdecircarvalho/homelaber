---
ID: 4864
post_title: Como executar VMware PowerCLI via Docker
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2v2kGjx
published: true
post_date: 2018-04-10 08:40:11
---
Olá Homelabers!

Nesse post vou mostrar a vocês como é executar o VMware PowerCLI via Docker.

O pessoal do <a href="https://communities.vmware.com/community/vmtn/automationtools/powercli" target="_blank" rel="noopener">PowerCLI</a> criou uma <a href="https://hub.docker.com/r/vmware/powerclicore/" target="_blank" rel="noopener"><strong>imagem Docker</strong></a> com todos os componentes necessários para que você possa rapidamente utilizar o PowerCLI em qualquer computador/sistema operacional sem ter que se preocupar em ficar instalando PowerShell, dependências, etc.

Essa imagem já está atualizada para a <a href="http://homelaber.com.br/vmware-powercli-10-0-0-disponivel-para-download/" target="_blank" rel="noopener">versão 10 do PowerCLI que eu falei sobre o lançamento nesse post</a>.

Se você já tem o Docker instalado em seu sistema operacional, basta executar o comando:
<pre class="">docker run -it vmware/powerclicore</pre>
<img class="aligncenter size-large wp-image-4866" src="http://homelaber.com.br/site/wp-content/uploads/2018/04/vmware-powercli-10-docker-image-644x518.gif" alt="" width="644" height="518" />

Sim, somente isso! A imagem tem 680MB e já vem configurada com a última versão do <a href="https://hub.docker.com/r/microsoft/powershell/" target="_blank" rel="noopener">PowerShell</a>, <a href="https://communities.vmware.com/community/vmtn/automationtools/powercli" target="_blank" rel="noopener">PowerCLI</a>, <a href="https://powernsx.github.io/" target="_blank" rel="noopener">PowerNSX</a>, <a href="https://github.com/jakkulabs/PowervRA" target="_blank" rel="noopener">PowerVRA</a> e <a href="https://github.com/vmware/PowerCLI-Example-Scripts" target="_blank" rel="noopener">PowerCLI Example Scripts</a> (scripts criados pela comunidade).

Eu estou rodando meus scripts PowerCLI sempre do Docker. E você?

Deixe nos comentários se você já tem utilizado Docker para alguma tarefa específica relacionada ao seu dia a dia com vSphere.

&nbsp;

&nbsp;

&nbsp;