## Azure Kubectl Setup

We have a Kubernetes (K8s) cluster in [Azure](portal.azure.com).

`kubectl` is the CLI tool you use to communicate with a K8s cluster.

Use [`az aks get-credentials`](https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest#az-aks-get-credentials) to fetch credentials for the cluster.

This will configure `kubectl` config so all future commands target the specified cluster.

```
az aks get-credentials -n {cluster_name} -g {resource_group}
```





