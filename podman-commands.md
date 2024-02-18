/ [Home](index.md)

## Podman



### How to install Podman in Ubuntu 20.04
```
sudo sh -c "echo 'deb http://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_20.04/ /' > /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list"

wget -nv https://download.opensuse.org/repositories/devel:kubic:libcontainers:stable/xUbuntu_20.04/Release.key -O- | sudo apt-key add -

sudo apt update

sudo apt -y install podman

podman --version
	podman version 3.4.2

ref:
https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_20.04/
https://phoenixnap.com/kb/install-podman-on-ubuntu
```

![image](images/Chromatius.png)
