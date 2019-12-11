# Blazor WASM Deployment
This is a sample application that uses Blazor WASM app with no host to publish as a static site to Azure Storage.

## How this works
This is deployed via a GitHub Action workflow (see .github/workflows/azure-storage-deploy.yml).  It uses the .NET Core SDK to build and publish the bits of the app and a series of GitHub Actions composed to distribute and deploy to Azure.

## Contact
This was done by [https://twitter.com/timheuer](Tim Heuer) as a sample and to play around with different deployment options.  If you have ideas, reach out!