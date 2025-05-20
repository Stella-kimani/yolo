
## Project Overview
This project demonstrates Kubernetes orchestration by deploying a microservices application (frontend, backend, and MongoDB) on Google Kubernetes Engine (GKE).

## Live Application
Access the deployed application at: [http://<GKE_EXTERNAL_IP>:<NODE_PORT>]

## Prerequisites
- Google Cloud SDK
- kubectl configured with GKE cluster access
- Docker Hub account

## Quick Start
1. Set up GKE cluster:
```bash
gcloud container clusters create my-cluster --num-nodes=3 --zone=us-central1-a

    Deploy the application:

bash

kubectl apply -f manifests/all-in-one.yaml

    Get access information:

bash

kubectl get svc

Project Structure

.
├── manifests/           # Kubernetes configuration
│   └── all-in-one.yaml  # Main deployment file
├── backend/             # Node.js backend service
├── client/              # React frontend
├── roles/               # Ansible configuration
├── Explanation.md       # Implementation details
└── README.md            # This file

Key Features

    MongoDB deployed as StatefulSet

    Frontend exposed via NodePort

    Persistent storage for database

    Health monitoring probes
