# TP1 VCL - Setup of a Nested VMware ESXi Environment

This repository contains the report and configurations for the first practical work (TP1) of the Virtualization and Cloud Computing (VCL) course.

## Project Overview

The main objective of this lab is to explore and implement nested virtualization. We deployed a Type 1 hypervisor (VMware ESXi) inside a Type 2 hypervisor (VMware Workstation). The infrastructure also includes external shared storage and an automated network-based OS deployment system.

## Architecture and Components

- **Type 2 Hypervisor:** VMware Workstation (installed on the host machine).
- **Type 1 Hypervisor:** VMware ESXi 6.x (running as a virtual machine).
- **Management Client:** Windows 10 virtual machine running vSphere Web Client.
- **NAS and PXE Server:** Red Hat / CentOS 7 virtual machine providing:
  - **NFS (Network File System):** Shared external datastore connected to the ESXi hypervisor.
  - **PXE (Preboot eXecution Environment):** Automated OS installation for Type 1 nested virtual machines using `dnsmasq`, `tftp`, and `vsftpd`.

## Key Implementations

1. **Virtual Network Configuration:** Setup of Host-only virtual switches (VMnet10) with manual IP addressing and DHCP disabled.
2. **ESXi Setup:** Installation and initial management network configuration (static IPv4, DNS).
3. **NFS Datastore:** Partitioning secondary virtual disks in Linux and exporting directories via NFS, then mounting them as a Datastore in vSphere.
4. **PXE Boot Server:** Configuration of a local DHCP, TFTP, and FTP server to distribute CentOS installation files over the network without requiring ISO files on the target VMs.
5. **Advanced vSphere Networking:** Migration from the default `vSwitch0` to a new `vSwitch1` without downtime. Implementation of NIC Teaming and Failover using dual virtual network adapters (`vmnic0` and `vmnic1`).
6. **Nested VM Deployment:** Creation of virtual machines directly inside the ESXi hypervisor and automated OS installation via the network PXE boot. Network configuration using the `nmcli` tool.

## Authors

- ATTIA Oussama Abderraouf
- SRAICH Imene

**Supervised by:** Dr. MENNACER Djamel-Eddine  
**Institution:** Ecole Nationale Superieure d'Informatique (ESI)  
**Academic Year:** 2025 - 2026