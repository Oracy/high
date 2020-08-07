---
layout: post
title: "How to install Terraform 0.11.14"
author: "Oracy Martos"
date: 2020-07-20 20:23:02
modified_at: 2020-07-20 20:23:02
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1595350195/terraform_pvg0hk.png
categories: how to, get started 
keywords: terraform, aws, infrastructure 
---

To use terraform 0.11.14 we need to download the bin and set on the Path.

Download and unzip file with commands below:

<pre class="bash">
  cd ~/Downloads && wget https://releases.hashicorp.com/terraform/0.11.14/terraform_0.11.14_linux_amd64.zip
  unzip terraform_0.11.14_linux_amd64.zip
</pre>

Create a folder under `/user/local/terraform-0.11.14/bin` that you will put your terraform bin file there and can change your terraform version when you want.

Add this folder to your environment PATH, if you are using `bash` you will change `~/.bashrc`, if you are using zsh, you will change `~/.zshrc`

<pre class="bash">
  # Create folder and Move to target folder
  sudo mkdir -p /usr/local/terraform-0.11.14/bin
  sudo mv terraform /usr/local/terraform-0.11.14/bin

  # Create Symbolic link to add to your path
  sudo ln -s /usr/local/terraform-0.11.14 /opt/terraform

  # Add Terraform bin path to environment PATH
  echo '# Terraform' >> ~/.bashrc
  echo 'export TERRAFORM_HOME=/opt/terraform' >> ~/.bashrc
  echo 'export PATH=$PATH:$TERRAFORM_HOME/bin' >> ~/.bashrc

  # Reload your bash|zsh
  source ~/.bashrc
</pre>

After those commands, you can run `terraform -v` and you should receive result below:

<pre class="bash">
  Terraform v0.11.14
<pre>
