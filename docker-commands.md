# Docker Commands

**Note:** All Docker commands are documented here


How to install docker on Ubuntu?
```
sudo apt-get update
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io

sudo systemctl start docker
sudo systemctl enable docker

docker --version
```
[How to install Docker on Ubunt](https://phoenixnap.com/kb/how-to-install-docker-on-ubuntu-18-04)


Dockr Login
```
docker login --username=rajacsp
```

List Docker images
```
docker image ls
docker images
```

List all Docker running containers
```
docker ps -a
```

Find docker container with filter
```
docker ps --filter "name=luigi"
```
will return the container whose name is luigi


List Docker containers
```
docker container ls -all
```

List Docker containers (running, all, all in quiet mode)
```
docker container ls
docker container ls --all
docker container ls -aq
```

List Docker containers (running, all, all in quiet mode)
```
docker container ls
docker container ls --all
docker container ls -aq
```


Stop the container
```
docker stop <container_name>
```



remove docker container
```
docker rm abcd
```


docker run with detached
```
docker run -d abcd
```






restart if exists
```
docker run --restart=always redis
```





docker commit
```
docker commit --change "ENV DEBUG true" c3f279d17e0a  svendowideit/testimage:version3
```





run the static site
```
docker run -d -P seqvence/static-site
```





Start the existing container
```
docker start <container-name>
```





docker run Ubuntu
```
docker run -it --name ubuntu ubuntu:xenial bash
```





start existing ubuntu
```
docker start ubuntu
```





get into bash
```
docker exec -it ubuntu bash
```





docker exec
```
docker exec -it ubuntu bash
```
ref:
    Run a command in a running container
    https://docs.docker.com/engine/reference/commandline/exec/





Clear docker / remove all containers / docker prune
```
docker system prune -a
```





Docker copy
```
docker ps

docker cp foo.txt 72ca2488b353:/foo.txt

docker cp 72ca2488b353:/foo.txt foo.txt
```
Ref:
https://www.shellhacks.com/docker-cp-command-copy-file-to-from-container/




Docker commit and push
```
docker pull ubuntu
docker run --name csp-lamp-server -it ubuntu:latest bash
apt-get update
apt-get install lamp-server^
docker commit -m "Added LAMP Server" -a "NAME" csp-lamp-server USER/test-lamp-server:latest
docker login
docker push rajacsp/csp-lamp-server
```
Ref: https://www.techrepublic.com/article/how-to-create-a-docker-image-and-push-it-to-docker-hub/






Docker logs:
```
Docker logs <container_id>
```





docker image inspect:
```
docker image inspect <imageid>
docker image inspect 5158108894a9
```
Ref: https://docs.docker.com/engine/reference/commandline/image_inspect/





Docker fresh build and deploy:
```
cd /Users/xyz-abc/projects/docker-flask-reverse-string

docker build -t flask-reverse-string:latest .
```





tagging
```
docker tag flask-reverse-string rajacsp/flask-reverse-string
```




How to build image and push to Docker?
```
docker build -t flask-reverse-string:latest .
docker run -d -p 4000:5000 flask-reverse-string:latest
docker commit <containerid> username/flask-reverse-string:latest
docker push username/flask-reverse-string
```