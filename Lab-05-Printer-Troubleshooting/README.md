# Lab 05 — Printer Troubleshooting

## Overview
Practiced the full printer troubleshooting workflow including adding printers manually, managing the print queue, restarting the Print Spooler service, and resolving offline printer issues. Printer troubleshooting is one of the most frequent T1 helpdesk tickets.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Settings, Control Panel, Command Prompt (Administrator), Services.msc

## How to Open Printer Settings
Settings → Bluetooth & devices → Printers & scanners

## Print Spooler Commands

```cmd
# Stop the Print Spooler
net stop spooler

# Clear stuck print jobs
del /Q /F /S "%systemroot%\System32\spool\PRINTERS\*.*"

# Start the Print Spooler
net start spooler
```

## Full Troubleshooting Checklist

| Step | Action | What It Fixes |
|---|---|---|
| 1 | Check Use Printer Offline setting | Printer appears offline accidentally |
| 2 | Restart Print Spooler only | Stuck service without losing jobs |
| 3 | Clear spool folder and restart | Corrupted or stuck print jobs |
| 4 | Remove and reinstall printer | Driver corruption |
| 5 | Check physical or network connection | Cable or network issue |

## Tasks Performed

### Adding a Printer
- Navigated to Printers and Scanners settings
- Added a printer manually using the Add Printer wizard
- Selected port and driver during manual installation
- Set printer as default and disabled automatic default management

### Print Spooler Management
- Stopped Print Spooler using net stop spooler
- Cleared the spool folder to remove stuck jobs
- Restarted Print Spooler using net start spooler
- Practiced GUI method via services.msc as alternative

### Printer Reinstallation
- Removed existing printer driver
- Reinstalled printer with fresh driver
- Simulated full printer reset for driver corruption scenario

### Offline Printer Fix
- Opened classic print queue via Control Panel
- Located Use Printer Offline setting in Printer menu
- Verified setting was disabled to restore online status

## Key Concepts
- **Print Spooler** is the Windows service that manages all print jobs
- Clearing the spool folder permanently deletes queued jobs — always warn the user first
- Restart spooler only first if jobs are important — clear folder only as last resort
- Use Printer Offline is a common accidental setting — always check it first
- Know both CMD and GUI methods — CMD is faster, GUI is better when walking a user through it

## Screenshots
See screenshots folder for documented evidence of each task.
