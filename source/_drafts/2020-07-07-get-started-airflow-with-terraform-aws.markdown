---
layout: post
title: "Get Started Airflow with Terraform AWS"
author: "Oracy Martos"
date: 2020-07-21 23:32:33
modified_at: 2020-07-07 23:32:33
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1595350195/terraform_pvg0hk.png
categories: how to, get started 
keywords: aws, airflow, terraform, amazon, ec2, infras, infra as a code 
---

Alguns dias atras fiz um desafio de subir um airflow de sandbox usando a infraestrutura da AWS com terraform, e deixar configurado os acessos.

Se voce precisa fazer alguma coisa do genero, acompanhe os codigos abaixo 😄

Bom, primeiro precisamos de alguns pre requisitos, que eh uma conta na [AWS]({{site.url}}/blog/2020/how-to-aws-sign-up/) e o terraform instalado na sua maquina, neste tutorial iremos usar a versao 0.11.14 do [Terraform]({{site.url}}/blog/2020/how-to-install-terraform-0.11.14/)

Iniciar o terraform

<pre class="bash">
  cd ~/Documents
  mkdir airflow_terraform
  cd airflow_terraform
  terraform init
</pre>

Vamos fazer este projeto modularizado, para poder adicionar mais modulos mais pra frente quando houver necessidade.

A estrutura inicial do projeto vai ficar assim:

<imagem_1>

Vamos la para as configuracoes dos arquivos


