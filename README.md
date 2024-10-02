# My Dotfiles

This repository contains my personal dotfiles and setup scripts for macOS. Follow the instructions below to automate the installation and configuration of your development environment.

## Installation Steps

### Install Xcode Command Line Tools
```sh
xcode-select --install
```

### Oh My ZSH
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
### PowerLevel10K Theme for Oh My Zsh
```sh
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

ZSH_THEME="powerlevel10k/powerlevel10k"
```
## ZSH Plugins

### Install zsh-autosuggestions:

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
### Install zsh-syntax-highlighting:

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
```sh
#Open the ”~/.zshrc” file in your desired editor and modify the plugins line to what you see below.

plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

```sh
rm -rf ~/.zshrc
```
### Setup dot dotfiles
```sh
git clone --recurse-submodules https://github.com/OliveiraMaicon/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```
### Install Homebrew

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ${HOME}/.profile && eval "$(/opt/homebrew/bin/brew shellenv)"

brew bundle --file ~/.dotfiles/Brewfile
```
## How to extract current installed files?
```sh
cd ~/.dotfiles && brew bundle dump --force && git add . && git commit -m "update" && git push 
```
