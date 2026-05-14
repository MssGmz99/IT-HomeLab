# Lab 04 — Windows Event Viewer on Domain Controller

## Overview
Navigated and interpreted Windows Event Viewer logs on a live Windows Server 2012 R2 Domain Controller. Analyzed system, security, and AD-specific logs to diagnose events and monitor domain activity. Server logs contain significantly more detail and relevance than workstation logs.

## Environment
- **Platform:** Windows Server 2012 R2 VM (VirtualBox)
- **Domain:** lab.local
- **Server:** Lab-DC01
- **Tools Used:** Event Viewer (eventvwr.msc)

## How to Open
- Server Manager → Tools → Event Viewer
- Windows Key + R → eventvwr.msc

## Event Viewer Overview
- **Total Security Events:** 4,165
- **Total System Events:** 1,168
- **Critical events (7 days):** 2
- **Errors (7 days):** 27
- **Warnings (7 days):** 65
- **Audit Success events (7 days):** 3,919

## Key Logs Reviewed

| Log | Location | Events |
|---|---|---|
| System | Windows Logs | 1,168 events |
| Security | Windows Logs | 4,165 events |
| Directory Service | Applications and Services Logs | 63 events |
| DNS Server | Applications and Services Logs | 15 events |

## Tasks Performed

### Task 1 — System Log Analysis
- Opened System log and reviewed errors and warnings
- Identified Event ID 1076 — User32 — unexpected shutdown warning
- Description: LAB\Administrator supplied reason for last unexpected shutdown as Other (Unplanned)
- Identified Event ID 6008 — EventLog — unexpected shutdown confirmation
- Identified Event ID 34 — disk warnings
- Identified Event ID 10020 — DHCP-Server warning
- Identified Event ID 12 — Time-Service synchronization warning

### Task 2 — Security Log Analysis
- Opened Security log and reviewed audit events
- Identified 3 failed logon events — Event ID 4625
- Failed account: Guest attempting network logon (Logon Type 3)
- Determined attempts were from initial VM setup — not a security threat
- Filtered for Event ID 4624 — found 946 successful logon events
- Confirmed high volume is normal for Domain Controllers running background services

### Task 3 — Directory Service Log
- Expanded Applications and Services Logs
- Opened Directory Service log — 63 events
- Identified Event ID 1869 — ActiveDirectory_DomainService
- Description: AD Domain Services located a global catalog at Lab-DC01.lab.local
- Identified Event ID 700/701 — NTDS ISAM Online Defragmentation — normal AD maintenance
- Confirmed Domain Controller is functioning correctly

### Task 4 — DNS Server Log
- Opened DNS Server log — 15 events
- Identified Event ID 4 — DNS-Server-Service
- Description: DNS server finished background loading and signing of zones
- Identified Event ID 4013 Warning — DNS waiting for AD initialization during boot
- Confirmed DNS service fully operational — all zones available for updates

### Task 5 — Custom View Creation
- Clicked Create Custom View in Actions panel
- Set filter: Last 7 days, Critical/Error/Warning levels
- Selected Windows Logs — System and Security
- Named view: DC-Critical-Events
- View showed 2 Error events — Event ID 1101 audit events dropped by transport
- Custom view saved under Custom Views for ongoing monitoring

## Key Event IDs — Domain Controller Specific

| Event ID | Source | Meaning |
|---|---|---|
| 4624 | Security | Successful logon |
| 4625 | Security | Failed logon attempt |
| 1076 | User32 | Unexpected shutdown reason logged |
| 6008 | EventLog | Unexpected shutdown occurred |
| 1869 | AD DomainService | Global catalog located |
| 700/701 | NTDS ISAM | AD database defragmentation |
| 4013 | DNS-Server | DNS waiting for AD during boot |
| 1101 | Eventlog | Audit events dropped by transport |

## Key Concepts
- Domain Controllers generate thousands of security events daily — this is normal
- Directory Service and DNS Server logs only exist on Domain Controllers
- 946 successful logon events on a DC is normal — background services authenticate constantly
- Event ID 4013 DNS warning during boot is expected — DNS waits for AD to initialize first
- Custom Views save time for repeated monitoring tasks
- A spike in 4625 events in a short window indicates potential brute force or lockout

## Screenshots
See screenshots folder for documented evidence of each task.
