---
layout: post
title: "Install Oh My Zsh and themes"
permalink: oh-my-zsh-and-themes
date: 2019-08-11 12:10:21
modified_at: 2019-08-11 12:10:21
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1565537717/preview_install_oh_my_zsh_and_themes_tw03pm.png
description: "Oh My Zsh and themes"
keywords: "zsh, zsh-themes, Debian, Linux, Open Source"
categories:
tags:
  - zsh
  - Debian
---

How to install, configure and personalize zsh terminal?
But why use zsh instead of the default terminal? Some features that I use every time from zsh that makes this terminal my default terminal:

- Autocompletion
- Color Customization
- Automatic change directory
- Spelling correction
- Themes

So, let's start installing _oh my zsh_:

<pre class="bash">
  # Update the packages
  sudo apt update
  
  # Upgrade system
  sudo apt upgrade -y
  
  # Install prerequisite packages (ZSH, powerline & powerline fonts)
  sudo apt install zsh -y
  sudo apt-get install powerline fonts-powerline -y
  
  # Clone the oh-my-zsh repository
  git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
  
  # Create a .zshrc configuration file from template of oh-my-zsh
  cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
  
  # Clone the ZSH Syntax Highlighting
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git "$HOME/.zsh-syntax-highlighting" --depth 1
  
  # Add syntax-highlighting in .zshrc Configuration
  echo "source $HOME/.zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> "$HOME/.zshrc"
  
  # Add zsh autosuggestion
  git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
  
  # Change your Default Shell to the zsh
  chsh -s /bin/zsh
</pre>

sudo apt install cargo

cargo install exa
export CARGO_HOME='~/.cargo'
export PATH=$PATH:$CARGO_HOME/bin