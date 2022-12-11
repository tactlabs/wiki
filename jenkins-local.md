/ [Home](index.md)

# Jenkins Set-up:

## Linux setup:

### Java installation
```
sudo apt install default-jdk
sudo apt install default-jre
```

### Jenkins installation
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -


cd /etc/apt
sudo gedit sources.list    

deb https://pkg.jenkins.io/debian-stable binary/ 
    (Insert after line 52)

sudo apt-get update && sudo apt-get install jenkins    

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```

Store password somewhere

### Docker
```
sudo groupadd docker 
sudo usermod -aG docker <username>
newgrp docker
sudo service jenkins restart 
```

To start:
```
sudo systemctl start jenkins
```

To stop:
```
sudo systemctl stop jenkins 
```



## Mac setup:

### Install the latest LTS version:
```
brew install jenkins-lts
```

### Install a specific LTS version: 
```
brew install jenkins-lts@YOUR_VERSION
```

### Start the Jenkins service: 
```
brew services start jenkins-lts
```

### Restart the Jenkins service: 
```
brew services restart jenkins-lts
```

### Update the Jenkins version: 
```
brew upgrade jenkins-lts
```