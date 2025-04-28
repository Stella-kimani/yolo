# YOLO Object Detection Web Application

## Overview
This project implements a containerized full-stack YOLO (You Only Look Once) object detection system using Docker. The application features:

- React frontend for user interaction
- Node.js backend with YOLO model integration
- MongoDB for data persistence
- Docker Compose for microservice orchestration

## System Requirements

- Docker Engine: [Installation Guide](https://docs.docker.com/engine/install/)
- Docker Compose: Included with Docker Desktop
- 4GB RAM (8GB recommended for YOLO processing)
- GPU acceleration recommended (for optimal YOLO performance)

## Quick Start

### Launch with Docker Compose
```bash
# Build and start all services
docker-compose up --build -d

# View running containers
docker-compose ps

#**Create .env file**
MONGODB_URI=mongodb://mongodb:27017/yolo-app
NODE_ENV=production
PORT=5000

## **Project Structure**
yolo-app/
├── client/          # React frontend
├── server/          # Node.js backend with YOLO
├── docker-compose.yml
└── .env.example
