# Lab 10 — Windows Services Management on Domain Controller

## Overview
Practiced starting, stopping, restarting, and configuring Windows services on a live Windows Server 2012 R2 Domain Controller. Server services are significantly more critical than workstation services — stopping the wrong service can take down authentication for the entire domain.

## Environment
- **Platform:** Windows Server 2012 R2 VM (VirtualBox)
- **Domain:** lab.local
- **Server:** Lab-DC01
- **Tools Used:** Services Manager (services.msc), PowerShell (Administrator)

## How to Open
Server Manager → Tools → Services

Windows Key + R → services.msc

## Critical Domain Controller Services

| Service | Status | Purpose |
|---|---|---|
| Active Directory Domain Services | Running — Automatic | Core AD service — manages the domain |
| Active Directory Web Services | Running — Automatic | Web interface for AD management |
| DNS Server | Running — Automatic | Resolves domain names on the network |
| DHCP Server | Running — Automatic | Assigns IP addresses to domain devices |
| Kerberos Key Distribution Center | Running — Automatic | Handles domain authentication |
| Netlogon | Running — Automatic | Required for users to log into the domain |
| DFS Namespace | Running — Automatic | Distributed file system namespace |
| DFS Replication | Running — Automatic | Replicates files across the domain |

## Tasks Performed

### Task 1 — Identified Critical Server Services
- Opened Services Manager on Domain Controller
- Identified AD-specific services not present on regular workstations
- Noted Active Directory Domain Services, Active Directory Web Services, DFS Namespace, DFS Replication, DHCP Server all running automatically
- Confirmed server is functioning correctly with all critical services running

### Task 2 — Restarted DHCP Server Service
- Located DHCP Server in services list
- Right clicked and selected Restart
- Confirmed service stopped and restarted successfully
- Confirmed status returned to Running
- Simulated resolving a DHCP outage where users cannot get IP addresses

### Task 3 — Reviewed Active Directory Domain Services Properties
- Opened AD DS Properties
- Confirmed Startup Type: Automatic
- Reviewed Recovery tab — configured to restart on failure
- Reviewed Dependencies tab — identified services AD DS relies on
- Learned that if a dependency fails AD DS cannot start

### Task 4 — Reviewed Netlogon Service Properties
- Located Netlogon service
- Opened Properties and reviewed all tabs
- Confirmed Startup Type: Automatic
- Identified Netlogon as critical — if stopped users cannot authenticate to domain
- Reviewed dependencies and recovery settings

### Task 5 — Reviewed Kerberos Key Distribution Center
- Located KDC service in services list
- Read description — handles Kerberos authentication for the domain
- Reviewed properties
- Confirmed KDC is critical — if stopped no domain authentication is possible

### Task 6 — Managed Services via PowerShell
- Opened PowerShell as Administrator
- Checked DHCP Server status using Get-Service
- Stopped DHCP Server using Stop-Service
- Started DHCP Server using Start-Service
- Verified service returned to Running status

```powershell
# Check service status
Get-Service -Name DHCPServer

# Stop the service
Stop-Service -Name DHCPServer

# Start the service
Start-Service -Name DHCPServer

# Verify running
Get-Service -Name DHCPServer
```

### Task 7 — Disabled and Re-enabled a Non-Critical Service
- Located Computer Browser service — already Disabled by default on Server 2012 R2
- Changed Startup Type to Manual
- Started the service
- Confirmed service running with Manual startup type
- Stopped the service and changed Startup Type back to Disabled
- Simulated disabling a problematic service to prevent auto-start

### Task 8 — Exported Running Services to CSV
- Used PowerShell to list all running services in table format
- Exported running services list to CSV file at C:\services-report.csv
- Verified file was created successfully

```powershell
# List all running services
Get-Service | Where-Object {$_.Status -eq "Running"} | Select-Object Name, Status, StartType | Format-Table -AutoSize

# Export to CSV
Get-Service | Where-Object {$_.Status -eq "Running"} | Select-Object Name, Status | Export-Csv -Path C:\services-report.csv -NoTypeInformation

# Verify file created
Get-Item C:\services-report.csv
```

## Key Concepts
- Domain Controller services are critical — stopping the wrong one affects all domain users
- Netlogon and KDC are required for domain authentication — never stop these in production without a maintenance window
- DHCP Server going down means new devices cannot get IP addresses
- PowerShell Get-Service and Stop-Service/Start-Service are the modern server management approach
- Always check Dependencies tab before stopping a service — other services may rely on it
- Exporting service lists to CSV is useful for baseline documentation and change management

## Interview Answer
When asked about services management on a server:

"On a Domain Controller I'm careful about which services I touch because stopping the wrong one can affect authentication for every user on the domain. I use PowerShell's Get-Service, Stop-Service, and Start-Service for quick management, and I always check the Dependencies tab before making changes to understand what else might be affected. Before stopping any critical service in production I would schedule a maintenance window and notify users."

## Screenshots
See screenshots folder for documented evidence of each task.
