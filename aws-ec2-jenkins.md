/ [Home](index.md)

# Jenkins setup in AWS EC2 instance 

**Note:** Easy It is!


### Installing Jenkins
```
sudo apt-get update
```

```
sudo apt install openjdk-8-jdk
```


###### First we need to add the repository key to the system
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```

```
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
/etc/apt/sources.list.d/jenkins.list'
```

```
sudo apt-get update
```

```
sudo apt-get install jenkins
```
Open the jenkins website 
```
http://<use the ec2 public ip>:8080/
```

After running this command copy the password and past it in the website and save the password in your notes
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```

#### Prerequisites

```
ssh key
```
###### ssh key setup in the EC2
```
ssh-keygen -t rsa -b 4096 -C "email@gmail.com"

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub
    (copy and past in your github)
```

###### ssh key setup for jenkins 
```
cd ~/.ssh
```
copy and past it the private key 
```
cat id_rsa
```
#### docker 
```
sudo apt install docker.io

sudo groupadd developers

sudo usermod -aG docker jenkins

sudo gpasswd developers

sudo gpasswd docker

newgrp docker
```
Reload the jenkins  
```
sudo service jenkins restart
```

###### Starting Jenkins

To start Jenkins run
```
sudo systemctl start jenkins
```

Check if Jenkins service has started
```
 sudo systemctl status jenkins
```

