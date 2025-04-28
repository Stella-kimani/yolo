# YOLO Object Detection Web Application

## Overview
This project implements a containerized full-stack YOLO (You Only Look Once) object detection system using Docker. The application features:

- React frontend for user interaction
- Node.js backend with YOLO model integration
- MongoDB for data persistence
- Docker Compose for microservice orchestration
---

## System Requirements

- **Docker Engine**: [Install Guide](https://docs.docker.com/engine/install/)
- **Docker Compose** (included with Docker Desktop)
- **Hardware**:
  - Minimum: 4GB RAM
  - Recommended: 8GB+ RAM with GPU (for YOLO processing)

## Quick Start

1. **Clone repository**
   git clone https://github.com/your-repo/yolo-app.git
   cd yolo-app

2. **Configure environment**
    cp .env.example .env
 
3. **Launch services**
   docker-compose up --build -d

# Verify containers
  docker-compose ps

   
## Core Project Structure

The following is the folder structure for this project

```plaintext
yolo-app/
├── client/          # React frontend
├── server/          # Node.js backend with YOLO
├── docker-compose.yml
└── .env.example
