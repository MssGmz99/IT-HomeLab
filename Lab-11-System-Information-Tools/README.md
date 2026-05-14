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

### msinfo32 — System Information
- Opened msinfo32 and read full system summary
- Identified OS: Windows 11 Home
- Identified Model: Dell Inspiron 14 7420 2-in-1
- Identified Processor: 12th Gen Intel Core i5-1235U
- Identified RAM: 8GB
- Identified BIOS Mode: UEFI
- Identified Secure Boot: Enabled

### msinfo32 — Display Components
- Expanded Components and clicked Display
- Identified two display adapters:
  - Meta Virtual Monitor — Oculus VR virtual display
  - Intel Iris Xe Graphics — real graphics adapter with 2GB VRAM at 1920x1200

### msinfo32 — Problem Devices
- Clicked Problem Devices under Components
- Found two Dell Data Vault Control Device entries with Error Code 48
- Identified Error Code 48 as Windows blocking a driver from loading
- Determined Dell Data Vault is non-critical telemetry software — no action required

### dxdiag — DirectX Diagnostic Tool
- Opened dxdiag and reviewed System tab
- Confirmed DirectX 12 installed
- Confirmed processor, RAM, and BIOS version
- Checked Display tab — confirmed No problems found
- Checked Sound tabs 1 through 4 — confirmed No problems found on all
- Saved full dxdiag output to Desktop for documentation

### systeminfo — Command Line
- Ran systeminfo from Command Prompt
- Read last boot time — machine had not rebooted in 9 days
- Identified available RAM: 1,688MB — machine memory constrained
- Read installed hotfixes — 4 Windows updates applied
- Read network adapter details including DHCP server and IP address

## Key Concepts
- Error Code 48 means Windows blocked a driver — investigate if it affects the user
- Save dxdiag output before escalating to T2 — attach it to the ticket
- Last boot time shows if a machine has not restarted in a long time — often causes performance issues
- systeminfo gives a complete snapshot in one command — faster than opening multiple GUI tools
- Always identify graphics adapter and driver version when troubleshooting display issues

## Screenshots
See screenshots folder for documented evidence of each task.
