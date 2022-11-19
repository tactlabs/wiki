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