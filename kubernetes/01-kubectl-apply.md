## Kubernetes Deployment

Take a look at the [application.yaml](application.yaml). 

Here we are deploything the http-echo Docker image to the Kubernetes cluster. You'll find the image name in spec -> spec -> containers. Also in this containers section we map it to port 5678 and pass in some arguments.

In the second portion of this file, we define a service, which allows us to expose the application as a network service. [Read more about services](https://kubernetes.io/docs/concepts/services-networking/service/). 

In the third portion of this file, we define an ingress, which allows enables HTTP/HTTPS routes to our service. [Read more about ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/).

Note: We are deploying this application in the default namespace and not your personal namespace previously created.

[Read more about deployments in general](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/).


### Apply the Deployment

In this folder, run 
```
kubectl apply -f application.yaml
```

Visit [rangerdanger.dev](rangerdanger.dev).

Modify the file to change the message. Re-run the command above to re-deploy the resources defined in the file.

Refresh [rangerdanger.dev](rangerdanger.dev) to see the updated message!