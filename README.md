# Cybersecurity Virtual Lab (SOC Training Environment)

## Overview

This project is a virtual cybersecurity lab built using VMware Workstation Pro. It simulates a small Security Operations Center (SOC) environment where an attacker machine (Kali Linux) interacts with vulnerable and target systems (Windows 10 and Metasploitable 2).

The purpose of this project is to demonstrate practical skills in:
- Virtual machine deployment and management
- Network configuration and segmentation
- Isolated lab environment setup
- Basic cybersecurity and SOC fundamentals

---

# Phase 1: Virtual Machine Setup

## Overview

In this phase, all virtual machines were created and configured using VMware Workstation Pro.  
All systems were initially set to NAT networking to allow internet access for installation, updates, and initial setup.

This phase focuses on building the foundation of the lab environment.

---

## 1. VMware Workstation Pro Dashboard

The VMware interface used to create and manage all virtual machines in the lab.

![VMware Dashboard](./images/phase1/vmware-home.png)

---

## 2. Kali Linux Virtual Machine (Initial Setup)

Kali Linux was configured as the primary security testing machine.

**Configuration:**
- Memory: 4 GB RAM  
- CPU: 4 Cores  
- Storage: 100 GB  
- Network: NAT (initial setup)

![Kali NAT Setup](./images/phase1/kali-nat.png)

---

## 3. Windows 10 Virtual Machine (Initial Setup)

Windows 10 was configured as a target system for testing and simulation.

**Configuration:**
- Memory: 4 GB RAM  
- CPU: 2 Cores  
- Storage: 40 GB  
- Network: NAT (initial setup)

![Windows NAT Setup](./images/phase1/windows-nat.png)

---

## 4. Metasploitable 2 Virtual Machine (Initial Setup)

Metasploitable 2 was deployed as a deliberately vulnerable system for penetration testing practice.

**Configuration:**
- Memory: 512 MB  
- Storage: 8 GB  
- Network: NAT (initial setup)

![Metasploitable NAT Setup](./images/phase1/metasploitable-nat.png)

---

## Phase 1 Summary

All virtual machines were successfully deployed and configured using NAT networking to provide internet access for installation and updates.

This phase establishes the base environment for further network segmentation and security testing.

---

# Phase 2: Network Segmentation & Lab Isolation

## Overview

In this phase, the virtual lab environment was reconfigured to establish a controlled and isolated internal network for security testing.

The goal was to separate internal lab traffic from external internet access and enable controlled communication between virtual machines.

This setup simulates a real-world SOC or penetration testing environment.

---

## Objectives

- Configure an isolated virtual network using VMware Workstation Pro
- Implement Host-Only networking for internal communication
- Validate IP addressing across all virtual machines
- Confirm connectivity between attacker and target systems
- Prepare environment for scanning and security testing

---

## 1. Virtual Network Editor Configuration

VMware Virtual Network Editor was used to configure the isolated lab network.

The Host-Only network (VMnet1) was configured as follows:

![Virtual Network Editor](./images/phase2/virtual-network-editor.png)

**Configuration:**
- Network Type: Host-Only (VMnet1)
- Subnet: 192.168.242.0/24
- DHCP: Enabled
- Host Adapter: Connected

---

## 2. Windows 10 Network Configuration

Windows 10 was configured as a target machine within the isolated network.

![Windows Host-Only](./images/phase2/windows-hostonly.png)

**Configuration:**
- IP Address: 192.168.242.131
- Subnet Mask: 255.255.255.0

---

## 3. Metasploitable 2 Network Configuration

Metasploitable 2 was configured as a vulnerable target system.

![Metasploitable Host-Only](./images/phase2/metasploitable-hostonly.png)

**Configuration:**
- IP Address: 192.168.242.130
- Subnet Mask: 255.255.255.0

---

## 4. Kali Linux Network Configuration

Kali Linux was configured as the attacker machine in the lab environment.

It operates with dual network interfaces:

![Kali Network Configuration](./images/phase2/kali-network.png)

**Network Interfaces:**
- NAT Interface (Internet access)
- Host-Only Interface (Internal lab network)

---

## 5. IP Address Verification

IP configurations were validated across all systems to confirm proper network segmentation.

![Kali IP](./images/phase2/kali-ip.png)  
![Windows IP](./images/phase2/windows-ip.png)  
![Metasploitable IP](./images/phase2/metasploitable-ip.png)

**Results:**
- Kali Linux: 192.168.242.131
- Windows 10: 192.168.242.129
- Metasploitable 2: 192.168.242.130

All systems are operating within the same isolated subnet.

---

## 6. Connectivity Testing

Connectivity tests were performed using ICMP (ping) from Kali Linux to validate communication within the lab network.

### Tests Performed:
- Kali → Windows 10  
- Kali → Metasploitable 2  

---

### Results:

**Kali → Windows 10**  
No response received. Windows Firewall is configured to block ICMP traffic by default.

**Kali → Metasploitable 2**  
Successful communication confirmed with stable ICMP replies.

![Connectivity Test](./images/phase2/ping-test.png)

---

## Phase 2 Summary

Phase 2 successfully established a controlled and isolated virtual network environment using VMware Workstation Pro.

All virtual machines were configured within a shared Host-Only subnet, enabling internal communication while maintaining isolation from external networks.

This environment forms the foundation for security testing, vulnerability scanning, and controlled attack simulation.

---

## Next Phase Preview

Phase 3 will focus on:

- Network reconnaissance using Nmap
- Host discovery and port scanning
- Service enumeration
- Vulnerability identification on Metasploitable 2
- Initial attack surface analysis using Kali Linux
