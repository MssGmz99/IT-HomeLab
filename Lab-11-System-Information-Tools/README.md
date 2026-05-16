# Lab 11 — System Information Tools

## Overview
Used Windows system information tools to pull hardware specs, driver versions, and system details from a live Windows 11 machine. These tools are essential when troubleshooting hardware issues, ordering replacement parts, or escalating a ticket to T2.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Device:** Dell Inspiron 14 7420 2-in-1
- **Tools Used:** msinfo32, dxdiag, Command Prompt (systeminfo)

## How to Open Key Tools
- System Information: Windows Key + R → msinfo32
- DirectX Diagnostic: Windows Key + R → dxdiag
- System Info CMD: Command Prompt → systeminfo

## Tool Comparison

| Tool | Best For |
|---|---|
| msinfo32 | Full hardware overview, problem devices, driver info |
| dxdiag | Display and audio issues, saving full spec report |
| systeminfo | Quick command line snapshot, uptime, network info, hotfixes |

## What to Pull From Each Tool

| Info Needed | Where to Find It |
|---|---|
| RAM amount | msinfo32 System Summary or systeminfo |
| Graphics adapter and driver version | msinfo32 Components > Display or dxdiag Display tab |
| Problem hardware | msinfo32 Components > Problem Devices |
| Last boot time | systeminfo |
| Installed Windows updates | systeminfo Hotfixes section |
| Network adapter and IP | systeminfo Network Card section |
| DirectX version | dxdiag System tab |
| BIOS version | msinfo32 System Summary or dxdiag |

## Tasks Performed

### Task 1 — msinfo32 System Summary
- Opened System Information via msinfo32
- Read full system summary including:
  - OS: Windows 11 Home
  - Model: Dell Inspiron 14 7420 2-in-1
  - Processor: 12th Gen Intel Core i5-1235U
  - RAM: 8GB
  - BIOS Mode: UEFI
  - Secure Boot: Enabled
  - System Type: x64-based PC
  - Platform Role: Mobile — confirms laptop

### Task 2 — Display Components
- Expanded Components in left panel
- Clicked Display to view graphics adapter details
- Identified two display adapters:
  - Meta Virtual Monitor — Oculus VR virtual display
  - Intel Iris Xe Graphics — real graphics adapter
- Noted Intel Iris Xe Graphics specs:
  - Adapter RAM: 2.00 GB
  - Resolution: 1920x1200 at 60hz
  - Driver Version: 32.0.101.7084
- Learned to identify graphics adapter and driver version for display troubleshooting

### Task 3 — Problem Devices
- Clicked Problem Devices under Components
- Identified Dell Data Vault Control Device entries with Error Code 48
- Error Code 48 means Windows blocked a driver from loading
- Determined Dell Data Vault is non-critical telemetry software
- Assessed impact — no functional issues for the user
- Documented finding without taking unnecessary action

### Task 4 — dxdiag System Tab
- Opened DirectX Diagnostic Tool via dxdiag
- Reviewed System tab including:
  - OS: Windows 11 Home 64-bit
  - Processor: 12th Gen Intel Core i5-1235U — 12 CPUs
  - Memory: 8192MB RAM
  - DirectX Version: DirectX 12
  - Page file usage — confirmed memory pressure
  - BIOS version confirmed

### Task 5 — dxdiag Display Tab
- Clicked Display tab at top of dxdiag
- Reviewed graphics adapter details
- Checked Notes section at bottom
- Confirmed No problems found on display
- Checked Sound tabs — confirmed No problems found on all sound devices

### Task 6 — systeminfo Command
- Opened Command Prompt
- Ran systeminfo command
- Read key system details:
  - Original Install Date
  - Last Boot Time — identified days since last reboot
  - Available RAM — confirmed memory constrained
  - Installed Hotfixes — 4 Windows updates applied
  - Network adapter details — DHCP enabled, IP address, gateway
  - Domain — WORKGROUP confirms not domain joined

## Key Concepts
- **Error Code 48** means Windows blocked a driver — investigate if it affects the user
- **Save dxdiag output** before escalating to T2 — attach it to the ticket
- **Last boot time** shows if machine hasn't restarted in a long time — often causes performance issues
- **systeminfo** gives complete snapshot in one command — faster than opening multiple GUI tools
- **Always identify** graphics adapter and driver version when troubleshooting display issues
- **SODIMM form factor** confirmed — laptop RAM, important when ordering parts

## Screenshots
See screenshots folder for documented evidence of each task.
