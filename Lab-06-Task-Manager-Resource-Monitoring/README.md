# Lab 06 — Task Manager & Resource Monitoring

## Overview
Used Windows Task Manager to diagnose and resolve performance issues on a live machine. Task Manager is the first tool a T1 tech opens when a user reports their computer is slow or a program is frozen.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Task Manager (Ctrl + Shift + Esc)

## How to Open
Ctrl + Shift + Esc OR 
Ctrl + Alt + Delete → Task Manager OR 
Right click Taskbar → Task Manager

## Key Tabs

| Tab | What It Shows | When to Use |
|---|---|---|
| Processes | All running apps and resource usage | Diagnosing slow or frozen computer |
| Performance | Real-time graphs of CPU, RAM, Disk, Network | Monitoring resource trends over time |
| Startup Apps | Programs that launch at boot | Fixing slow boot times |

## Tasks Performed

### Process Analysis
- Opened Task Manager and navigated to Processes tab
- Sorted processes by Memory and CPU to identify top resource consumers
- Identified Claude browser tabs consuming 385MB as top memory user
- Identified Antimalware Service Executable at 138MB as normal background process
- Identified OVRServer (Oculus VR) running unnecessarily in background

### Process Management
- Attempted to end OVRServer process
- Observed process automatically restarted — demonstrating parent service management
- Learned that some processes require stopping the underlying service not just ending the process

### Performance Monitoring
- Navigated to Performance tab and read Memory graph
- Identified machine running at 77% memory usage — 5.8GB of 8GB in use
- Noted only 1.8GB available — machine running memory constrained
- Identified RAM slots used: 2 of 2 — no room to add more RAM
- Identified form factor: SODIMM — laptop RAM, important for ordering parts

### Startup Management
- Navigated to Startup Apps tab
- Reviewed all enabled startup items
- Disabled ChatGPT from launching at startup
- Reduced unnecessary startup load to improve boot time

## Key Concepts
- Sort by Memory or CPU to quickly find resource consumers
- Memory consistently above 85-90% means the machine needs more RAM or fewer background apps
- 8GB RAM with both slots filled means sticks must be replaced — no room to add more
- SODIMM is the laptop RAM form factor — important when ordering replacement parts
- Some processes restart automatically — managed by a parent service, fix the root cause
- Disabling unnecessary startup items improves boot time and frees RAM on launch
- Last BIOS time shows how long before Windows starts loading

## Screenshots
See screenshots folder for documented evidence of each task.
