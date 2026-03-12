# TP5 Part B - Application Deployment with Docker

This document covers the second part of the TP5 lab, which focuses on application-level virtualization using Docker. The goal is to package a simple Python web application into a Docker image, run it as a container, and verify its accessibility across the network.

## Architecture and Components
- **Docker Host:** An Ubuntu 20.04 virtual machine where the Docker Engine is installed and runs.
- **Client VM:** A RedHat 7.0 virtual machine used to test remote access to the containerized application.
- **Application:** A minimalist web application built with the Python Flask framework, which serves a simple "Hello World" style message.

## Key Concepts and Tasks
1.  **Docker Engine Installation:** Following the official procedure to install Docker Community Edition (Docker-CE) on Ubuntu, including setting up the official Docker repository.
2.  **Dockerfile Authoring:** Creating a `Dockerfile` that defines the steps to build a custom application image. This includes:
    - Specifying a base image (`python:3.8-alpine`).
    - Setting a working directory.
    - Installing Python dependencies from a `requirements.txt` file using `pip`.
    - Copying the application source code into the image.
    - Exposing the application port and defining the container's startup command.
3.  **Image Building:** Using the `docker build` command to create a portable, self-contained image from the Dockerfile.
4.  **Container Execution:** Running the application using `docker container run`. This step involves mapping a port from the host machine to a port inside the container to make the application accessible externally.
5.  **Testing and Verification:** Confirming that the application is running correctly by accessing it from both the local host and the remote client VM. The `docker ps` and `docker stop` commands are used to manage the container's lifecycle.