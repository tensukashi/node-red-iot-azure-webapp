# node-red-iot-azure-webapp

A webapp wrapper for running node-red in an Azure Web App.
To use it just:

1. Deploy to Azure with this button:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmdvanes%2Fnode-red-iot-azure-webapp%2Fmain%2Fwebapp.json" target="_blank"><img src="http://azuredeploy.net/deploybutton.png"/></a>

Contains a predefined flow to set as a destination in [KPN Things](https://portal.kpnthings.com/) and forward data to [Ubidots](https://www.ubidots.com/)

## Known problems

When deployment fails with this error on the `web`/`sourcecontrols` resource:

```
{"code":"DeploymentFailed","message":"At least one resource deployment operation failed. Please list deployment operations for details. Please see https://aka.ms/DeployOperations for usage details.",
"details":[{"code":"Conflict","message":"{\r\n  \"status\": \"Failed\",\r\n  \"error\": {\r\n    \"code\": \"ResourceDeploymentFailure\",\r\n    
\"message\": \"The resource operation completed with terminal provisioning state 'Failed'.\"\r\n  }\r\n}"}]}
```

This deployment will also take too long, approximately 15 minutes.

The service seems to be running afterwards. To still fix the error state, use the "Redeploy" button on the deployment view and select the same settings. Also try a higher SKU, e.g. B1. The deployment should complete without error within 1 minute.
