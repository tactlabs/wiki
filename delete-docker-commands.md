/ [Home](index.md)

# Delete Docker Commands

Paste the code line by line in terminal:
```
sudo docker rm $(docker ps -aq) -f

sudo docker rmi $(sudo docker images -aq) -f

sudo docker system prune --volumes -f

docker images -a

sudo snap remove docker

sudo docker rm $(sudo docker ps -aq) -f  
```