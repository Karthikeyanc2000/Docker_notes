# 🐳 Docker Zero to Hero – Learning Repository

🚀 Repo to learn Docker with real-world examples 

## Docker installation
 **reffer these videos**
 - [Video 1](https://www.youtube.com/watch?v=-Wg2r1lWrTc)
 - [Video 2](https://www.youtube.com/watch?v=3YlxYZK1x_o)
 - [Video 3](https://www.youtube.com/watch?v=5Mfe54238xE)

--------------------------------------------------

## 📦 What is a Container?

A container is a standard unit of software that packages code and all its dependencies so the application runs quickly and reliably across different environments.

A Docker container image includes:
- Application code
- Runtime
- System tools
- System libraries
- Configuration

👉 In simple terms:

A container is a lightweight bundle of application + required libraries + minimal system dependencies.

--------------------------------------------------

## 📊 Containers vs Virtual Machines

Feature | Containers | Virtual Machines
--------|------------|------------------
Resource Usage | Lightweight | Heavy
Startup Time | Fast | Slow
OS | Shares host OS kernel | Full OS per VM
Isolation | Moderate | Strong
Management | Easy | Complex

--------------------------------------------------

## ⚡ Why Containers are Lightweight?

Containers are lightweight because:
- They share the host OS kernel
- They include only required dependencies
- No full operating system is bundled

Example:
- Ubuntu container image: ~22 MB
- Ubuntu VM image: ~2.3 GB

👉 Containers are ~100x smaller than VMs

--------------------------------------------------

## 🖼️ Visual Understanding

Container Concept Image:
https://user-images.githubusercontent.com/43399466/217262726-7cabcb5b-074d-45cc-950e-84f7119e7162.png

Docker Architecture Image:
https://user-images.githubusercontent.com/43399466/217507877-212d3a60-143a-4a1d-ab79-4bb615cb4622.png

Docker Lifecycle Image:
https://user-images.githubusercontent.com/43399466/217511949-81f897b2-70ee-41d1-b229-38d0572c54c7.png

--------------------------------------------------

## 📁 Files & Folders in Container Base Images

- /bin   → Essential binaries (ls, cp, etc.)
- /sbin  → System binaries (init, shutdown)
- /etc   → Configuration files
- /lib   → Shared libraries
- /usr   → User applications and utilities
- /var   → Logs and temporary files
- /root  → Root user home directory

--------------------------------------------------

## 🧩 Host OS Resources Used by Containers

- Host file system (via bind mounts)
- Networking stack
- Kernel system calls
- Namespaces (isolation)
- Control groups (resource limits)

--------------------------------------------------

## 🐳 Docker Overview

Docker is a containerization platform used to:
- Build container images
- Run containers
- Push images to registries

Containerization is a concept  
Docker is an implementation

--------------------------------------------------

## 🏗 Docker Architecture

- Docker Daemon (dockerd)
- Docker Client
- Docker Registry

--------------------------------------------------

## 🔄 Docker Lifecycle

1. docker build → Create image
2. docker run → Run container
3. docker push → Push image

--------------------------------------------------

## 📘 Docker Components

Docker Daemon → Manages containers, images, networks  
Docker Client → CLI tool  
Docker Desktop → GUI tool with Kubernetes  
Docker Registry → Stores images  
Dockerfile → Build instructions  
Image → Read-only template  

--------------------------------------------------

## 🛠️ Install Docker

https://docs.docker.com/get-docker/

Ubuntu:
sudo apt update
sudo apt install docker.io -y

--------------------------------------------------

## ▶️ Start Docker & Verify

docker run hello-world

If permission issue occurs:

sudo systemctl status docker
sudo systemctl start docker
sudo usermod -aG docker ubuntu

--------------------------------------------------

## 🚀 Docker Commands

Login
docker login

Build Image
docker build -t username/my-image:latest .

List Images
docker images

Run Container
docker run -it username/my-image

Push Image
docker push username/my-image

--------------------------------------------------

## 🧠 Docker Objects

Dockerfile → Instructions to build image  
Image → Read-only template  
Container → Running instance of image  

--------------------------------------------------

## 🚀 Build First Image

docker build -t abhishekf5/my-first-docker-image:latest .

--------------------------------------------------

## ▶️ Run Container

docker run -it abhishekf5/my-first-docker-image

--------------------------------------------------

## 📤 Push Image

docker push abhishekf5/my-first-docker-image

--------------------------------------------------

## ⚠️ Important Note While Building Docker Image

Docker image names must be lowercase; uppercase letters are not allowed.

❌ Invalid:
docker build -t MyApp/Image:latest .

✅ Valid:
docker build -t myapp/image:latest .

--------------------------------------------------

## 📦 Image Size Comparison (Multi-stage vs Normal Build)

Normal image size: ~800MB  
Multi-stage image size: ~3.5MB  

Benefits:
- Smaller size
- Faster deployment
- Better security
- Production optimized

--------------------------------------------------

## 🧠 Just for Knowledge

GitHub → Source code management  
Docker Hub → Container image registry  

--------------------------------------------------

## ⚠️ Drawbacks of Docker

- Requires root privileges  
- Single point of failure (daemon)  
- Less isolation than VMs  

--------------------------------------------------

## 🎯 Final Note

Containers are lightweight, fast, and scalable.  
Docker simplifies containerization for real-world applications.

🚀 Happy Learning!