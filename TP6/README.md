# TP6 VCL - Managing Containerized Applications with Kubernetes

This repository contains the report and workflow for the sixth practical work (TP6) of the Virtualization and Cloud Computing (VCL) course. The lab provides a comprehensive introduction to container orchestration using Kubernetes.

## Project Overview

The primary goal of this lab is to learn the fundamentals of Kubernetes by deploying, managing, and scaling a containerized web application. We use **Minikube**, a lightweight Kubernetes implementation, to run a single-node cluster locally. The lab is structured into a series of hands-on exercises that cover the entire application lifecycle.

## Architecture and Tools
- **Orchestration Platform:** Kubernetes, running locally via Minikube.
- **Container Runtime:** Docker, used as the driver for Minikube to run the cluster node.
- **Host Environment:** An Ubuntu 20.04 virtual machine running on VMware Workstation.
- **CLI Tool:** `kubectl`, the primary command-line interface for interacting with the Kubernetes API server.
- **Application:** A simple Python Flask web application, pre-packaged into a Docker image and hosted on Docker Hub. Two versions of the image are used to demonstrate rolling updates.

## Key Concepts and Tasks
1.  **Environment Setup:** Preparing the local machine by installing Docker, Minikube, and `kubectl`.
2.  **Cluster Creation:** Using `minikube start` to bootstrap a single-node Kubernetes cluster.
3.  **Imperative Deployment:** Deploying the first version of the application using `kubectl create deployment`. This involves creating Kubernetes objects like Deployments and Pods.
4.  **Application Exploration:** Interacting with the running application inside the cluster using `kubectl proxy`, `kubectl logs`, and `kubectl exec` to understand its state and behavior.
5.  **Service Publication:** Exposing the application to the external network by creating a Service of type `NodePort` with `kubectl expose`, making it accessible without a proxy.
6.  **Scaling:** Using `kubectl scale` to increase the number of application replicas (Pods) from one to four, demonstrating how Kubernetes handles load distribution.
7.  **Rolling Updates:** Performing a zero-downtime update of the application to a new version using `kubectl set image`. Kubernetes manages the process of gradually replacing old pods with new ones.
8.  **Declarative Deployment:** Deploying the same application using a YAML manifest file. This demonstrates the "Infrastructure as Code" approach, which is the standard practice for managing Kubernetes resources in production.