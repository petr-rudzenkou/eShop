# Getting started
Clone the eShop repository: https://github.com/petr-rudzenkou/eShop

# Prerequisites
1. [.NET 9](https://dotnet.microsoft.com/en-us/download)
2. [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
   - Windows
     ```powershell
     winget install --exact --id Microsoft.AzureCLII
     ```
   - macOS
     ```bash
     brew update && brew install azure-cli
     ```
3. [Azure Developer CLI](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/install-azd)
    - Windows
     ```powershell
     winget install microsoft.azd
     ```
   - macOS
     ```bash
     brew tap azure/azd && brew install azd
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

    