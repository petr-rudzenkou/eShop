# Getting started

# 1. Local Dev Environment

Clone the eShop repository: https://github.com/petr-rudzenkou/eShop

## Prerequisites
1. [.NET 9](https://dotnet.microsoft.com/en-us/download)
2. [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
   - Windows
     ```powershell
     winget install --id Microsoft.AzureCLII
     ```
   - macOS
     ```bash
     brew update && brew install azure-cli
     ```
3. [Aspire CLI](https://learn.microsoft.com/en-us/dotnet/aspire/cli/install)
     ```powershell
     dotnet tool install -g Aspire.Cli --prerelease
     ```
4. OCI compliant container runtime:
   - Docker
      - [Install Docker Desktop on Windows](https://docs.docker.com/desktop/setup/install/windows-install/)
      - [Install Docker Desktop on Mac](https://docs.docker.com/desktop/setup/install/mac-install/)
   - Podman
      - [Podman Installation Instructions](https://podman.io/docs/installation)
      - [Podman for Windows guide](https://github.com/containers/podman/blob/main/docs/tutorials/podman-for-windows.md)
5. Integrated Developer Environment (IDE) or code editor:
   - [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) version 17.9 or higher
   - [Visual Studio Code](https://code.visualstudio.com/)
     - Extension: [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit)

# 2. Exploring Runtime Architecture

## eShop Reference Application

![eShop Reference Application architecture diagram](img/eshop_architecture.png)

The application consists of:
 - 2 Frontends
 - 5 APIs
 - 2 Processors
 - 4 Databases
 - Cache
 - Event Bus
 - Monitoring system

## Running the Project

1. Start the application by running:
   ```
   dotnet run --project src/eShop.AppHost
   ```

2. Watch the console output for initialization messages

3. Look for the dashboard URL in the console output (typically something like `https://localhost:19888/login?t=4f08cd9d2bfc2a0ee873fdb8c7bf11e6`)

4. Open the Aspire dashboard in your browser to examine the application structure, logs, traces.

5. Check the running containers:
- Docker:
    ```
    docker ps
    ```
- Podman:
    ```
    podman ps
    ```

![Container list](img/container_list.png)

## Troubleshooting Common Issues

### Unhealthy resources
Give some time for the services to warm-up

### SSL Certificate Issues
If you encounter SSL/TLS connection errors, run:
    ```
    dotnet dev-certs https --trust
    ```

### Port Conflicts
If you experience port conflicts:
1. Stop all running Docker containers:
   ```
   docker stop $(docker ps -q)
   ```
2. Re-run the AppHost project

### Note
Make sure you've completed all the setup requirements from the Local Dev Environment guide before running the project.

# 3. Publishing and Deployement

## 1. Aspire CLI
The Aspire Command Line Interface will provide enhanced capabilities for:

### Features
- Project scaffolding and templates
- Local development orchestration
- Enhanced Publish/Deploy Semantics
- Support for generation of IaC artifacts for multiple providers (Bicep, Docker Compose, K8S, Terraform)
- Broader deployment targets, including non-Azure environments.

### How to install?

    ```
    dotnet tool install -g Aspire.Cli --prerelease
    ```

## 1. Aspire to Azure (Preview)

Add Azure Container App environment to your AppHost project using the AddAzureContainerAppEnvironment method:

    ```
    var aca = builder.AddAzureContainerAppEnvironment("aca-env");
    ```

Generate Bicep manifests from your Aspire application:
    ```
    aspire publish -o aca-artifacts
    ```

Deploy Bicep manifests from your Aspire application:
    ```
    aspire deploy
    ```

## 1. Aspire to Kubernetes (Preview)

Add a Kubernetes environment to your AppHost project using the AddKubernetesEnvironment method:

    ```
    var k8s = builder.AddKubernetesEnvironment("k8s");
    ```

Generate Kubernetes manifests from your Aspire application:
    ```
    aspire publish -o k8s-artifacts
    ```

# Summary

## Advantages
 - Simplified orchestration
 - Set of abstractions
 - Unified configuration point
 - Rich Integrations
 - Dashboard
 - Excellent documentation and examples

## Disadvantages
 - Not yet in demand in the market
 - Deployment capabilities are limited and many features are still in preview


# Support Resources
- [Aspire Overview](https://learn.microsoft.com/en-us/dotnet/aspire/get-started/aspire-overview)
- [Architecture Overview](https://learn.microsoft.com/en-us/dotnet/aspire/architecture/overview)
- [Orchestration Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/app-host-overview)
- [Integrations Guide](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/integrations-overview)
- [Dashboard Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/dashboard/overview)
- [Deployment Guide](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/overview)
- [Aspire publishing and deployment overview](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/overview)
- [.NET Aspire Azure Container Apps Integration](https://learn.microsoft.com/en-us/dotnet/aspire/azure/configure-aca-environments)
- [.NET Aspire Kubernetes Integration](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/kubernetes-integration)
- [.NET Aspire Docker Integration](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/docker-integration)
- [Aspire CLI](https://learn.microsoft.com/en-us/dotnet/aspire/cli/install)