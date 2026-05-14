# Lab 04 — Windows Event Viewer

## Overview
Navigated and interpreted Windows Event Viewer logs to diagnose system issues, identify security events, and create custom monitoring views. Event Viewer is one of the most powerful diagnostic tools available to a T1 helpdesk technician.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Event Viewer (eventvwr.msc)

## How to Open
Windows Key + R → eventvwr.msc

## Key Logs

| Log | What It Contains | When to Use |
|---|---|---|
| System | Hardware, driver, and service events | Crashes, driver failures, shutdowns |
| Application | Software errors and crashes | App-specific issues |
| Security | Login attempts, account changes | Failed logins, account activity |

## Critical Event IDs

| Event ID | Meaning | Action |
|---|---|---|
| 4624 | Successful logon | Normal activity |
| 4625 | Failed logon attempt | Investigate if spike in short window |
| 6006 | Clean system shutdown | Normal |
| 6008 | Unexpected/dirty shutdown | Investigate possible crash |
| 1074 | System restart initiated | Normal if scheduled |

## Tasks Performed

### System Log Analysis
- Navigated System log and identified Warning and Error events
- Read and interpreted Event ID 6062 from Netwtw14 Wi-Fi driver
- Identified Event ID 10016 from DistributedCOM as background noise
- Distinguished actionable errors from normal background warnings

### Security Log Analysis
- Filtered Security log for Event ID 4624 — found 328 successful logon events
- Filtered Security log for Event ID 4625 — identified failed logon attempts
- Analyzed timestamp patterns to determine if failed logins were suspicious

### Custom Views
- Created a Custom View filtered to System log Warnings and Errors
- Set time range to Last 24 hours
- Named view — System Errors Last 24hrs
- Saved view for repeated monitoring use

## Key Concepts
- Filter by Event ID to avoid scrolling through thousands of events
- A few scattered 4625 events are normal — a spike in a short window is a red flag
- Custom Views save time for repeated monitoring tasks
- Warnings are not always actionable — learn to distinguish noise from real problems

## Screenshots
See screenshots folder for documented evidence of each task.
