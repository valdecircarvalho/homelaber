---
ID: 5586
post_title: 'Min.io &#8211; Um servidor S3 para rodar na sua infraestrutura'
author: Valdecir Carvalho
post_excerpt: ""
layout: post
permalink: http://bit.ly/2kdiFfO
published: true
post_date: 2019-07-16 15:11:50
---
Olá Homelabers,

Hoje vou falar sobre o <strong>MinIO</strong>, uma ferramenta que me chamou a atenção há alguns meses e que agora estou estudando mais a fundo para talvez implementar em um projeto na FIRMA.

O MinIO é um <strong>servidor de Object Storage 100% compatível com o "protocolo" S3</strong> - da AWS - open source, multi-cloud (que você pode rodar on-prem - dentro da sua infraestrutura), facilmente escalável, de alta performance e distribuído.

<img class="aligncenter size-large wp-image-5592" src="http://homelaber.com.br/site/wp-content/uploads/2019/07/MINIO_wordmark-644x97.png" alt="" width="644" height="97" />

&nbsp;
<blockquote>MinIO é uma solução de armazenamento de objetos de código aberto escrita principalmente em Go. Ele oferece uma API para integração com servidores de armazenamento de objetos S3, bem como uma interface de linha de comando que pode se comunicar com o S3. A interface de linha de comando também permite trabalhar com dados de armazenamento de objetos usando comandos familiares do Unix, como ls e diff. O Minio pode ser instalado em qualquer tipo de sistema operacional moderno - Linux, Windows e MacOS - e também pode ser executado como um contêiner do Docker.</blockquote>
Uma das grandes vantagens do MinIO na minha opinião, é que ele é totalmente compatível com a API S3 da AWS, ou seja, se hoje você tem uma aplicação que "fala" S3 e precisa ter um storage dentro de casa, você pode utilizar o MinIO sem alterações no seu código. Existem muitas outras vantagens, mas essa, é a que mais me chamou a atenção , principalmente para o cenário que estou trabalhando no momento.

O MinIO é open source (APache 2.0) e está disponível para todas as plataformas: Linux, Windows, MacOS e Docker. Empresas podem comprar uma subscription para ter direito ao suporte.

A instalação e configuração do MinIO é bastante simples e nos próximos posts vou mostrar alguns cenários de instalação.

A <a href="https://docs.min.io/" target="_blank" rel="noopener noreferrer">documentação</a> é simples, mas bem completa. Estão disponíveis SDKs para as linguagens Javascript, Java, GO, Python e .Net

Outras features bem legais do MinIO são a Replicação Continuada (Continuous Replication) e o Gateway Multi-Cloud (Multi-Cloud Gateway).

A feature de<strong> Multi-Cloud Gateway</strong> permite que você tenha seus dados disponíveis em qualquer lugar, seja seu ambiente on-prem, seja em um storage tradicional e nas principais clouds publicas - Google, Azure, etc - utilizando a API S3 para manipulação de dados.

<img class="aligncenter size-large wp-image-5604" src="http://homelaber.com.br/site/wp-content/uploads/2019/07/min.io-multi-cloud-gateway-644x327.jpg" alt="" width="644" height="327" />

A feature de Replicação Continuada (<strong>Continuous Replication</strong>) permite que seu dados estejam sempre replicados em diferentes datacenters e clouds, suportando sua estratégia de DR e de uma maneira facilmente escalável.

<img class="aligncenter size-large wp-image-5605" src="http://homelaber.com.br/site/wp-content/uploads/2019/07/min.io-continuous-replication-644x270.jpg" alt="" width="644" height="270" />

O MinIO conta também com uma ferramenta de linha de comando para gerenciamento e manutenção do ambiente chamada MinIO Client e está disponível para Linux, MacOS e Windows. https://docs.MinIO/docs/minio-client-quickstart-guide.html

<strong>Links úteis:</strong>

<a href="https://min.io/product/" target="_blank" rel="noopener noreferrer">https://min.io/product/</a> - Informações sobre o produto

<a href="https://docs.min.io/" target="_blank" rel="noopener noreferrer">https://docs.min.io/</a> - Documentação do produto

<a href="https://github.com/minio/minio/issues" target="_blank" rel="noopener noreferrer">https://github.com/minio/minio/issues</a> - Lista de Issues (Aqui que você pode pedir ajuda)

<a href="https://github.com/minio/awesome-minio" target="_blank" rel="noopener noreferrer">https://github.com/minio/awesome-minio</a> - Uma lista de projetos da comunidade utilizando MinIO.

É isso ai pessoal, aguardem mais posts aqui sobre o MinIO. Tenho gasto algumas boas horas no lab, estudando e montando cenários de uso e vou trazer para vocês!

Deixe nos comentários se você já conhecia o MinIO, se já usa hoje no seu ambiente - estou curioso para saber - ou ainda como você pensa que o MinIO pode ser útil para você.