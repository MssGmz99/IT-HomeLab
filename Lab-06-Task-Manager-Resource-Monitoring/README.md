# Lab 06 — Task Manager & Resource Monitoring

## Overview
Used Windows Task Manager to diagnose and resolve performance issues on a live Windows 11 machine. Task Manager is the first tool a T1 tech opens when a user reports their computer is slow or a program is frozen.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Device:** Dell Inspiron 14 7420 2-in-1
- **Tools Used:** Task Manager (Ctrl + Shift + Esc)

## How to Open
- Ctrl + Shift + Esc — fastest method
- Ctrl + Alt + Delete → Task Manager
- Right click Taskbar → Task Manager

## Key Tabs

| Tab | What It Shows | When to Use |
|---|---|---|
| Processes | All running apps and resource usage | Diagnosing slow or frozen computer |
| Performance | Real-time graphs of CPU, RAM, Disk, Network | Monitoring resource trends over time |
| Startup Apps | Programs that launch at boot | Fixing slow boot times |

## Tasks Performed

### Task 1 — Processes Tab — Sort by Memory
- Opened Task Manager and navigated to Processes tab
- Clicked Memory column to sort highest to lowest
- Identified top memory consumers on the machine
- Claude browser tabs identified as top memory consumer
- Antimalware Service Executable identified as normal background process
- OVRServer (Oculus VR) identified running unnecessarily in background

### Task 2 — Processes Tab — Sort by CPU
- Clicked CPU column to sort by processor usage
- Identified which processes were consuming the most CPU
- Confirmed overall CPU usage was healthy
- Noted that most background processes were at 0% CPU

### Task 3 — Performance Tab — Memory
- Navigated to Performance tab via graph icon in left sidebar
- Clicked Memory to view RAM usage graph
- Read key memory statistics:
  - Total RAM: 8.0 GB
  - In use: 5.8 GB (77%)
  - Available: 1.8 GB
  - Slots used: 2 of 2 — no room to add more RAM
  - Form factor: SODIMM — laptop RAM
- Identified machine running memory constrained at 77% usage

### Task 4 — Startup Apps Review
- Navigated to Startup Apps tab via list icon in left sidebar
- Reviewed all enabled and disabled startup items
- Identified unnecessary programs launching at boot
- Noted Last BIOS time for boot performance reference

### Task 5 — Disabled a Startup Item
- Selected non-essential startup application
- Clicked Disable to prevent it from launching at boot
- Confirmed status changed to Disabled
- Simulated fixing a slow boot time complaint

## Key Concepts
- Sort by Memory or CPU to quickly find resource consumers
- Memory consistently above 85-90% means machine needs more RAM or fewer background apps
- 8GB RAM with both slots filled means sticks must be replaced — no room to add more
- SODIMM is the laptop RAM form factor — important when ordering replacement parts
- Some processes restart automatically when ended — managed by a parent service
- Disabling unnecessary startup items improves boot time and frees RAM on launch
- Last BIOS time shows how long before Windows starts loading

## Screenshots
See screenshots folder for documented evidence of each task.
