## Kubernetes Namespaces

Kubernetes has many different resource types, like `Deployment`, `PersistentVolumeClaim`,`Service`, and `Ingress`, to name a few. 

Resources must live within a Namespace. So, a `namespace` is a an isolated collection of resources.  

See the `namespaces` on the cluster with 
```
kubectl get namespaces

# kubectl get ns
```

Pick a name for your new namespace, and create it with 
```
$ kubectl create ns plant
namespace/plant created
```

See the newly created namespace 
```
kubectl get ns

NAME              STATUS   AGE
default           Active   73m
plant             Active   3s
```



