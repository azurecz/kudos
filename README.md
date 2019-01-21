# kudos-app
HR Kudos application leveraging Azure PaaS including serverless, API Management, AAD, CosmosDB, PowerBI and others

** Work in progress **

# Deploy to Azure via portal
Click button and follow wizard.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Fazurecz%2Fkudos-app%2Fraw%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>


# Deploy to Azure via CLI and templates in GitHub
```
az group create -n kudos-app -l westeurope
az group deployment create -g kudos-app \
    --template-uri https://github.com/azurecz/kudos-app/raw/master/azuredeploy.json
```

# Deploy to Azure from local templates
(use for quick turnaround when developing templates)
```
az group create -n kudos-app -l westeurope

az group deployment create -g kudos-app --template-file azuredeploy.json

az group deployment create -g kudos-app \
    --template-file linked/api-kudos.json \
    --parameters apiName=kudos-apim-tahaxxakmr72q backendFunctionsName=kudos-func-tahaxxakmr72q  # Change to your values

```