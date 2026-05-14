# Lab 01 — Active Directory Domain Controller Build

## Overview
Built a fully functional Active Directory domain from scratch on Windows Server 2012 R2 running in VirtualBox. This lab mirrors a real production environment.

## Environment
- **Platform:** Oracle VirtualBox
- **OS:** Windows Server 2012 R2 Standard Evaluation
- **Server Name:** Lab-DC01
- **Domain:** lab.local
- **Static IP:** 192.168.1.200

## Roles Installed
- Active Directory Domain Services (AD DS)
- DHCP Server
- DNS Server

## What Was Built

### Domain Controller
- Promoted Windows Server 2012 R2 to Domain Controller
- Created new forest with domain name lab.local
- Configured static IP at 192.168.1.200

### DHCP Configuration
- Created DHCP scope: 192.168.1.100 — 192.168.1.199
- Set default gateway: 192.168.1.1
- Set DNS server: 192.168.1.200
- Scope status: Active

### Active Directory Structure
- Created Organizational Units: IT, HR, Production
- Created user accounts in each OU:
  - jsmith — IT Department
  - sjones — HR Department
  - mdavis — Production Department
- Created security group: IT-Admins
- Added jsmith to IT-Admins group

### User Management Tasks Performed
- Reset user password with force change on next logon
- Disabled and re-enabled a user account
- Located account unlock option in user properties

### Group Policy
- Created GPO: Password Policy
- Linked to lab.local domain
- Configured minimum password length of 8 characters

## Key Commands Used
```powershell
# Verify static IP configuration
ipconfig

# Test network connectivity
ping 8.8.8.8
```

## Screenshots
See screenshots folder for documented evidence of each step.

## Skills Demonstrated
- Windows Server administration
- Active Directory deployment and configuration
- DHCP scope creation and management
- DNS configuration
- OU and user account management
- Group Policy Object creation and linking
- VM snapshot management
