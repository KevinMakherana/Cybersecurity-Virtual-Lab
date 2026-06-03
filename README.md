# Cybersecurity Virtual Lab (SOC Training Environment)

## Overview

This project is a virtual cybersecurity lab built using VMware Workstation Pro. It simulates a small Security Operations Center (SOC) environment where an attacker machine (Kali Linux) interacts with vulnerable and target systems (Windows 10 and Metasploitable 2).

The goal of this project is to demonstrate practical skills in:

- Virtual machine deployment  
- Network configuration  
- Isolated lab environment setup  
- Cybersecurity fundamentals and SOC awareness  

---

# Phase 1: Virtual Machine Setup (Initial Installation)

In this phase, all virtual machines were created and configured using VMware Workstation Pro.  
All systems were initially configured using **NAT networking** to allow internet access for installation, updates, and initial setup.

---

## 1. VMware Workstation Pro Dashboard

The VMware environment used to create and manage all virtual machines in this lab.

![VMware Workstation Pro Dashboard](./images/phase1/vmware-home.png)

---

## 2. Kali Linux Virtual Machine (Initial Setup)

Kali Linux was configured as the primary security testing machine.

**Configuration:**
- Memory: 4 GB RAM  
- CPU: 4 Cores  
- Storage: 100 GB  
- Network: NAT (initial setup)

![Kali Linux NAT Configuration](./images/phase1/kali-nat.png)

---

## 3. Windows 10 Virtual Machine (Initial Setup)

Windows 10 was configured as a target system for testing and simulation.

**Configuration:**
- Memory: 4 GB RAM  
- CPU: 2 Cores  
- Storage: 40 GB  
- Network: NAT (initial setup)

![Windows 10 NAT Configuration](./images/phase1/windows-nat.png)

---

## 4. Metasploitable 2 Virtual Machine (Initial Setup)

Metasploitable 2 was deployed as a deliberately vulnerable system for penetration testing practice.

**Configuration:**
- Memory: 512 MB  
- Storage: 8 GB  
- Network: NAT (initial setup)

![Metasploitable 2 NAT Configuration](./images/phase1/metasploitable-nat.png)

---

# Phase 1 Summary

All virtual machines were successfully installed and configured using NAT networking to provide internet access for setup and updates.

This phase establishes the foundation of the cybersecurity lab before moving into network segmentation and isolated attack simulation in the next phase.
