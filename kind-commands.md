/ [Home](index.md)

# Kind Commands 

**Note:** All kubernetes commands come here

Install of Kind :
```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/games/kind
```

Create cluster :
```
kind create cluster --name (name-cluster)
```
Running the application:
```
kind load docker-image (docker-image-name):latest --name (name-cluster)

docker build -t (docker-image-name) .

kubectl apply -f k8s

kubectl port-forward svc/(docker-image-name) 9000:80
```

If you make changes in the application :
```
docker build -t (docker-image-name) .

kind load docker-image (docker-image-name):latest --name (name-cluster)

kubectl rollout restart deployment/(app-name)

```

If you change in the  K8s file 
```
docker build -t (docker-image-name) .

kind load docker-image (docker-image-name):latest --name (name-cluster)

kubectl apply -f k8s

kubectl rollout restart deployment/(app-name)

```


kind loading an image:

```
kind load docker-image finance-app --name cluster-name
```

kind creating a cluster:

```
kind create cluster --name mycluster
```


```
kubectl cluster-info --context kind-myclustergcp
```

get all images in kind:

```
docker exec -it my-node-name crictl images
```


rollout:

```
kubectl rollout restart deployment/finance-app 
```


delete kind cluster:

```
kind delete cluster --name mycluster
```



get all running clusters :

```
kind get clusters
```


get all running nodes :

```
kind get nodes
```
----------------
```

```

### Ref :

  * []()
