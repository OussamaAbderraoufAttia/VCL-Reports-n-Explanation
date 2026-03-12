# TP5 Part A - Container Platform with Linux LXC

This document outlines the first part of the TP5 lab, focusing on OS-level virtualization using Linux Containers (LXC). The objective is to build a multi-tenant web hosting platform where two isolated web servers run inside separate containers, accessed through a single entry point via a reverse proxy.

## Architecture and Components
- **Host VM:** A CentOS 7 virtual machine running on VMware Workstation, which hosts the LXC engine.
- **Client VM:** A RedHat 7.2 virtual machine used to test access to the web applications.
- **Containers:** Two CentOS 7 containers (`centos1`, `centos2`) created using LXC templates. Each container runs its own isolated instance of the Apache HTTP Server.
- **Reverse Proxy:** An Nginx server running on the Host VM, responsible for routing incoming HTTP requests to the correct container based on the URL path (`/web1` or `/web2`).

## Key Concepts and Tasks
1.  **LXC Installation:** Setting up the LXC environment by enabling the EPEL repository and installing necessary packages (`lxc`, `lxc-templates`, `libvirt`).
2.  **Container Creation and Management:** Using `lxc-create` to provision new containers from a template and `lxc-start` to run them. The `chroot` command is used for initial configuration, such as setting the root password.
3.  **Network Configuration:** Creating a virtual bridge (`lxcbr0`) on the host using `nmcli` to establish a private network for the containers. Static IP addresses are assigned to each container by modifying their respective configuration files.
4.  **Application Isolation:** Installing and configuring Apache HTTP Server independently within each container, demonstrating the isolation of services.
5.  **Reverse Proxying:** Implementing a reverse proxy with Nginx to expose multiple backend services (the two websites) through a single IP address and port on the host machine.