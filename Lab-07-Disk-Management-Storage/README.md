# Lab 07 — Disk Management & Storage Troubleshooting

## Overview
Used Windows disk management tools to check drive health, view partition layout, free up disk space, and run storage diagnostics from both the GUI and command line.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Disk Management, File Explorer, Disk Cleanup, PowerShell

## How to Open Key Tools
(Disk Management: Windows Key + R → diskmgmt.msc) OR 
(Disk Cleanup: Windows Key + R → cleanmgr) OR 
(PowerShell: Start Menu → Windows PowerShell)

## PowerShell Commands Used

```powershell
# Check drive health
Get-PhysicalDisk | Select-Object FriendlyName, HealthStatus, OperationalStatus

# Check disk space in human readable format
Get-PSDrive C | Select-Object Name, @{Name="Used(GB)";Expression={[math]::Round($_.Used/1GB,2)}}, @{Name="Free(GB)";Expression={[math]::Round($_.Free/1GB,2)}}
```

## Tasks Performed

### Disk Management GUI
- Opened Disk Management and read full partition layout
- Identified EFI System Partition — how Windows boots
- Identified OS C: drive at 405GB
- Identified unallocated space at 53GB
- Identified multiple Recovery Partitions
- Confirmed all partitions showing Healthy status

### Disk Space Check
- Checked C: drive space via File Explorer — This PC
- Confirmed 128GB free of 405GB total
- Identified healthy blue bar indicating no storage concerns
- Learned that red bar indicates critically low space under 10%

### Disk Cleanup
- Ran Disk Cleanup via cleanmgr
- Reviewed categories available for cleanup
- Safely removed temporary files, cached data, and old update files
- Confirmed Disk Cleanup never touches personal files

### Drive Health Check
- Attempted wmic diskdrive get status — discovered wmic deprecated on Windows 11
- Pivoted to PowerShell using Get-PhysicalDisk
- Confirmed drive: NVMe KBG50ZNS512G KIOXIA 512GB
- Confirmed Health Status: Healthy
- Confirmed Operational Status: OK

### Command Line Disk Space
- Used Get-PSDrive in PowerShell to check disk space
- Converted raw bytes to human readable GB format
- Confirmed 261.76GB used and 144.16GB free

## Key Concepts
- Blue bar in File Explorer = healthy space. Red bar = critically low under 10%
- Drive health statuses: Healthy, Warning (back up immediately), Unhealthy (replace urgently)
- EFI partition is how Windows boots — never delete it
- Recovery partitions contain manufacturer recovery tools — leave alone
- Unallocated space can be extended into an existing partition
- wmic is deprecated on Windows 11 — use PowerShell instead
- Disk Cleanup is safe — it never touches personal files

## Screenshots
See screenshots folder for documented evidence of each task.
