## Azure Account Setup

Open a command prompt/termal.

```
$ az login
```
Login with your Microsoft account

```
$ az account list
```
You should see in your list the following entry:
```
  {
    "cloudName": "AzureCloud",
    "id": "{subscription_id}",
    "isDefault": false,
    "name": "Visual Studio Enterprise",
    "state": "Enabled",
    "tenantId": "{tenant_id}",
    "user": {
      "name": "{your_microsoft_account_email}",
      "type": "user"
    }
  }
```
This corresponds to the Azure subscription that we will use for the project. If you go to portal.azure.com you'll see the web interface for the subscription. Here you can use the GUI to add and interact with Azure resources.

Many actions related to working with Azure resources can be done both via Azure CLI and through the portal.  

