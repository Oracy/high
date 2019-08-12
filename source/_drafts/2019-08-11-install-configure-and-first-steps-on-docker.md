---
layout: post
title: "Install, configure and first steps on Docker"
permalink: install-configure-and-first-steps-on-docker
date: 2019-08-11 12:15:48
modified_at: 2019-08-11 12:15:48
comments: true
description: "Install, configure and first steps on Docker"
keywords: ""
categories:

tags:

---

Primeiro, atualize sua lista atual de pacotes:
sudo apt update

Em seguida, instale alguns pacotes de pré-requisitos que permitem que o apt utilize pacotes via HTTPS:
sudo apt install apt-transport-https ca-certificates curl software-properties-common

Então adicione a chave GPG para o repositório oficial do Docker em seu sistema:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Adicione o repositório do Docker às fontes do APT:
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"

sudo apt update
apt-cache policy docker-ce

Você verá uma saída como esta, embora o número da versão do Docker possa estar diferente: 

docker-ce:
  Installed: (none)
  Candidate: 18.03.1~ce~3-0~ubuntu
  Version table:
     18.03.1~ce~3-0~ubuntu 500
        500 https://download.docker.com/linux/ubuntu bionic/stable amd64 Packages

sudo apt install docker-ce
sudo systemctl status docker
