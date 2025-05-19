# Microservice Web Application with Node.js, MongoDB, and Docker Compose

## Technical Architecture

### Base Image Selection

| Component       | Version       | Rationale                                                                 |
|-----------------|---------------|---------------------------------------------------------------------------|
| **Node.js**     | 23.11         | Latest stable release offering optimal performance and reliability         |
| **Alpine Linux**| 3.21.3        | Lightweight distribution (5MB base) for efficient container deployments   |

### Dockerfile Directives

```dockerfile
FROM node:23.11-alpine3.21.3  # Base image
WORKDIR /app                  # Container working directory
COPY package*.json ./         # Dependency files
RUN npm install               # Build-time installation
COPY . .                      # Application code
EXPOSE 3000                   # Documentation port
CMD ["npm", "start"]          # Runtime execution

## Network Architecture
networks:
  app-net:
    driver: bridge
    attachable: true


## Deployment Guide

# To Build services run
docker-compose build

# To launch stack
docker-compose up -d

#Base Image Selection
- **Node.js**: Used `node:16-alpine` for minimal size (100MB) and security
- **MongoDB**: Used official `mongo:5.0` image for stability and compatibility

## Dockerfile Directives
- Multi-stage build to minimize final image size
- Proper layer caching with separate COPY for package.json
- EXPOSE for documentation and port mapping

## Docker-compose Networking
- Custom bridge network (`app-network`) for secure inter-container communication
- Port mapping 5000:5000 for web access
- Service discovery using service names (web can access mongo via 'mongo' hostname)

## Volume Usage
- Named volume `mongodb_data` for persistent storage
- Ensures product data persists across container restarts

## Git Workflow
- Feature branch workflow with descriptive commits
- Atomic commits for each component (Dockerfile, compose, etc.)
- Regular pushes to GitHub with clear commit messages

## Debugging Measures
- Used `docker-compose logs` to troubleshoot startup issues
- Verified volume persistence by restarting containers
- Tested network connectivity between containers

## Best Practices
- Semantic versioning for images (1.0.0)
- .dockerignore file to exclude unnecessary files
- Proper documentation in README.md
