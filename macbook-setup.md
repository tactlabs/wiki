/ [Home](index.md)

# Macbook Setup


### 1. Install Brew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


### 2. Install Brave
```
brew install --cask brave-browser
```

### 3. Install iTerm2
```
brew install --cask iterm2
```

### 4. Install vscode
```
brew install --cask visual-studio-code
```
  

### 5. Install iTerm2
```
# Have a backup:
cp ~/.zshrc ~/.zshrc.orig

# Install Zshrc
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Install the necessary fonts
git clone https://github.com/powerline/fonts
cd fonts && ./install.sh


sudo code ~/.zshrc
ZSH_THEME="agnoster"
# You may have to remove the default theme robby

# add these two lines anywhere
# hide the username
DEFAULT_USER prompt_context(){}

source ~/.zshrc

ref:
https://medium.com/featurepreneur/how-to-apply-agnoster-theme-in-mac-zshrc-876f3baf8bf

```

### 5. Install Power10K
```
verify:
echo $ZSH_CUSTOM

git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

code ~/.zshrc

# PowerLevel 10 K Configuration
ZSH_THEME="powerlevel10k/powerlevel10k"
POWERLEVEL10K_DISABLE_RPROMPT=true
POWERLEVEL10K_PROMPT_ON_NEWLINE=true
POWERLEVEL10K_MULTILINE_LAST_PROMPT_PREFIX=""
POWERLEVEL10K_MULTILINE_FIRST_PROMPT_PREFIX=""
DEFAULT_USER=$USER


source ~/.zshrc


source ~/.oh-my-zsh/custom/themes/powerlevel10k/powerlevel10k.zsh-theme >>~/.zshrc

echo 'source ~/.oh-my-zsh/custom/themes/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc


p10k configure


ref:
https://medium.com/featurepreneur/how-to-beautify-your-terminal-with-powerlevel10k-87cffcfdcfb4
```


