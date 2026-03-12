# TP2 VCL - Linux Virtualization with KVM

This repository contains the report and source code for the second practical work (TP2) of the Virtualization and Cloud Computing (VCL) course.

## Project Overview

The objective of this lab is to deploy and manage virtual machines natively on Linux using the Kernel-based Virtual Machine (KVM) module. We explore various administration approaches, ranging from GUI tools and CLI commands to custom API scripting.

## Architecture and Tools

- **Hypervisor:** QEMU/KVM (Type 1, integrated into the Linux kernel).
- **Host OS:** CentOS 7.
- **Management API:** `libvirt` daemon.
- **Administration Tools:**
  - `virt-manager`: Desktop user interface for managing virtual machines.
  - `virt-install`: Command-line tool for provisioning new VMs.
  - `virt-viewer`: UI for interacting with the graphical console of virtual machines.
  - `virsh`: Advanced command-line interface for managing domains.
  - `nmcli`: Network management tool used to create the virtual bridge (`kvmbr0`).

## Key Implementations

1. **Environment Setup:** Preparing a nested virtualization environment in VMware Workstation (enabling Intel VT-x / AMD-V pass-through).
2. **Network Bridging:** Configuring a virtual bridge (`kvmbr0`) to attach virtual machines directly to the network.
3. **KVM Installation:** Setting up the hypervisor and validating kernel modules (`lsmod | grep kvm`).
4. **VM Provisioning:** 
   - Installing Ubuntu via the `virt-manager` GUI.
   - Provisioning a RedHat VM entirely through CLI using `virt-install`.
5. **Python Automation:** Developing a custom interactive Python 2.7 script utilizing the `libvirt` Python bindings to programmatically query host info, list domains, retrieve IP addresses, and control VM states (start, shutdown, suspend, resume).

## Authors

- ATTIA Oussama Abderraouf
- SRAICH Imene

**Supervised by:** Dr. MENNACER Djamel-Eddine  
**Institution:** Ecole Nationale Superieure d'Informatique (ESI)  
**Academic Year:** 2025 - 2026