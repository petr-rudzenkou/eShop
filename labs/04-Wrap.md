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

# What next?

## 1. Aspire CLI (Preview)
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

## 2. Aspire to Kubernetes (Preview)

To get started with the Aspire Kubernetes hosting integration, install the 📦 Aspire.Hosting.Kubernetes NuGet package in the AppHost project.

    ```
    dotnet add package Aspire.Hosting.Kubernetes --prerelease
    ```

After installing the package, add a Kubernetes environment to your AppHost project using the AddKubernetesEnvironment method:

    ```
    var k8s = builder.AddKubernetesEnvironment("k8s");
    ```

To generate Kubernetes manifests from your Aspire application, use the aspire publish command:
    ```
    aspire publish -o k8s-artifacts
    ```

# Support Resources
- [Aspire publishing and deployment overview](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/overview)
- [.NET Aspire Azure Container Apps Integration](https://learn.microsoft.com/en-us/dotnet/aspire/azure/configure-aca-environments)
- [.NET Aspire Kubernetes Integration](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/kubernetes-integration)
- [.NET Aspire Docker Integration](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/docker-integration)
- [Aspire CLI](https://learn.microsoft.com/en-us/dotnet/aspire/cli/install)