/ [Home](index.md)

# Krew Installation

Step 1: Run this command on terminal along with paranthesis: 

```
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)
```

Step 2: Open zshrc and paste the following

To open zshrc:
```
  code ~/.zshrc
```
Paste the following:

last line of zshrc file
```
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"
```

put the following under alias
```
alias kubectx="kubectl ctx"
```
To apply changes made in zshrc
```
source ~/.zshrc
```
Step 3: Run ```kubectl krew``` to check installation
