\ [Home](index.md)

# Remove sudo

Paste the following commands in your terminal one by one:
```
    sudo groupadd docker
    sudo usermod -aG docker $USER
    newgrp docker
```