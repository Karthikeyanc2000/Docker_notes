# 🐳 Docker Commands – Complete Reference Guide

This document contains commonly used Docker commands with explanations and practical usage notes for future learning and DevOps reference.

--------------------------------------------------

## 📦 Image Management Commands

docker images
→ Lists all Docker images available on the host machine.

docker pull <image-name>
→ Downloads an image from Docker registry (Docker Hub by default).

docker rmi <image-id>
→ Removes a Docker image from the host machine.

--------------------------------------------------

## 🏗 Image Build Command

docker build -t <image-name>:<tag> .
→ Builds a Docker image from a Dockerfile in the current directory.

Example:
docker build -t myapp:latest .

--------------------------------------------------

## 🚀 Container Run Command

docker run <image-name>
→ Runs a container from an image.

Common options:

docker run -d <image>
→ Run container in detached (background) mode.

docker run -p host_port:container_port <image>
→ Maps host port to container port.

docker run -it <image>
→ Interactive terminal mode.

Example:
docker run -d -p 8080:80 nginx

👉 Use this for more options:
docker run --help

--------------------------------------------------

## 📊 Container Management Commands

docker ps
→ Lists only running containers.

docker ps -a
→ Lists all containers (running + stopped).

docker stop <container-id>
→ Stops a running container.

docker start <container-id>
→ Starts a stopped container.

docker rm <container-id>
→ Removes a stopped container.

--------------------------------------------------

## ⚙️ Execute Commands Inside Container

docker exec -it <container-id> <command>
→ Runs a command inside a running container.

Example:
docker exec -it mycontainer bash

--------------------------------------------------

## 🌐 Docker Networking

docker network ls
→ Lists all Docker networks.

docker network create <network-name>
→ Creates a new Docker network.

docker network inspect <network-name>
→ Shows details of a network.

docker network connect <network> <container>
→ Connect container to a network.

docker network disconnect <network> <container>
→ Disconnect container from network.

--------------------------------------------------

## 📤 Registry Commands

docker login
→ Log in to Docker Hub or private registry.

docker push <image-name>
→ Uploads image to registry.

Example:
docker push myusername/myapp:latest

--------------------------------------------------

## 🧠 Advanced & Useful Commands

docker logs <container-id>
→ Shows logs of a running container.

docker inspect <container-id>
→ Displays detailed information about container or image.

docker stats
→ Shows real-time resource usage of containers.

--------------------------------------------------

## 🔥 Important Notes (DevOps Best Practices)

- Always use lowercase for image names.
- Prefer tagging images properly (v1, v2, latest).
- Use detached mode (-d) for production containers.
- Clean unused images using:
  docker image prune
- Clean unused containers:
  docker container prune

--------------------------------------------------

## 🚀 Quick Workflow Example

1. **Build Image:**
docker build -t myapp:1.0 .

2. **Run Container:**
docker run -d -p 8080:80 myapp:1.0

3. **Check Running Containers:**
docker ps

4. **Stop Container:**
docker stop <container-id>

5. **Remove Container:**
docker rm <container-id>

--------------------------------------------------

## 🎯 Final Note

Docker simplifies application packaging, deployment, and scaling.
Mastering these commands is essential for DevOps, Cloud, and Kubernetes environments.

🚀 Keep practicing and build real-world projects!