# TP3 VCL - Storage Virtualization with iSCSI

This repository contains the report and setup guide for the third practical work (TP3) of the Virtualization and Cloud Computing (VCL) course.

## Project Overview

The objective of this lab is to implement network-based storage virtualization using the iSCSI protocol. We demonstrate how to separate physical storage resources from the virtualization server by using a dedicated Storage Area Network (SAN) server and an iSCSI initiator.

## Architecture

- **SAN Server (Target):** RedHat 7 machine acting as a storage bay, using `targetcli` to manage block and fileio backstores.
- **KVM Server (Initiator):** RedHat 7 machine acting as the virtualization host, connected to the SAN via a dedicated iSCSI network (VMnet11).
- **Management Client:** RedHat 7 machine for remote administration.

## Key Implementations

1. **Storage Target Configuration:** Setting up `targetcli` on the SAN server, including creation of LUNs (Logical Unit Numbers), IQNs (iSCSI Qualified Names), and CHAP authentication.
2. **iSCSI Initiator Setup:** Configuring the KVM host to discover and log in to the remote iSCSI targets using the `iscsi-initiator-utils` suite.
3. **Storage Pool Integration:** Using `virsh` to create an iSCSI storage pool that integrates directly with the `libvirt` management layer.
4. **VM Data Offloading:** Migrating or creating new virtual machine disks directly on the iSCSI LUNs, ensuring the hypervisor stores VM data on the remote SAN rather than locally.

## Authors

- ATTIA Oussama Abderraouf
- SRAICH Imene

**Supervised by:** Dr. MENNACER Djamel-Eddine  
**Institution:** Ecole Nationale Superieure d'Informatique (ESI)  
**Academic Year:** 2025 - 2026