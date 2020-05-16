# Docker Compose Commands

**Note:** All Docker Compose commands are documented here


Install docker-compose in Ubuntu:
```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version
```
[Ref](https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04)


Get docker-compose version
```
docker-compose --version
```

verify docker compose
```
docker-compose config 
```





Start
```
docker-compose up
```





Start with fresh build
```
docker-compose up -d --build
```




start with detached more
```
docker-compose up -d
```




stop
```
docker-compose down
```





```
docker-compose ps
```





```
docker-compose --help
```




Scale the specific service
```
docker-compose up -d --scale service_1=4 service_2=3
```

