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

---

## zsh Themes

#### I'll install 'powerlevel9k' theme

Change `~/zshrc` file on line ZSH_THEME, with your theme that you want to use:

<pre class="bash">
  sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="powerlevel9k\/powerlevel9k"/g' ~/.zshrc
</pre>

###### just replace powerlevel9k to other theme that you want

#### Add ZSH-AutoSuggestion Plugin (best plugin for me)

This plugin get your last command and auto suggest and autocomplete, just pressing → arrow.

<pre class="bash">
  # Install plugin:
  git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

  # Add plugin into zshrc file
  sed -i 's/plugins=(git)/plugins=(\n\tgit\n\tzsh-autosuggestions\n)/g' ~/.zshrc
</pre>

<pre class="bash">
  # Customise the Powerlevel9k prompts
  POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(
    dir
    custom_javascript 
    vcs
    newline
    status
  )
  POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=()
  POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
</pre>

Now we need a good font to see nice icons, I'll use nerd font, you can download on: [nerd-font](https://github.com/ryanoasis/nerd-fonts)

`git clone git@github.com:ryanoasis/nerd-fonts.git`

After download the font, you should move them to `mv nerd-fonts/ ~/.local/share/fonts/`

Next step is add this font as default font to our _zsh terminal_ `echo "POWERLEVEL9K_MODE=\"nerdfont-complete\" >> ~/.zshrc"`

Now we can start our personalization, follow steps below and everything will be fine!! 😄

We have two sectors to configure "left" and "right"
Left sector just to be pretty Tux icon
`echo "POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(custom_linux_icon context dir vcs)" >> ~/.zshrc`

<pre class="bash">
  echo "POWERLEVEL9K_CUSTOM_LINUX_ICON=\"echo ICON \"
  POWERLEVEL9K_CUSTOM_LINUX_ICON_BACKGROUND=069
  POWERLEVEL9K_CUSTOM_LINUX_ICON_FOREGROUND=015" >> ~/.zshrc
</pre>

sudo apt install cargo

cargo install exa
export CARGO_HOME='~/.cargo'
export PATH=$PATH:$CARGO_HOME/bin
