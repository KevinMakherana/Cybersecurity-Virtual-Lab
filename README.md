# Cybersecurity Virtual Lab (SOC Training Environment)

## Overview

This project is a virtual cybersecurity lab built using VMware Workstation Pro. It simulates a small Security Operations Center (SOC) environment where an attacker machine (Kali Linux) interacts with vulnerable and target systems (Windows 10 and Metasploitable 2).

The goal of this project is to demonstrate practical skills in:
- Virtual machine deployment
- Network configuration
- Lab environment setup
- Cybersecurity fundamentals

---

# Phase 1: Virtual Machine Setup (Initial Installation)

In this phase, all virtual machines were created and configured using VMware Workstation Pro. At this stage, all machines were initially set to NAT networking to allow internet access for installation and updates.

---

## 1. VMware Workstation Pro Dashboard

This shows the initial environment where all virtual machines were created and managed.

![VMware Dashboard](images/phase1/vmware-home.png)

---

## 2. Kali Linux Virtual Machine (Initial Setup)

Kali Linux was configured as the primary security testing machine.

- Memory: 4 GB RAM  
- CPU: 4 Cores  
- Storage: 100 GB  
- Network: NAT (initial setup)

![Kali NAT Setup](images/phase1/kali-nat.png)

---

## 3. Windows 10 Virtual Machine (Initial Setup)

Windows 10 was configured as a target system for testing and simulation.

- Memory: 4 GB RAM  
- CPU: 2 Cores  
- Storage: 40 GB  
- Network: NAT (initial setup)

![Windows NAT Setup](images/phase1/windows-nat.png)

---

## 4. Metasploitable 2 Virtual Machine (Initial Setup)

Metasploitable 2 was deployed as a deliberately vulnerable system for penetration testing practice.

- Memory: 512 MB  
- Storage: 8 GB  
- Network: NAT (initial setup)

![Metasploitable NAT Setup](images/phase1/metasploitable-nat.png)

---

# Summary of Phase 1

In this phase, all virtual machines were successfully installed and configured using NAT networking to ensure internet access for setup and updates. This forms the foundation for the next phase, where network segmentation and lab isolation will be implemented.
