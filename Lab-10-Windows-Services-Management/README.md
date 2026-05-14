## Startup Types

| Startup Type | Meaning |
|---|---|
| Automatic | Starts every time Windows boots |
| Automatic (Delayed) | Starts shortly after boot to reduce load |
| Manual | Only starts when something needs it |
| Manual (Triggered) | Starts when a specific system event occurs |
| Disabled | Will not start under any circumstances |

## Key CMD Commands

| Command | Purpose |
|---|---|
| sc query spooler | Check the status of a specific service |
| net stop spooler | Stop a service |
| net start spooler | Start a service |
| sc queryex type= service state= all | List all services and their states |

## Tasks Performed

### Services Manager Navigation
- Opened Services Manager through Computer Management
- Read service names, status, startup types, and log on accounts
- Identified services as Running or Stopped
- Navigated the full services list

### Print Spooler Management
- Located Print Spooler in the services list
- Restarted Print Spooler through the GUI right click menu
- Opened Print Spooler Properties and reviewed all tabs

### Recovery Tab
- Reviewed Recovery tab on Print Spooler
- Identified First failure set to Restart the Service
- Identified Second failure set to Restart the Service
- Identified Subsequent failures set to Take No Action
- Learned this explains why some services keep restarting after being stopped

### Dependencies Tab
- Reviewed Dependencies tab on Print Spooler
- Identified Print Spooler depends on HTTP Service and Remote Procedure Call (RPC)
- Identified Fax service depends on Print Spooler
- Learned that if a dependency is not running the service will not start

### Startup Type Management
- Located Fax service in the services list
- Changed startup type from Manual to Disabled
- Changed startup type back to Manual
- Practiced startup type modification workflow

### Command Line Service Management
- Used sc query spooler to check Print Spooler status
- Confirmed STATE: 4 RUNNING
- Used sc queryex type= service state= all to list all running services

## Key Concepts
- Recovery Tab controls what happens when a service crashes — explains auto restart behavior
- Dependencies Tab shows what a service needs to run — check this if a service won't start
- Stopping vs Disabling — stopping is temporary, disabling prevents the service from running at all
- Some processes restart automatically — managed by a parent service, fix the root cause
- net stop and net start are faster than the GUI for quick service management

## Screenshots
See screenshots folder for documented evidence of each task.
