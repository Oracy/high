---
layout: post
title: "Configuring Linux Environment to programming"
date: 2019-08-09 09:29:46
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1565356687/preview_configuring_linux_environment_to_programming_p1oia4.jpg
categories: environment
keywords: programming, linux, vscode, R, RStudio, node, conda, python, jupyter, Fira Code, java
---

Every time that you need to format your computer or get a new one, you have a big head ache, doesn't? Things like did I installed java? Or that extension that do not help in anything but you are in love about that, useless things that you do (not) live without them 😛.

So this is more a _remember_ guide instead of a _how to_, if you remember others things that is cool to use to program or just to live with them, please leave your comment 😃.

I'll try to use easiest way to install everything to be quickly.

1. [Git](#git)
2. [zsh](#zsh)
3. [cURL](#curl)
4. [conda](#conda)
5. [Jupyter](#jupyter)
6. [R](#r)
7. [RStudio](#rstudio)
8. [VSCode](#vscode)
9. [Cinnamon](#cinnamon)
10. [Fira Code](#firacode)
11. [Mysql](#mysql)

First of all we need to get all codes from somewhere, so we need who? Exactly

### [GIT](https://git-scm.com/download/linux)

```bash
sudo apt-get install git -y
git config --global user.name "YOUR NAME"
git config --global user.email your@email.com
```

After install Git, we need to edit all those codes, and put our mind into logic as a big monster trying to get that little indefense lady!! haha

---

#imagem

---

I'll use VSCode (~sublime~, ~atom~)

### [VSCode](https://code.visualstudio.com/)

```bash
   sudo apt-get install snapd snapd-xdg-open
   sudo snap install --classic code
```

There is no much thing to say about that, if Microsoft hits the bull’s eye in something, this something is VSCode... 90% of people that I know works with VSCode, 8% works on Atom and the last 2% is receiving the popup to buy that editor (I won't say which one 😛)
But the best part of VSCode is the extensions, I'll list my extensions here and probably in another video I'll say more about them, follow them below!

```bash
code --install-extension aaron-bond.better-comments
code --install-extension abusaidm.html-snippets
code --install-extension ahmadawais.shades-of-purple
code --install-extension amandeepmittal.expressjs
code --install-extension bbenoist.vagrant
code --install-extension bierner.emojisense
code --install-extension christian-kohler.npm-intellisense
code --install-extension christian-kohler.path-intellisense
code --install-extension CoenraadS.bracket-pair-colorizer
code --install-extension coolbear.systemd-unit-file
code --install-extension DavidAnson.vscode-markdownlint
code --install-extension dbaeumer.vscode-eslint
code --install-extension donjayamanne.githistory
code --install-extension dracula-theme.theme-dracula
code --install-extension eamodio.gitlens
code --install-extension eg2.vscode-npm-script
code --install-extension eprincev-egor.toggle-upper-case
code --install-extension esbenp.prettier-vscode
code --install-extension fatihacet.gitlab-workflow
code --install-extension formulahendry.auto-rename-tag
code --install-extension formulahendry.code-runner
code --install-extension foxundermoon.shell-format
code --install-extension funkyremi.vscode-google-translate
code --install-extension ginfuru.ginfuru-vscode-jekyll-syntax
code --install-extension ginfuru.vscode-jekyll-snippets
code --install-extension GrapeCity.gc-excelviewer
code --install-extension Gruntfuggly.todo-tree
code --install-extension HookyQR.beautify
code --install-extension humao.rest-client
code --install-extension jasonn-porch.gitlab-mr
code --install-extension marcostazi.VS-code-vagrantfile
code --install-extension micnil.vscode-checkpoints
code --install-extension ms-azuretools.vscode-cosmosdb
code --install-extension ms-azuretools.vscode-docker
code --install-extension ms-python.python
code --install-extension ms-vscode.azure-account
code --install-extension ms-vscode.wordcount
code --install-extension mtxr.sqltools
code --install-extension oderwat.indent-rainbow
code --install-extension pflannery.vscode-versionlens
code --install-extension PKief.material-icon-theme
code --install-extension pnp.polacode
code --install-extension qezhu.gitlink
code --install-extension rbbit.typescript-hero
code --install-extension redhat.vscode-xml
code --install-extension RoscoP.ActiveFileInStatusBar
code --install-extension shd101wyy.markdown-preview-enhanced
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension streetsidesoftware.code-spell-checker-portuguese-brazilian
code --install-extension timonwong.shellcheck
code --install-extension vector-of-bool.gitflow
code --install-extension xabikos.JavaScriptSnippets
code --install-extension Zignd.html-css-class-completion
```

User Settings (ctrl + ,)

```json
{
  "editor.tabSize": 2,
  "emmet.includeLanguages": {
    "html": "html",
    "javascript": "javascriptreact"
  },
  "workbench.iconTheme": "material-icon-theme",
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 2000,
  "terminal.external.linuxExec": "iterm",
  "terminal.external.osxExec": "iTerm.app",
  "terminal.integrated.shell.osx": "zsh",
  "terminal.integrated.enableBold": true,
  "terminal.integrated.fontFamily": "MesloLGL Nerd Font",
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.rightClickCopyPaste": true,
  "editor.wordWrap": "on",
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "workbench.editor.highlightModifiedTabs": true,
  "explorer.sortOrder": "type",
  // "editor.minimap.enabled": false,
  "[javascript]": {
    "editor.defaultFormatter": "numso.prettier-standard-vscode"
  },
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "Shades of Purple",
  "prettier.jsxSingleQuote": true,
  "prettier.printWidth": 100,
  "prettier.semi": false,
  "prettier.useTabs": true,
  "prettier.tabWidth": 2,

  "todo-tree.defaultHighlight": {
    "icon": "alert",
    "type": "text",
    "foreground": "red",
    "background": "white",
    "opacity": 50,
    "iconColour": "blue"
  },
  "todo-tree.defaultHighlight": {
    "icon": "alert",
    "type": "text",
    "foreground": "red",
    "background": "white",
    "opacity": 50,
    "iconColour": "blue"
  },
  "todo-tree.customHighlight": {
    "TODO": {
      "icon": "check",
      "type": "line",
      "foreground": "black",
      "iconColour": "red"
    },
    "FIXME": {
      "foreground": "black",
      "iconColour": "yellow",
      "icon": "bug"
    },
    "ASKFORHELP": {
      "icon": "heart",
      "iconColour": "pink"
    }
  },
  "typescript.updateImportsOnFileMove.enabled": "always",
  "cSpell.userWords": ["urlstations"],
  "editor.cursorStyle": "line",
  "editor.cursorBlinking": "expand",
  "files.trimFinalNewlines": true,
  "gitlab.instanceUrl": "http://192.168.101.250/gitlab",
  "window.zoomLevel": 0,
  "shellformat.flag": "-i 4",
  "javascript.updateImportsOnFileMove.enabled": "always",
  "[dockerfile]": {
    "editor.defaultFormatter": "ms-azuretools.vscode-docker"
  },
  "editor.renderWhitespace": "all",
  "extensions.ignoreRecommendations": false
}
```

We are missing the last one configuration on VSCode, and it is the **Fira Code**!!!!

I had a lot of issues to install that on my machine, so the way that works for me is run a sh script and install by this way.

```bash
   #!/usr/bin/env bash

   fonts_dir="${HOME}/.local/share/fonts"
   if [ ! -d "${fonts_dir}" ]; then
      echo "mkdir -p $fonts_dir"
      mkdir -p "${fonts_dir}"
   else
      echo "Found fonts dir $fonts_dir"
   fi

   for type in Bold Light Medium Regular Retina; do
      file_path="${HOME}/.local/share/fonts/FiraCode-${type}.ttf"
      file_url="https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-${type}.ttf?raw=true"
      if [ ! -e "${file_path}" ]; then
         echo "wget -O $file_path $file_url"
         wget -O "${file_path}" "${file_url}"
      else
      echo "Found existing file $file_path"
      fi;
   done

   echo "fc-cache -f"
   fc-cache -f
```
