# 🏡 John Wesley Paige Jr. Home Lab Project

This project documents the build and implementation of a hybrid cloud-enabled cybersecurity home lab. It includes local self-hosted services, log monitoring, VPN tunneling, and secure data offloading to the cloud.

---

## 💻 Lab Hardware

- **Jetway Mini PC**: Running pfSense (firewall & OpenVPN server)
- **Dell XPS 420**: Future Splunk/Suricata deployment
- **HP 17-cn0xxx Laptop**: Main workstation, Azure/AWS interaction
- **External SSD**: For local backups and log storage
- **Router/AP & Switch**: Pending deployment for full segmented networking

---

## 🌐 Network Architecture

- **pfSense Firewall**:
  - LAN/VPN segmentation
  - OpenVPN (Remote Access & Site-to-Site options)
  - Rules configured to route specific subnets through VPN
- **DNS, DHCP, and VLANs** handled via pfSense
- **Windows Server 2019**:
  - Hosting AD DS for internal domain management
  - DNS Forwarding to pfSense

---

## ☁️ Hybrid Cloud Integration (Azure)

### 🎯 Goal:
Offload logs and backups securely to an Azure Blob for hybrid network resilience and log redundancy.

### 🔧 Implementation:
- **Service Used**: Azure
- **Tools**:
  - AWS CLI configured on local systems
  - Cron jobs & Bash scripts to upload logs from:
    - pfSense
    - Suricata (planned)
    - Windows Server 2019 Event Logs (future via PowerShell)
   
    - This document is a living blueprint of the evolving Paige Home Lab. Configs and implementations are updated as new services come online.
