# Lab 07 — Disk Management & Storage Troubleshooting

## Overview
Used Windows disk management tools to check drive health, view partition layout, free up disk space, and run storage diagnostics from both the GUI and PowerShell command line. These are the exact tools a T1 tech uses when a user reports their disk is full or a drive is showing errors.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Device:** Dell Inspiron 14 7420 2-in-1
- **Tools Used:** Disk Management, File Explorer, Disk Cleanup, PowerShell

## How to Open Key Tools
- Disk Management: Windows Key + R → diskmgmt.msc
- Disk Cleanup: Windows Key + R → cleanmgr
- PowerShell: Start Menu → Windows PowerShell (Run as Administrator)

## PowerShell Commands Used

```powershell
# Check drive health
Get-PhysicalDisk | Select-Object FriendlyName, HealthStatus, OperationalStatus

# Check disk space in human readable GB format
Get-PSDrive C | Select-Object Name, @{Name="Used(GB)";Expression={[math]::Round($_.Used/1GB,2)}}, @{Name="Free(GB)";Expression={[math]::Round($_.Free/1GB,2)}}
```

## Tasks Performed

### Task 1 — Disk Management GUI
- Opened Disk Management via diskmgmt.msc
- Read full partition layout of 476GB SSD
- Identified EFI System Partition — how Windows boots, never delete
- Identified OS C: drive at 405GB — main Windows partition
- Identified unallocated space at 53GB — unused, could be extended
- Identified multiple Recovery Partitions — manufacturer recovery tools
- Confirmed all partitions showing Healthy status
- Noted single physical disk — Disk 0

### Task 2 — File Explorer Disk Space Check
- Opened File Explorer and navigated to This PC
- Checked C: drive space bar color — blue indicates healthy space
- Confirmed drive had sufficient free space
- Learned red bar indicates critically low space under 10%

### Task 3 — Disk Cleanup
- Ran Disk Cleanup via cleanmgr
- Reviewed available cleanup categories including:
  - Temporary Internet Files
  - Recycle Bin
  - Temporary Files
  - Windows Update Cleanup
- Confirmed Disk Cleanup never touches personal files
- Safely removed unnecessary files to free up space

### Task 4 — Drive Health Check via PowerShell
- Opened PowerShell as Administrator
- Ran Get-PhysicalDisk command
- Confirmed drive: NVMe KBG50ZNS512G KIOXIA 512GB
- Confirmed Health Status: Healthy
- Confirmed Operational Status: OK
- Learned wmic is deprecated on Windows 11 — PowerShell is the modern replacement

### Task 5 — Disk Space via PowerShell
- Ran Get-PSDrive with GB conversion formula
- Confirmed used and free space in human readable format
- Verified results matched what File Explorer showed
- Demonstrated command line alternative to GUI disk space check

## Key Concepts
- **Blue bar** in File Explorer = healthy space
- **Red bar** = critically low space — under 10% free
- **Drive health statuses:** Healthy, Warning (back up immediately), Unhealthy (replace urgently)
- **EFI partition** is how Windows boots — never delete it
- **Recovery partitions** contain manufacturer recovery tools — leave alone
- **Unallocated space** can be extended into an existing partition if needed
- **wmic is deprecated** on Windows 11 — use PowerShell instead
- **Disk Cleanup** is safe — it never touches personal files

## Screenshots
See screenshots folder for documented evidence of each task.
