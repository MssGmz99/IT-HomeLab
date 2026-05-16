# Lab 09 — Backup & Restore

## Overview
Explored Windows backup and restore tools to understand how to protect user data, recover lost files, and roll back system changes. Knowing the tools and their limitations is what separates a prepared T1 tech from everyone else — if no backup exists there is nothing to restore.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Device:** Dell Inspiron 14 7420 2-in-1
- **Tools Used:** Windows Backup, File History, Backup and Restore, System Restore

## How to Open Key Tools
- Windows Backup: Settings → Accounts → Windows Backup
- File History: Windows Key + R → control /name Microsoft.FileHistory
- Backup and Restore: Windows Key + R → control /name Microsoft.BackupAndRestore
- System Restore: Windows Key + R → sysdm.cpl → System Protection tab

## Windows Backup Tools Comparison

| Tool | What It Backs Up | Limitation |
|---|---|---|
| File History | Documents, Desktop, Pictures | Requires external drive |
| System Image | Entire drive including Windows | Large storage requirement |
| System Restore | System files and registry | Stored on C: drive — won't survive drive failure |
| OneDrive | Synced folders to cloud | Requires internet and Microsoft account |
| Backup and Restore | Selected files on a schedule | Legacy tool — still works on Windows 11 |

## File Recovery Order

1. Check Recycle Bin first — quickest and easiest
2. Check Previous Versions in file Properties — only works if File History was active
3. Check OneDrive or cloud backup if syncing was enabled
4. Check IT backup server if on a company network

## Tasks Performed

### Task 1 — Windows Backup Settings
- Opened Windows Backup via Settings → Accounts → Windows Backup
- Reviewed current backup status
- Confirmed App list and Preferences backed up to Microsoft account
- Identified OneDrive folder syncing status
- Noted last backup date and time

### Task 2 — File History
- Opened File History via Control Panel
- Confirmed File History status
- Identified external drive requirement
- Learned File History cannot back up to same drive Windows runs on
- Reviewed folders protected by File History — Libraries, Desktop, Contacts, Favorites

### Task 3 — Previous Versions
- Opened file Properties in Documents folder
- Clicked Previous Versions tab
- Reviewed available file versions
- Learned previous versions only exist if File History or restore points were active
- Demonstrated what a user sees when no backup was configured

### Task 4 — Backup and Restore Tool
- Opened Backup and Restore (Windows 7) via Control Panel
- Reviewed backup and restore options
- Identified System Image option for full drive backup
- Identified system repair disc creation option
- Confirmed no backup currently configured on machine

### Task 5 — Created System Restore Point
- Opened System Properties via sysdm.cpl
- Navigated to System Protection tab
- Clicked Create to make a new restore point
- Named restore point: Lab-09-Restore-Point
- Clicked Create and waited for confirmation
- Received success confirmation message

### Task 6 — Verified Restore Point
- Clicked System Restore button in System Protection tab
- Clicked Next to view available restore points
- Confirmed Lab-09-Restore-Point appeared in the list with correct date and time
- Learned restore points are stored on C: drive and cannot survive drive failure

## Key Concepts
- **System Restore is not a backup solution** — stored on C: and cannot survive drive failure
- **Previous Versions only exist** if File History or restore points were actively running
- **Always create a restore point** before making any significant system changes
- **No backup means no recovery** — proactive setup is critical
- **File History requires external drive** — cannot back up to same drive Windows runs on
- **Disable before delete** mentality applies to backups too — always verify before removing

## Screenshots
See screenshots folder for documented evidence of each task.
