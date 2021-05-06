# Zsh Terminal 

Zsh Terminal
```
sudo apt-get update
sudo apt upgrade
```
```
sudo apt install zsh
sudo apt-get install powerline fonts-powerline
```
```
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```
```
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```
```
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

```
gedit .zshrc

source ~/.zshrc
ZSH_THEME="powerlevel9k/powerlevel9k"POWERLEVEL9K_DISABLE_RPROMPT=true
POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="▶"
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX=""
```
```
chsh -s /bin/zsh

sudo gedit ~/.zshrc

ZSH_THEME="agnoster"

source ~/.zshrc

sudo gedit ~/.oh-my-zsh/themes/agnoster.zsh-theme
```

comment #prompt_context

```
Error: conda command not found

Solution:
Copy your conda setup from .bashrc and paste it in .zshrc 
```