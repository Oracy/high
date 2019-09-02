---
layout: post
title: "Using Rabbitmq with Node"
author: "Oracy Martos"
date: 2019-09-01 19:43:11
modified_at: 2019-09-01 19:43:11
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1567377775/preview_using_rabbitmq_with_node_aypgns.png
categories: tutorial 
keywords: rabbitmq, node, js, parallel processing 
---

How to use RabbitMq with Node.js in the same script, using data that coming from workers?
Let's go to know how to do that!!

First thing you need to install [RabbitMq](https://www.rabbitmq.com/download.html) and [Nodejs](https://oracy.github.io/high/blog/2019/install-node.js-easily-way-to-change-version-without-nvm/)

In this text I'll use to Debian distribution, but I'll do by apt way, you can download and install as you think is better, or follow me to install from Server, until our live Dashboard.

<pre class="bash">
  # Import RabbitMQ apt keys.
  wget -O- https://dl.bintray.com/rabbitmq/Keys/rabbitmq-release-signing-key.asc | sudo apt-key add - 
  wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
  # Add RabbitMQ to Repository.
  echo "deb https://dl.bintray.com/rabbitmq/debian $(lsb_release -sc)"
  # Update packages.
  sudo apt update
  # Finally install rabbitmq server.
  sudo apt -y install rabbitmq-server
</pre>

After install server, you can run command below to check if everything is fine
<pre class="bash">
  sudo systemctl status  rabbitmq-server.service 
  # Active service to start with turn on PC
  sudo systemctl enable rabbitmq-server
</pre>

You should see something like that:

![RabbitMq Status](https://res.cloudinary.com/dvy4tauff/image/upload/v1567385367/rabbitmq_status_mrpwaq.png)

Now we need to enable dashboard:

<pre class="bash">
  sudo rabbitmq-plugins enable rabbitmq_management 
</pre>

Now you can see if Rabbit is installed and running as expected with `http://localhost:15672`

You can login as
User: guest
Pass: guest

Or create your admin account with lines below:
<pre class="bash">
  # admin is your username, replace StrongPassword with your password.
  sudo rabbitmqctl add_user admin StrongPassword
  # Set tag administrator to your user.
  sudo rabbitmqctl set_user_tags admin administrator
</pre>