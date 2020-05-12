![.NET Core Build and Deploy (AppSvc Win)](https://github.com/timheuer/blazor-deploy-sample/workflows/.NET%20Core%20Build%20and%20Deploy%20(AppSvc%20Win)/badge.svg) ![.NET Core Build and Deploy (Container)](https://github.com/timheuer/blazor-deploy-sample/workflows/.NET%20Core%20Build%20and%20Deploy%20(Container)/badge.svg) ![.NET Core Build and Deploy (AppSvc Linux)](https://github.com/timheuer/blazor-deploy-sample/workflows/.NET%20Core%20Build%20and%20Deploy%20(AppSvc%20Linux)/badge.svg) ![.NET Core Build and Deploy (Storage)](https://github.com/timheuer/blazor-deploy-sample/workflows/.NET%20Core%20Build%20and%20Deploy%20(Storage)/badge.svg)

# Blazor WASM Deployment
This is a sample application that uses Blazor WASM app with no host to publish as a static site to Azure Storage.  A complimentary blog post explaining this can be found here [Deploy a Blazor Wasm app various ways to Azure using GitHub Actions](https://timheuer.com/blog/deploy-blazor-webassembly-applications-on-azure-using-github-actions-wasm).

## How this works
This sample takes a Blazor Web Assembly project and uses GitHub Actions to deploy it in a few ways:

- [Azure Storage](.github/workflows/azure-storage-deploy.yml)
- [Azure App Service (Linux)](.github/workflows/azure-app-svc-linux-deploy.yml)
- [Azure App Service (Linux) using Containers](.github/workflows/azure-app-svc-linux-container.yml)
- [Azure App Service (Windows)](.github/workflows/azure-app-svc-windows-deploy.yml)

You can see each of the steps in the .github/workflows files linked above.

## Requirements
The following is required (and/or pre-requisite) to get this working similarly:

- An Azure Account - get one [Free](https://azure.com/free)
- An Azure Service Principal and stored in repo Secrets as ```AZURE_CREDENTIALS```
- An Azure Storage resource [configured to use Static Sites](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website)

## Contact
This was done by [Tim Heuer](https://twitter.com/timheuer) as a sample and to play around with different deployment options.  If you have ideas, reach out!