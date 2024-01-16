/[Home](index.md)

# Docker Hub Commands

**Note** The placeholder "username" will be used for docker username and "repository-name" for docker repository.

### Commands in order:

```
docker build -t local-doc .

docker run -p 9090:5000 --name docker-cont local-doc:latest

docker login -u username

docker tag local-doc:latest username/repository-name:latest

docker push username/repository-name:latest
```

## Run commands:

```
docker pull mohammedaadil/sample-flask:latest

docker run -p 9090:5000 --name docker-cont mohammedaadil/sample-flask:latest
```