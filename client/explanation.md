# Containerization Implementation Explanation

## 1. Base Image Selection
- **Node.js**: Used `node:16-alpine` for minimal size (100MB) and security
- **MongoDB**: Used official `mongo:5.0` image for stability and compatibility

## 2. Dockerfile Directives
- Multi-stage build to minimize final image size
- Proper layer caching with separate COPY for package.json
- EXPOSE for documentation and port mapping

## 3. Docker-compose Networking
- Custom bridge network (`app-network`) for secure inter-container communication
- Port mapping 5000:5000 for web access
- Service discovery using service names (web can access mongo via 'mongo' hostname)

## 4. Volume Usage
- Named volume `mongodb_data` for persistent storage
- Ensures product data persists across container restarts

## 5. Git Workflow
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