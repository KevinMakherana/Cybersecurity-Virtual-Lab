# Cybersecurity Virtual Lab (SOC Training Environment)

## Overview

This project is a virtual cybersecurity lab built using VMware Workstation Pro. It simulates a small Security Operations Center (SOC) environment where Kali Linux is used as an attacker workstation and interacts with target systems including Windows 10 and Metasploitable 2.

The purpose of this project is to demonstrate practical skills in:

* Virtual machine deployment and management
* Network configuration and segmentation
* Isolated lab environment setup
* Cybersecurity and SOC fundamentals
* Network troubleshooting and validation
* Security testing preparation

---

## Skills Demonstrated

* VMware Workstation Pro Administration
* Virtual Machine Deployment
* Network Segmentation
* NAT and Host-Only Networking
* IP Address Configuration
* Linux Administration
* Windows Administration
* Cybersecurity Lab Design
* Network Troubleshooting
* Technical Documentation

---

## Tools Used

* VMware Workstation Pro
* Kali Linux
* Windows 10
* Metasploitable 2
* Linux Networking Utilities
* Windows Networking Tools

---

# Phase 1: Virtual Machine Setup

## Overview

In this phase, all virtual machines were created and configured using VMware Workstation Pro.

All systems were initially configured with NAT networking to provide internet access for operating system installation, software updates, and initial system configuration.

This phase focuses on establishing the foundation of the cybersecurity lab environment.

---

## 1. VMware Workstation Pro Dashboard

The VMware Workstation Pro dashboard used to create, manage, and monitor all virtual machines within the lab environment.

![VMware Dashboard](./images/phase1/vmware-home.png)

---

## 2. Kali Linux Virtual Machine (Initial Setup)

Kali Linux was configured as the primary security testing and attack simulation machine.

**Configuration:**

* Memory: 4 GB RAM
* CPU: 4 Cores
* Storage: 100 GB
* Network: NAT (Initial Setup)

![Kali NAT Setup](./images/phase1/kali-nat.png)

---

## 3. Windows 10 Virtual Machine (Initial Setup)

Windows 10 was configured as a target system for testing, monitoring, and security assessments.

**Configuration:**

* Memory: 4 GB RAM
* CPU: 2 Cores
* Storage: 40 GB
* Network: NAT (Initial Setup)

![Windows NAT Setup](./images/phase1/windows-nat.png)

---

## 4. Metasploitable 2 Virtual Machine (Initial Setup)

Metasploitable 2 was deployed as a deliberately vulnerable system for penetration testing and security training purposes.

**Configuration:**

* Memory: 512 MB
* Storage: 8 GB
* Network: NAT (Initial Setup)

![Metasploitable NAT Setup](./images/phase1/metasploitable-nat.png)

---

## Phase 1 Summary

All virtual machines were successfully deployed and configured using NAT networking to provide internet access for software installation, updates, and initial setup activities.

This phase established the foundation required for network segmentation, connectivity testing, and future security assessments.

---

# Phase 2: Network Segmentation & Lab Isolation

## Overview

In this phase, the virtual lab environment was reconfigured to establish a controlled and isolated internal network for cybersecurity testing.

The goal was to separate internal lab traffic from external internet access while enabling controlled communication between virtual machines.

This configuration simulates a realistic SOC and penetration testing environment where security assessments can be performed safely.

---

## Objectives

* Configure an isolated virtual network using VMware Workstation Pro
* Implement Host-Only networking for internal communication
* Validate IP addressing across all virtual machines
* Confirm connectivity between attacker and target systems
* Prepare the environment for scanning and security testing

---

## 1. Virtual Network Editor Configuration

VMware Virtual Network Editor was used to configure the isolated lab network.

The Host-Only network (VMnet1) was configured as follows:

![Virtual Network Editor](./images/phase2/virtual-network-editor.png)

**Configuration:**

* Network Type: Host-Only (VMnet1)
* Subnet: 192.168.242.0/24
* DHCP: Enabled
* Host Adapter: Connected

---

## 2. Windows 10 Network Configuration

Windows 10 was configured as a target machine within the isolated network.

![Windows Host-Only](./images/phase2/windows-hostonly.png)

**Configuration:**

* Network Mode: Host-Only
* IP Address: 192.168.242.129
* Subnet Mask: 255.255.255.0

---

## 3. Metasploitable 2 Network Configuration

Metasploitable 2 was configured as a vulnerable target system within the isolated lab network.

![Metasploitable Host-Only](./images/phase2/metasploitable-hostonly.png)

**Configuration:**

* Network Mode: Host-Only
* IP Address: 192.168.242.130
* Subnet Mask: 255.255.255.0

---

## 4. Kali Linux Network Configuration

Kali Linux was configured as the attacker machine within the lab environment.

To support both internet access and internal testing, Kali Linux was configured with dual network interfaces.

![Kali Network Configuration](./images/phase2/kali-network.png)

**Network Interfaces:**

* NAT Interface (Internet Access)
* Host-Only Interface (Internal Lab Network)

This dual-network configuration allows Kali Linux to access online resources while maintaining communication with systems inside the isolated lab environment.

---

## 5. IP Address Verification

IP configurations were validated across all systems to confirm proper network segmentation and connectivity.

![Kali IP](./images/phase2/kali-ip.png)

![Windows IP](./images/phase2/windows-ip.png)

![Metasploitable IP](./images/phase2/metasploitable-ip.png)

**Results:**

* Kali Linux: 192.168.242.131
* Windows 10: 192.168.242.129
* Metasploitable 2: 192.168.242.130

All systems were successfully assigned addresses within the same isolated subnet.

---

## 6. Connectivity Testing

Connectivity tests were performed using ICMP (ping) from Kali Linux to validate communication within the lab network.

### Tests Performed:

* Kali Linux → Windows 10
* Kali Linux → Metasploitable 2

---

### Results:

**Kali Linux → Windows 10**

No ICMP response was received. This behaviour is expected because Windows Firewall blocks inbound ICMP requests by default.

**Kali Linux → Metasploitable 2**

Successful communication was confirmed through stable ICMP replies, verifying connectivity within the isolated environment.

![Connectivity Test](./images/phase2/ping-test.png)

---

## Phase 2 Summary

Phase 2 successfully established a controlled and isolated virtual network environment using VMware Workstation Pro.

All virtual machines were configured within a shared Host-Only subnet, enabling internal communication while maintaining isolation from external networks.

This environment forms the foundation for reconnaissance, vulnerability assessment, security testing, and controlled attack simulation activities.

---

## Key Learning Outcomes

Through this phase of the project, I gained practical experience in:

* Deploying and managing virtual machines
* Configuring NAT and Host-Only networking
* Designing isolated cybersecurity testing environments
* Performing network troubleshooting and validation
* Understanding network segmentation concepts
* Documenting cybersecurity projects using industry-style reporting

---

## Next Phase Preview

Phase 3 will focus on:

* Network reconnaissance using Nmap
* Host discovery and port scanning
* Service enumeration
* Vulnerability identification on Metasploitable 2
* Initial attack surface analysis using Kali Linux
