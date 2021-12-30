# netlifycmsauth

OAuth function app for authenticating netlify cms against github

this function app is based on the solution of deepbass at <https://github.com/deepbass/serverless-cms-azure/>

## App Settings

Get Azure credentials by running:

``` PowerShell
az ad sp create-for-rbac --name https://netlifycmsauth.github.ismaili.de --role contributor --scopes /subscriptions/a4d8ff1d-be81-4022-a3be-0d74d16db134/resourceGroups/static-web-apps --sdk-auth
```

In GitHub, create a secret with the required app settings:

See also documentation how to add app settings via yaml here:
<https://github.com/marketplace/actions/azure-app-service-settings>

``` JSON
[
  {
    "name": "OAUTH_CLIENT_ID",
    "value": "d4897496498f6885a9b0",
    "slotSetting": false
  },
  {
    "name": "OAUTH_CLIENT_SECRET",
    "value": "...",
    "slotSetting": false
  },
    {
    "name": "ORIGIN",
    "value": "dev.ismaili.de",
    "slotSetting": false
  },
   {
    "name": "REDIRECT_URL",
    "value": "https://netlifycmsauth.azurewebsites.net/callback",
    "slotSetting": false
  }
]
```
