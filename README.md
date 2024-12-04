# Terraform-CI-CD-azure
This repo is created to show the continuous integration and continuous delivery and updating the azure resources automatically using terraform and azure CLI commands

create service principal in azure CLI:
`az ad sp create-for-rbac --name 'SOME-NAME' --role contributor --scopes /subscriptions/SUBSCRIPTION-ID --sdk-auth`
the result shuld be something like this:
```
{
  "clientId": "...",
  "clientSecret": "...",
  "subscriptionId": "...",
  "tenantId": "...",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}
```

The first 4 lines should be added to GH as environment variables so that GH Actions can use them in order to authenticate to azure and then perform the command `terraform plan` successfully.

The service principal can be accessed using Azure portal -> Microsoft Entra ID -> Manage -> App Registrations
