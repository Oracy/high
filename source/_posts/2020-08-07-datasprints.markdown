---
layout: post
title: "DataSprint"
author: "Oracy Martos"
date: 2020-08-07 19:45:02
modified_at: 2020-08-07 19:45:02
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1596838413/Logo_branca_k3he9p.png
categories:  
keywords: data, dataengineer, engineer, airflow, terraform 
---

Eh possível acessar o projeto no github, no link:

[DataSprints case](https://github.com/Oracy/data-sprints)

La tem todo o código detalhado e os READMEs para cada etapa.

## Estrutura usada para o projeto

- A estrutura utilizada foi a stack da AWS.
- Para armazenamento dos dados usei S3.
- Para subir o airflow usei terraform.
- A maquina foi uma ec2 t3a.xlarge
- Para visualização dos dados usei QuickSight, nao consigo disponibilizar para publico o dashboard, mas esta pronto na minha conta, e consigo dar permissão para usuarios.

## Terraform

Repositório [Terraform]({{site.url}}/blog/2020/datasprints-terraform)

Para iniciar o projeto terraform, é necessario ter os acessos a AWS com `aws_key_id` e `aws_secret_access_key`.

Rodar os comandos `terraform init && terraform plan && terraform apply`.

`terraform plan` nao é um comando essencial, apenas para ver quais alteracoes irao ocorrer.

## Fluxo Airflow

A configuração do airflow esta dentro da ec2, e o container rodando, um container com airflow e um container com o postgresql.

Para armazenar os dados estou usando o postgres.

O código da dag esta em [DataSprints dag]({{site.url}}/blog/2020/datasprints-dag)

## QuickSight

[Dashboard]({{site.url}}/blog/2020/datasprints-dashboard) (prints).

## Analise

[Analise dos Dados]({{site.url}}/blog/2020/datasprints-analise)