# Virtualization and Cloud Computing (VCL) Lab Reports

This repository contains a comprehensive collection of practical lab reports for the "Virtualization and Cloud Computing" (VCL) course at the Ecole Nationale Superieure d'Informatique (ESI). The series of seven labs provides a hands-on journey, starting from fundamental hypervisor concepts and progressing to advanced container orchestration and private cloud platforms.

## Overview of Practical Labs (TPs)

The repository is structured around seven distinct practical labs, each building upon the concepts of the previous one.

---

### [TP1: Nested Virtualization with VMware](link-to-tp1-folder)

This foundational lab introduces the concept of **nested virtualization**. We deploy a Type-1 hypervisor (VMware ESXi) inside a Type-2 hypervisor (VMware Workstation) and build a complete, isolated environment from the ground up.

- **Key Concepts:** Nested Virtualization, Type-1 vs. Type-2 Hypervisors, Virtual Networking, Shared Storage.
- **Technologies Used:** VMware Workstation, VMware ESXi, NFS, PXE Boot Server (dnsmasq, TFTP, FTP).

---

### [TP2: Linux Virtualization with KVM/QEMU](link-to-tp2-folder)

This lab shifts focus to native Linux virtualization. We explore the KVM/QEMU stack and its management ecosystem, creating and managing virtual machines through both graphical and command-line interfaces.

- **Key Concepts:** Kernel-based Virtual Machine (KVM), `libvirt` API, Network Bridging, Remote VM Management.
- **Technologies Used:** QEMU/KVM, `libvirt`, `virt-manager` (GUI), `virt-install`/`virsh` (CLI), Python scripting.

---

### [TP3: Storage Virtualization with iSCSI](link-to-tp3-folder)

Building on the KVM environment, this lab focuses on storage virtualization. We deploy a dedicated Storage Area Network (SAN) server and connect it to our KVM hypervisor using the iSCSI protocol, offloading VM storage to the network.

- **Key Concepts:** iSCSI Protocol, Target vs. Initiator, Logical Unit Numbers (LUNs), Shared Storage Pools.
- **Technologies Used:** `targetcli`, `iscsi-initiator-utils`, LVM (Logical Volume Manager), `virsh`.

---

### [TP4: Virtual Datacenter with VMware vCenter](link-to-tp4-folder)

We return to the VMware ecosystem to explore centralized management. This lab covers the deployment and configuration of vCenter Server to create a fully-featured virtual datacenter with high-availability features.

- **Key Concepts:** Centralized Management, High Availability (HA), Live Migration (vMotion), Distributed Networking.
- **Technologies Used:** VMware vCenter Server Appliance (VCSA), ESXi Clusters, Distributed Virtual Switch (dvSwitch), DRS.

---

### [TP5: Containerization with LXC & Docker](link-to-tp5-folder)

This lab introduces the world of containerization, contrasting two popular technologies.
- **Part A (LXC):** Focuses on OS-level virtualization by creating full, isolated Linux systems in containers to host separate web servers.
- **Part B (Docker):** Focuses on application-level virtualization by packaging a Python Flask web application into a portable Docker image.

- **Key Concepts:** OS-level vs. Application-level Virtualization, Container Isolation, Reverse Proxying, Dockerfile.
- **Technologies Used:** LXC, Nginx, Docker, Python Flask.

---

### [TP6: Container Orchestration with Kubernetes](link-to-tp6-folder)

As a logical follow-up to Docker, this lab introduces container orchestration. We deploy and manage a containerized application on a local Kubernetes cluster, exploring the core concepts of application lifecycle management at scale.

- **Key Concepts:** Container Orchestration, Pods, Deployments, Services, Scaling, Rolling Updates, Declarative vs. Imperative Management.
- **Technologies Used:** Kubernetes (K8s), Minikube, `kubectl`, Docker, YAML.

---

### [TP7: Using the OpenStack Platform](link-to-tp7-folder)

The final lab culminates in the deployment of a complete, private Infrastructure-as-a-Service (IaaS) cloud. We install OpenStack from scratch and walk through the workflow of provisioning virtual resources as a cloud user.

- **Key Concepts:** IaaS, Private Cloud, Multi-Tenancy (Projects/Users), Cloud Networking, Instance Provisioning.
- **Technologies Used:** OpenStack (PackStack deployment), Keystone, Neutron, Glance, Nova, Horizon Dashboard.


## Authorship

- **Created by:**
  - ATTIA Oussama Abderraouf
  - SRAICH Imene

- **Supervised by:** Dr. MENNACER Djamel-Eddine
- **Institution:** Ecole Nationale Superieure d'Informatique (ESI)
- **Academic Year:** 2025 - 2026