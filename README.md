# Action-b

[action-b.yml](.github/workflows/action-b.yml) workflow
for login to Asuze and set kubecofig for ready to install service with Helm 

## Prepare secrets for Azure login
* login to azure via azure-cli.
```
az login
```

* Create a service principal and configure its access to Azure resources.
```
az ad sp create-for-rbac --name "GitHub-Actions" --role contributor \
                          --scopes /subscriptions/50e9362c-c42f-4561-a4d3-ea4f94734cb4 \
                          --sdk-auth
```
output was like this.
```
{
  "clientId": "5372e824-efcb-4d5d-a3f0-766be09deba5",
  "clientSecret": "eCV8Q~1Wwkw3VXdG2QbMjOOBqiqSC.4nhbb2LbkM",
  "subscriptionId": "50e9362c-c42f-4561-a4d3-ea4f94734cb4",
  "tenantId": "8326914f-8931-4277-a058-a66091b77dd3",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```

* add secrets in [settings/secrets/actions](../../settings/secrets/actions) with output of the previous step. 
then save in name "AZURE_CREDENTIALS" 
