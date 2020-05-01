# Blazor WASM Deployment
This is a sample application that uses Blazor WASM app with no host to publish as a static site to Azure Storage.  A complimentary blog post explaining this can be found here [Deploy a Blazor WASM site to Azure Storage using GitHub Actions](https://timheuer.com/blog/deploy-blazor-app-to-azure-using-github-actions).

## How this works
This is deployed via a GitHub Action workflow (see .github/workflows/azure-storage-deploy.yml).  It uses the .NET Core SDK to build and publish the bits of the app and a series of GitHub Actions composed to distribute and deploy to Azure.

## Requirements
The following is required (and/or pre-requisite) to get this working similarly:

- An Azure Account - get one [Free](https://azure.com/free)
- An Azure Service Principal and stored in repo Secrets as ```AZURE_CREDENTIALS```
- An Azure Storage resource [configured to use Static Sites](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website)

## Contact
This was done by [Tim Heuer](https://twitter.com/timheuer) as a sample and to play around with different deployment options.  If you have ideas, reach out!