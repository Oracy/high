---
layout: post
title: "Install Node.js easily way to change version without NVM"
date: 2019-08-30 20:39:59
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1567209938/preview_install_node.js_easily_way_to_change_version_without_nvm_lqpnkn.png
categories: tutorial
keywords: nodejs linux
---

Here you can find an easy way to use nodejs directly from binaries.

So let's start, first of all we need to install from trust place: [NodeJs](https://nodejs.org/en/)
You can go to this url and download the version that you want, or just type:

<pre class="bash">
  cd ~/Downloads
  wget https://nodejs.org/dist/v10.16.3/node-v10.16.3-linux-x64.tar.xz
</pre>

After download is necessary to extract file, but pay attention it is not a tgz extension.

<pre class="bash">
  tar -xvf node-v10.16.3-linux-x64.tar.xz
</pre>

Now we are good, and with the binaries on our hand, I'll use the place that I always use when need to install softwares this way to keep them organized.

<pre class="bash">
  sudo mv node-v10.16.3-linux-x64 /usr/local/
</pre>

/usr/local/ will be the place that I always put the binaries that I downloaded e.g.: Pentaho, Node, Robo3t.

But to be easy to change the version as our necessity without use NVM, we need to run those commands below:

<pre class="bash">
  # This line below is creating a Symbolik Link to node folder on /usr/local
  sudo ln -s /usr/local/node-v10.16.3-linux-x64/ /opt/node
</pre>

And this line above is why is so easy to navigate between versions, we just need to remove link in /opt/node, and create other that point to the new version, but it is not finished yet.

We still need to set our node binary into our environment variable.

<pre class="bash">
  # Edit our profile file
  echo "export NODE_HOME='/opt/node'" >> ~/.bashrc
  echo "export PATH=$PATH:$NODE_HOME/bin" >> ~/.bashrc
</pre>

Now we just need to reload our configuration typing `bash` or `source ~/.bashrc`

type `node -v` and there is =)
