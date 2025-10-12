# Docker-roboshop

# As we are not filling any data into the Redis we can directly run the redis container on our Docker host

# Command >>>> docker run -d --name redis --network roboshop redis:7
    indicates that redis is running on roboshop network with the name redis

# As we are creating the Rabbitmq directly via docker compose and we are mentioning the env variables as well in the docker compose file

 # My Docker Credentials
 username - nagashankar1992332

 login to the docker and run docker compose command

 ==========================================


# DOCKER BEST PRACTISES

 # Dockerfile and Image Optimization:
    Use Multi-stage Builds: Separate build-time dependencies from runtime dependencies to create smaller, more secure final images.
    Choose Small Base Images: Start with lightweight base images (e.g., Alpine) to reduce image size and attack surface.
    Minimize Layers: Combine related commands in a single RUN instruction using && to reduce the number of image layers and improve build cache utilization.
    Leverage Build Cache: Order Dockerfile instructions to maximize caching, placing frequently changing instructions later in the file.
    Use .dockerignore: Exclude unnecessary files from the build context to speed up builds and reduce image size.
    Prefer COPY over ADD: COPY is generally safer and more predictable as it only copies local files, while ADD can also fetch remote URLs and extract archives.
    Pin Base Image Versions: Specify exact image tags (e.g., node:18-alpine) to ensure reproducible builds and prevent unexpected changes.
    Don't Install Unnecessary Packages: Only include what's essential for your application to run.
# Container Security:
    Run as Non-Root User: Create a dedicated user inside the container and run the application as that user, reducing potential privilege escalation.
    Limit Capabilities: Restrict container capabilities to only those strictly necessary for the application.
    Enable Rootless Mode: Where possible, run Docker daemon and containers in rootless mode for enhanced security.
    Use Trusted Images: Source images from official repositories or trusted vendors and scan them for vulnerabilities.
    Avoid Exposing Sensitive Information: Do not store secrets or credentials directly in Dockerfiles or images. Utilize Docker Secrets or environment variables with caution.
    Secure the Docker Daemon Socket: Avoid exposing /var/run/docker.sock to containers or the network.
# Deployment and Management:
    Create Ephemeral Containers: Design containers to be stateless and easily replaceable.
    Decouple Applications: Run only one primary process per container to maintain clear separation of concerns.
    Implement Health Checks: Include HEALTHCHECK instructions in your Dockerfile to allow Docker to determine if a container is running correctly.
    Use Custom Networks: Create custom Docker networks for better isolation and control over inter-container communication.
    Integrate with CI/CD: Automate image building, testing, and deployment within your CI/CD pipeline.
    Monitor and Log: Implement robust logging and monitoring solutions to track container performance and identify issues.