## Windows Backup Tools

| Tool | What It Backs Up | Limitation |
|---|---|---|
| File History | Documents, Desktop, Pictures | Requires external drive |
| System Image | Entire drive including Windows | Large storage requirement |
| System Restore | System files and registry | Stored on C: drive — won't survive drive failure |
| OneDrive | Synced folders to cloud | Requires internet and Microsoft account |
| Backup and Restore | Selected files on a schedule | Legacy tool — still works on Windows 11 |

## File Recovery Order

1. Check the Recycle Bin first — quickest and easiest
2. Check Previous Versions in file Properties — only works if File History was active
3. Check OneDrive or cloud backup if syncing was enabled
4. Check IT backup server if on a company network

## Tasks Performed

### Windows Backup Settings
- Opened Windows Backup page and reviewed current backup status
- Confirmed App list and Preferences were backed up to Microsoft account
- Identified OneDrive folder syncing was not configured

### File History
- Opened File History via Control Panel
- Identified no external drive available — File History requires separate drive
- Learned File History cannot back up to the same drive Windows runs on

### Previous Versions
- Checked Previous Versions on a real file edited over a month ago
- Found no previous versions available — File History was not enabled
- Learned firsthand that previous versions only exist if something was actively capturing them

### Backup and Restore Tool
- Opened Backup and Restore (Windows 7) tool
- Reviewed System Image and system repair disc options
- Identified no backup currently configured

### System Restore
- Opened System Properties via sysdm.cpl
- Navigated to System Protection tab
- Created a System Restore point named Lab Practice Restore Point
- Verified restore point appeared in the restore point list
- Learned System Restore is stored on C: drive and cannot survive drive failure

## Key Concepts
- System Restore is not a backup solution — stored on C: and cannot survive drive failure
- Previous Versions only exist if File History or restore points were actively running
- Always create a System Restore point before making any significant system changes
- No backup means no recovery — proactive setup is critical
- File History requires an external drive — cannot back up to the same drive Windows runs on

## Screenshots
See screenshots folder for documented evidence of each task.
