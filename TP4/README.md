# TP4 VCL - Virtual Datacenter Configuration with vCenter

This repository contains the report and setup guide for the fourth practical work (TP4) of the Virtualization and Cloud Computing (VCL) course.

## Project Overview

The main objective of this lab is to deploy and configure a centralized management platform for a virtual datacenter using **VMware vCenter Server**. This setup enables advanced features like high availability, load balancing, and live migration.

## Architecture

- **vCenter Server:** Deployed as a vCenter Server Appliance (VCSA) 6.5, a pre-configured virtual machine running Photon OS.
- **Hypervisors:** Two VMware ESXi 6.5 hosts (ESXi1 and ESXi2) managed by vCenter.
- **Shared Storage:** A RedHat/CentOS 7 NAS server providing a shared NFS datastore for the ESXi hosts.
- **Management Client:** A Windows 10 virtual machine used to access the vSphere Web Client.
- **Network:** All components are connected via a single virtual switch (VMnet10) on a `10.10.0.0/24` network.

## Key Implementations

1. **VCSA Deployment:** Importing and configuring the vCenter Server Appliance OVA, including network settings and Single Sign-On (SSO) domain setup.
2. **Datacenter Creation:** Creating a virtual datacenter object in vCenter to serve as a container for all inventory objects.
3. **Cluster Configuration:** Creating a cluster and adding the two ESXi hosts. **DRS (Distributed Resource Scheduler)** is enabled for automated load balancing.
4. **Shared Datastore:** Configuring a shared NFS datastore, making it accessible to both ESXi hosts within the cluster. This is a prerequisite for live migration.
5. **Distributed Virtual Switch (dvSwitch):** Creating a dvSwitch to centralize network configuration across all hosts in the cluster, and migrating both physical NICs and VMkernel adapters to it.
6. **vMotion Activation:** Enabling the vMotion service on the VMkernel adapters of both ESXi hosts to allow for live migration of virtual machines.
7. **Live Migration Test:** Demonstrating a successful live migration by creating a VM on one host and then simulating a host failure, which triggers an automatic migration of the running VM to the second host without any service interruption.

## Authors

- ATTIA Oussama Abderraouf
- SRAICH Imene

**Supervised by:** Dr. MENNACER Djamel-Eddine  
**Institution:** Ecole Nationale Superieure d'Informatique (ESI)  
**Academic Year:** 2025 - 2026