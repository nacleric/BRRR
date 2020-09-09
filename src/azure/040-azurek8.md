# Clarifications on az aks and kubectl?
az commandline will connect to your azure kubernetes service. To access the clusters and manage them, you use kubectl.

# Azure Kubernetes Quickstart
[Documentation Link](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough#create-aks-cluster)  
In this quickstart, you deploy an Azure Kubernetes Service (AKS) cluster using the Azure CLI. AKS is a managed Kubernetes service that lets you quickly deploy and manage clusters. A multi-container application that includes a web front end and a Redis instance is run in the cluster. You then see how to monitor the health of the cluster and pods that run your application.


# What is a Resource group?
[Documentation Link](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal#what-is-a-resource-group)  
A resource group is a container that holds related resources for an Azure solution. The resource group can include all the resources for the solution, or only those resources that you want to manage as a group. You decide how you want to allocate resources to resource groups based on what makes the most sense for your organization. Generally, add resources that share the same lifecycle to the same resource group so you can easily deploy, update, and delete them as a group.

The resource group stores metadata about the resources. Therefore, when you specify a location for the resource group, you are specifying where that metadata is stored. For compliance reasons, you may need to ensure that your data is stored in a particular region.