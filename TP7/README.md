# TP7 VCL - Using the OpenStack Platform

This repository contains the report and guide for the seventh practical work (TP7) of the Virtualization and Cloud Computing (VCL) course. This lab focuses on deploying a private cloud from scratch using the OpenStack platform.

## Project Overview

The objective of this lab is to install and configure a single-node, all-in-one private cloud using **OpenStack** with the **PackStack** deployment tool. After a successful installation, we walk through the entire process of provisioning and launching a virtual machine instance from the perspective of both a cloud administrator and a regular tenant user.

## Architecture and Components
- **Cloud Platform:** OpenStack (Rocky release).
- **Deployment Tool:** PackStack, an automated utility for deploying OpenStack on CentOS/RHEL.
- **Host Environment:** A single CentOS 7 virtual machine running on VMware Workstation, which hosts all OpenStack services (Controller, Compute, Network, etc.).
- **Core OpenStack Services Used:**
  - **Keystone:** Identity service for authentication and project management.
  - **Neutron:** Networking service for managing virtual networks, routers, and security groups.
  - **Glance:** Image service for storing and managing virtual machine images.
  - **Nova:** Compute service for managing the lifecycle of virtual machine instances.
  - **Horizon:** The web-based dashboard for interacting with OpenStack.

## Key Concepts and Tasks
1.  **PackStack Installation:** Preparing a CentOS 7 host and using `packstack` with a pre-configured answer file to deploy a complete, single-node OpenStack cloud.
2.  **Multi-Tenancy:** Creating a new **Project** (tenant) and a new **User** in Keystone, demonstrating the separation of resources and access control.
3.  **Network Provisioning:** As a tenant user, creating two distinct virtual networks:
    - An **internal network** for private communication between instances.
    - An **external network** to provide public connectivity.
4.  **Routing and Connectivity:** Creating a virtual router to connect the internal and external networks, enabling instances to access the outside world.
5.  **Security and Access Management:**
    - Configuring **Security Groups** to define firewall rules (allowing SSH, HTTP, and ICMP traffic).
    - Allocating and associating a **Floating IP** to an instance to make it reachable from outside the cloud.
    - Importing an **SSH key pair** to ensure secure access to instances.
6.  **Instance Launch:** Going through the full "Launch Instance" workflow in the Horizon dashboard, which includes selecting an image, a flavor (resource size), a network, and a key pair.

## Authors

- ATTIA Oussama Abderraouf
- SRAICH Imene

**Supervised by:** Dr. MENNACER Djamel-Eddine  
**Institution:** Ecole Nationale Superieure d'Informatique (ESI)  
**Academic Year:** 2025 - 2026