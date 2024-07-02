#### Mac OS Setup Commends

###### Install xcode

```zsh
xcode-select --install
```


###### Choose zsh as default


###### Setup config files

1 .zshrc

```zsh
touch ~/.dotfiles/.zshrc
```
```zsh
export ZSH="$HOME/.oh-my-zsh"

#ZSH_THEME="robbyrussell"
ZSH_THEME="lukerandall"

plugins=(git)

source $ZSH/oh-my-zsh.sh

tmux attach-session -t 0

alias ll='ls -alF'
alias la=';a -A'

alias vim=nvim

# custom for development
alias dev="sh ~/.dotfiles/scripts/dev.sh"
alias gs='git status'
alias gitlog='git log --graph --decorate --all --oneline'
alias ga='git add'
source /Users/jakub/.docker/init-zsh.sh || true # Added by Docker Desktop
```

2 .gitconfig

```zsh
touch ~/.dotfiles/.gitconfig
```
```git
[user]
	name = JayCode Developer
	email = JayCode.contakt@gmail.com
```

3 .gitignore

```zsh
touch ~/.dotfiles/.gitignore
```
```git
.DS_Store

.env*.local
```

4 .tmux.conf

```zsh
touch ~/.dotfiles/.tmux.conf
```
```bash
set-option -g detach-on-destroy on

set -g mouse on
```


###### Setup dotfiles directory

```zsh
ln -s ~/.dotfiles/.zshrc ~/.zshrc
```
```zsh
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```
```zsh
ln -s ~/.dotfiles/.gitignore ~/.gitignore
```
```zsh
ln -s ~/.dotfiles/.tmux.conf ~/.tmux.conf
```
```zsh
ln -s ~/.dotfiles/nvim/init.lua ~/.config/nvim/init.lua
```


###### Install HomeBrew

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)
```
```zsh
brew bundle --file ~/.dotfiles/Brewfile
```
```zsh
cd ~/.dotfiles && brew bundle
```


###### MacOS Settings

- https://macos-defaults.com/feedback-assistant/autogather.html

```zsh
defaults write com.apple.dock "autohide-delay" -float "0" && killall Dock
```
```zsh
defaults write com.apple.dock "autohide-time-modifier" -float "0.2" && killall Dock
```
```zsh
defaults write com.apple.dock "mineffect" -string "scale" && killall Dock
```


###### Scripts

```zsh
touch ~/.dotfiles/scripts/dev.sh
```
```zsh
SESSION=dev
tmux send-keys "cd ~" Enter;
tmux send-keys "cd ~" Enter;
tmux send-keys "clear" Enter;
tmux split-window -h;
tmux send-keys "cd Developer" Enter;
tmux send-keys "clear" Enter;
```

###### Install Brew Apps

```zsh
brew install tmux
```
```zsh
brew install neovim
```
```zsh
brew install --cask vlc
```
```zsh
brew install fzf
```
