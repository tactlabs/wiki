/ [Home](index.md)

# Pbcopy on Ubuntu


* To install On Debian, Ubuntu, Linux Mint:
```
sudo apt install xclip xsel
```
* Once installed, you need create aliases for pbcopy and pbpaste commands. To do so, edit your ~/.zshrc file:

```
vi ~/.zshrc
```
* If you want to use xsel, paste the following lines in your ~/.zshrc file.
```
alias pbcopy='xclip -selection clipboard'
alias sshcopy='pbcopy < ~/.ssh/id_rsa.pub'
```
Save and close the file.

* The ZSH users paste the above lines in ~/.zshrc file and update the changes using command:

```
source ~/.zshrc
```