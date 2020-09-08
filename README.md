# azure-arm-template

[![Quality](https://img.shields.io/badge/quality-demo-red)](https://curity.io/resources/code-examples/status/)
[![Availability](https://img.shields.io/badge/availability-source-blue)](https://curity.io/resources/code-examples/status/)

The repository contains Azure Resource Manager (ARM) templates to deploy Curity in Azure. 

# Deploy using Azure CLI
To deploy a template using Azure CLI you have to be authenticated and have a resource group available.

```az login```

If you need a new resource group
```
az group create \
  --name myResourceGroup \
  --location "Central US"
```
If you have cloned this repository you can then deploy templates from the template directory
```
az deployment group create \
  --name curityDeployment \
  --resource-group myResourceGroup \
  --template-file template/curity-arm-aci.json  
```
  
The template contains parameters. If you havn't set the mandatory ones you will be asked to fill these in before you can deploy the template.
If you want to set e.g. the `password` parameter you would to it like this:
```
az deployment group create \
  --name curityDeployment \
  --resource-group myResourceGroup \
  --template-file template/curity-arm-aci.json was \
  --parameters password=mySecretPassw0rd  
```
   
# Quickstart using Azure Container Instance (ACI)
Sets up a single ACI with one node acting as both admin and runtime. Username for administrator account is **admin**. 

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcurityio%2Fazure-arm-template%2Fmaster%2Ftemplate%2Fcurity-arm-aci.json)

After the deployment is finshed you can see the deployment Outputs for URLs to the Admin UI and to the runtime node.

For instructions how to set up the system, have a look at the [First configuration](https://curity.io/resources/tutorials/getting-started/setup/first-config/) guide.

## License

These templates are licensed under the [Apache v. 2 license](LICENSE).

## Questions

For questions, contact Curity AB:

> info@curity.io
>
> https://curity.io

Copyright (C) 2020 Curity AB.
