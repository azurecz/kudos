# kudos-app
HR Kudos application leveraging Azure PaaS including serverless, API Management, AAD, CosmosDB, PowerBI and others

# Deploy complete solution via portal
Click button and follow wizard.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Fazurecz%2Fkudos%2Fraw%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>


# Deploy complete solution from GitHub
```
az group create -n kudos-app -l westeurope
az group deployment create -g kudos-app \
    --template-uri https://github.com/azurecz/kudos/raw/master/azuredeploy.json
```

# Deploy master template from local (it will link to repos)
```
az group create -n kudos -l westeurope
az group deployment create -g kudos --template-file azuredeploy.json
```

# Deploy individual components
Visit individual repos and deploy repo by repo. Please make sure you follow correct order:
1. Backend, currently only Functions implementation in [kudos-backend-functions](https://github.com/azurecz/kudos-backend-functions)
2. API Management in [kudos-apim](https://github.com/azurecz/kudos-apim)
3. Frontend, currently served via WebApp deployed by [kudos-frontend-webapp](https://github.com/azurecz/kudos-frontend-webapp)