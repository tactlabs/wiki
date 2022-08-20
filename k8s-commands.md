/ [Home](index.md)

# Kubernetes Commands

**Note:** All kubernetes commands come here




```
https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-macos
```





Kubectl version
```
kubectl version

Client Version: version.Info{Major:"1", Minor:"16", GitVersion:"v1.16.2", GitCommit:"c97fe5036ef3df2967d086711e6c0c405941e14b", GitTreeState:"clean", BuildDate:"2019-10-15T23:43:08Z", GoVersion:"go1.12.10", Compiler:"gc", Platform:"darwin/amd64"}
    Server Version: version.Info{Major:"1", Minor:"15", GitVersion:"v1.15.0", GitCommit:"e8462b5b5dc2584fdcd18e6bcfe9f1e4d970a529", GitTreeState:"clean", BuildDate:"2019-06-19T16:32:14Z", GoVersion:"go1.12.5", Compiler:"gc", Platform:"linux/amd64"}
```





Basic Minikube commands
```
minikube start
kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080
kubectl expose deployment hello-minikube --type=NodePort
kubectl get pod
curl $(minikube service hello-minikube --url)
kubectl delete deployment hello-minimube
minikube stop
```






```
minikube stop && minikube delete
```






```
minikube ip
```






```
minikube dashboard
```






```
minikube dashboard --url=true
```






```
kubectl proxy
```





Get nodes
```
kubectl get nodes
```





Don't show miniukbe notifications
```
minikube config set WantUpdateNotification false
```





Kubeclt service types
```
ClusterIP
NodePort
LoadBalancer
ExternalName
```
https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types





Delete all pods
```
kubectl delete --all pods --namespace=default
```




Delete all deployments
```
kubectl delete --all deployments --namespace=default
```





Delete all services
```
kubectl delete --all services --namespace=default
```

Cleanup
```
kubectl -n default delete services reverser-be reverser-fe

kubectl -n default delete deployment flask-app
kubectl -n default delete deployment reverser-be reverser-fe
```



Install Minikube
```

```
https://kubernetes.io/docs/tasks/tools/install-minikube/


  





Kube config location
```
/Users/xyzabc/.kube
config_oct14  - OLD and Localhost
config - AWS Remote
```




Delete pods
```
kubectl delete pods <pod>
```
https://kubernetes.io/docs/tasks/run-application/force-delete-stateful-set-pod/




Simple App in Kubectl
```
kubectl apply -f deployment.yaml 
deployment.apps/nginx-deployment
kubectl describe deployment nginx-deployment
kubectl get pods
kubectl get pods -l app=nginx
kubectl describe pod nginx-deployment-5754944d6c-5lhbm

kubectl get deployments

kubectl expose deployment nginx-deployment --type=NodePort
curl $(minikube service nginx-deployment --url)
    http://192.168.99.100:31775
```





Simple Flask app
```
Image: https://hub.docker.com/r/tiangolo/uwsgi-nginx-flask/
docker pull tiangolo/uwsgi-nginx-flask


kubectl apply -f flask-deployment.yaml 

# if any updates, change the yaml file and do
kubectl apply -f flask-deployment.yaml 

# verify inside pod
kubectl exec -it flask-sample-deployment-6bf5f67f9-w8rwh bash
curl http://localhost:80

# get from deployments
kubectl get deployments
    flask-sample-deployment   2/2     2            2           6m13s
```


Expose service
```
kubectl expose deployment flask-sample-deployment --type=NodePort
```


verify services
```
kubectl get svc
flask-sample-deployment   NodePort    10.98.110.45     <none>        5002:31561/TCP   19s
```




get url
```
minikube service flask-sample-deployment --url
http://192.168.99.100:31561
```





Check logs
```
kubectl logs flask-sample-deployment-5fb467f9d-4ctf5
```





Delete deployment and services
```
kubectl get all
    PODS:
        pod/flask-sample-deployment-5fb467f9d-kj4gh   1/1     Running            0          2m8s
        pod/flask-sample-deployment-6bf5f67f9-q6g6w   1/1     Running            0          2m9s
    Services:
        service/flask-sample-deployment   NodePort    10.98.110.45     <none>        5002:31561/TCP   7m5s
    Deployments:
        deployment.apps/flask-sample-deployment   1/2     1            1           13m
```


Delete both deployment and service
```
kubectl delete deployment.apps/flask-sample-deployment service/flask-sample-deployment
```


Kube pod details
```
kubectl get po

kubectl logs bapi-be-6db7bf6f95-bshhk

kubectl get services -o wide

    more:
    https://coreos.com/tectonic/docs/latest/tutorials/sandbox/deleting-deployment.html
```






```
kubect exec -it nginx-deployment-5754944d6c-mkpt8 bash
```
more:
https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands

https://kubernetes.io/docs/reference/kubectl/cheatsheet/

https://medium.com/@wisegain/minikube-cheat-sheet-a273385e66c9




### Minikube:

```
brew install minikube

minikube start

minikube start
minikube dashboard

kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node
kubectl get deployments
kubectl get pods
kubectl get events
kubectl config view
```





set minikube context
```
kubectl config use-context minikube

kubectl expose deployment hello-node --type=LoadBalancer --port=8080
kubectl get services
minikube addons list
minikube addons enable heapster
kubectl get pod,svc -n kube-system
```





pods, deployments, services, ingress, nodes
```
kubectl get pods
kubectl get deployment
kubectl get services
kubectl get ingress
kubectl get nodes
```





how to delete
```
kubectl delete service hello-node
kubectl delete deployment hello-node
```





stop, delete
```
minikube stop
minikube delete
```






```
kubectl cluster-info
```





kubectl get namespace
```
NAME          STATUS   AGE
default       Active   8m
kube-public   Active   8m
kube-system   Active   8m
```



```
kubectl create namespace rjdev
NAME          STATUS   AGE
default       Active   10m
kube-public   Active   10m
kube-system   Active   10m
rjdev         Active   47s
```


kube config location
```
~/.kube/config
```





kubectl config get-clusters
```
kubectl config
current-context
delete-cluster
delete-context
get-clusters
rename-context
set
set-cluster
set-context
set-credentials
unset
use-context
view
```





kubectl config view
```
kubectl config get-contexts
    CURRENT   NAME       CLUSTER    AUTHINFO   NAMESPACE
    *         minikube   minikube   minikube
```
    


```
kubectl config current-context
minikube
```



```
kubectl config get-clusters
    NAME
    minikube
```




```
kubectl config --help
```






```
kubectl get namespace

NAME          STATUS   AGE
default       Active   40m
kube-public   Active   40m
kube-system   Active   40m
rjdev         Active   31m
```






```
kubectl -n dev get pods
    get pods in the dev namespace
```





```
kubectl get pods
    get pods in the current (default) namespace
```


```
kubectl config current-context
```


```
kubectl config set-context $(kubectl config current-context)
```



```
kubectl get pods
kubectl get deployments
kubectl get services
kubectl get ingress
kubectl get nodes
```


```
minikube --help
```



```
minikube ip
    192.168.99.101
```


```
minikube ssh-key
    /Users/xyzabc/.minikube/machines/minikube/id_rsa
```


```
minikube ssh
```



```
minikube start --kubernetes-version v1.7.0
```


```
minikube start --kubernetes-version v1.7.0 \
 --extra-config=proxy.IPTables.SyncPeriod.Duration=5000000000 \
 --extra-config=proxy.IPTables.MinSyncPeriod.Duration=3000000000 \
```

 
```
minikube addons list
```

    
#
```
eval $(minikube docker-env)
    enables us to interact and build against docker daemon inside the minikube VM.
``` 
    

```
kubectl get deployments
```


```
kubectl get pods
```



```
kubectl get events
```



```
kubectl config view

```
https://kubernetes.io/docs/tutorials/hello-minikube/



debugging:
```
kubectl get event -n reverser-dev
```

misc commands
```
kubectl get svc --all-namespaces -o wide

kubectl get nodes -o wide

kubectl get nodes --show-labels

aws eks list-nodegroups --cluster-name rj-test-cluster

kubectl -n reverser-dev get nodes

eksctl get nodegroups --cluster rj-test-cluster

eksctl scale nodegroup --cluster=rj-test-cluster --nodes=2 --name=rj-test-ng

eksctl drain nodegroup --cluster=rj-test-cluster  --name=rj-test-ng

kubectl get all

cat ~/.kube/config
```












