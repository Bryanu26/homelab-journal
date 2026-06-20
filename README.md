# Project Ascent 101

## Objective

Transition from Network & Infrastructure Technician to Network Engineer through hands-on networking, virtualization, Linux, security, and troubleshooting projects.

---

# Hardware

## Rack Infrastructure

* Rack
* Patch Panel
* Power Distribution

## Network

* UCG Ultra
* USW Lite 8 PoE
* AP-101

## Compute

### Lenovo ThinkStation P320 Tiny

* Intel i7-7700T
* 16GB RAM
* 512GB NVMe SSD
* Proxmox VE

## Endpoints

* Desktop-101
* MacBook Air
* iPhone
* Apple TV

---

# Current Network

Internet
↓
Modem
↓
UCG Ultra
↓
USW Lite 8 PoE
↓
Proxmox Server

Current LAN:

10.10.1.0/24

Gateway:

10.10.1.1

---

# Current Devices

## Network Infrastructure

| Device         | IP Address  | Purpose               |
| -------------- | ----------- | --------------------- |
| UCG Ultra      | 10.10.1.1   | Gateway / Router      |
| AP-101         | 10.10.1.91  | Wireless Access Point |
| USW Lite 8 PoE | 10.10.1.196 | Managed Switch        |

## Endpoints

| Device      | IP Address | Purpose             |
| ----------- | ---------- | ------------------- |
| Desktop-101 | 10.10.1.62 | Primary Workstation |
| MacBook Air | DHCP       | User Device         |
| iPhone      | DHCP       | User Device         |
| Apple TV    | DHCP       | Media Device        |

## Virtualization

| Device        | IP Address  | Purpose      |
| ------------- | ----------- | ------------ |
| Ubuntu-Server | 10.10.1.49  | Linux Server |
| Proxmox Host  | 10.10.1.223 | Hypervisor   |

---

# Planned VLANs

## VLAN 10 - Management

* Router
* Switch
* Access Points
* Proxmox Management

## VLAN 20 - Users

* Desktop
* MacBook
* iPhone
* Apple TV

## VLAN 30 - Servers

* Ubuntu Server
* Windows Server
* Grafana
* Wazuh
* Future NAS

## VLAN 40 - Lab

* Kali Linux
* Metasploitable
* Testing VMs

---

# Build Log

## Project 001 - WAN Network Conflict

Date:
2026-06

Issue:
No internet after moving modem connection from LAN1 to LAN2.

Hypothesis:
WAN network conflict.

Findings:
Modem LAN network and router LAN network overlapped.

LAN1:
192.168.1.1

Router LAN:
192.168.1.1

Resolution:
Changed router LAN network from 192.168.1.1/24 to 10.10.1.1/24.

Result:
Internet connectivity restored.

Lessons Learned:
Verify upstream / downstream networks are not using overlapping subnets.

---

## Project 002 - Proxmox Installation

Date:
2026-06

Objective:
Deploy Proxmox Virtual Environment on a Lenovo ThinkStation P320 Tiny.

Hardware:

* Lenovo ThinkStation P320 Tiny
* Intel i7-7700T
* 16GB RAM
* 512GB NVMe SSD

Installation Process:

* Downloaded Proxmox VE
* Created bootable USB using Rufus
* Configured BIOS
* Installed Proxmox VE

Result:
Successful installation completed.

---

## Project 003 - BIOS Virtualization Troubleshooting

Issue:
Proxmox installer reported:

"No support for hardware-accelerated KVM virtualization detected."

Investigation:

Checked BIOS CPU settings.

Findings:

Intel Virtualization Technology was disabled.

Resolution:

Enabled Intel Virtualization Technology in BIOS.

Result:

Proxmox installation proceeded successfully.

Lessons Learned:

Always verify virtualization support before deploying hypervisors.

---

## Project 004 - DisplayPort Boot Troubleshooting

Issue:

BIOS and boot screens would not display correctly through DisplayPort.

Symptoms:

* Black screen during boot
* Unable to access BIOS reliably
* Display appeared corrupted or scaled incorrectly

Troubleshooting:

* Tested DisplayPort connection
* Tested alternate display methods

Resolution:

Used Thunderbolt-to-DisplayPort adapter.

Result:

Successfully accessed BIOS and boot menu.

Lessons Learned:

Video output behavior can differ between BIOS and operating system environments.

---

## Project 005 - Bootable USB Troubleshooting

Issue:

Unable to create bootable Proxmox USB.

Findings:

The Proxmox ISO file was stored on the same USB drive being used as the installation target.

Resolution:

Moved the ISO to local storage and recreated the USB.

Result:

Bootable installation media created successfully.

Lessons Learned:

Installation media and source ISO cannot reside on the same target drive.

---

## Project 006 - First Virtual Machine

Date:
2026-06

Objective:
Deploy first virtual machine inside Proxmox.

Operating System:
Ubuntu Server 24.04 LTS

Resources Allocated:

* 2 vCPU
* 4GB RAM
* 32GB Storage

Result:
Successfully deployed Ubuntu Server VM.

Validation:

* Received DHCP address
* Internet connectivity verified
* DNS resolution verified

Assigned Address:
10.10.1.49

Lessons Learned:
A hypervisor is only the beginning. The real value comes from the services and virtual machines running inside it.

---

# Current Skills Being Developed

* Proxmox VE
* Virtualization
* Linux
* Network Troubleshooting
* VLAN Design
* Routing
* Switching
* Documentation
* Homelab Design
* Infrastructure Planning

---

# Upcoming Projects

* Ubuntu Administration
* SSH
* Docker
* Windows Server
* Active Directory
* VLAN Segmentation
* WireGuard VPN
* OPNsense Firewall
* Grafana Monitoring
* Wazuh Security Monitoring
* Remote Management
* Backup Strategy
* Network Monitoring

---

# Recruiter Summary

Project Ascent 101 is a self-directed infrastructure and networking lab designed to develop practical experience in:

* Virtualization (Proxmox VE)
* Linux Administration
* Routing and Switching
* VLAN Design
* Network Troubleshooting
* VPN Technologies
* Windows Server
* Active Directory
* Monitoring and Security Platforms

The objective is to build hands-on experience relevant to NOC, MSP, System Administration, and Network Engineering roles through documented projects and real-world troubleshooting scenarios.

---

# Goal

Build a production-style homelab that demonstrates practical networking, virtualization, Linux, security, and troubleshooting skills relevant to NOC, MSP, System Administration, and Network Engineering roles.
