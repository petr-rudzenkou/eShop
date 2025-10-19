# Exploring Runtime Architecture

## eShop Reference Application

![eShop Reference Application architecture diagram](../img/eshop_architecture.png)

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
Make sure you've completed all the setup requirements from the [Setup](1-Setup.md) guide before running the project.

## Documentation and Resources
- [Aspire Overview](https://learn.microsoft.com/en-us/dotnet/aspire/get-started/aspire-overview)
- [Architecture Overview](https://learn.microsoft.com/en-us/dotnet/aspire/architecture/overview)
- [Orchestration Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/app-host-overview)
- [Integrations Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/integrations-overview)
- [Networking Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/networking-overview)
- [Dashboard Overview](https://learn.microsoft.com/en-us/dotnet/aspire/fundamentals/dashboard/overview)