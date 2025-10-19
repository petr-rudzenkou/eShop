# Exploring Runtime Architecture

## Running the Project

1. Start the application by running:
   ```
   aspire run
   ```

2. Watch the console output for initialization messages

3. Look for the dashboard URL in the console output (typically something like `https://localhost:19888/login?t=4f08cd9d2bfc2a0ee873fdb8c7bf11e6`)

4. Open the Aspire dashboard in your browser to examine the application structure, logs, traces.

5. In the task manager, navigate to the "Process Tree" view to understand the Developer Control Plane architecture

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



    