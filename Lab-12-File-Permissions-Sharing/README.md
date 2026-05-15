# Lab 12 — File Permissions & Sharing on Active Directory

## Overview
Practiced setting, modifying, and removing file and folder permissions on a Windows Server 2012 R2 Domain Controller using domain user accounts. All permissions were applied to Active Directory users — more realistic than local account permissions on a workstation.

## Environment
- **Platform:** Windows Server 2012 R2 VM (VirtualBox)
- **Domain:** lab.local
- **Server:** Lab-DC01
- **Tools Used:** File Explorer, Security Tab, Advanced Sharing

## Permission Levels

| Permission | What It Allows |
|---|---|
| Full Control | Read, write, modify, delete, and change permissions |
| Modify | Read, write, edit, and delete files |
| Read & Execute | Open and run files but not modify them |
| Read | View files only — cannot make changes |
| Write | Create and edit files but cannot delete |
| Deny | Blocks access regardless of any Allow permissions |

## Tasks Performed

### Task 1 — Created Shared Folder
- Navigated to C:\ on Domain Controller
- Created new folder named DeptShare
- Simulated creating a department shared folder on a file server

### Task 2 — Set NTFS Permissions
- Opened DeptShare Properties → Security tab
- Reviewed default permissions — SYSTEM, Administrators, Users
- Clicked Edit → Add
- Added domain user LAB\jsmith
- Set jsmith permissions to Read only
- Applied least privilege principle — read access only for standard user

### Task 3 — Shared Folder on Network
- Opened DeptShare Properties → Sharing tab
- Clicked Advanced Sharing
- Enabled Share this folder
- Named share: DeptShare
- Added LAB\jsmith to Share permissions with Read access
- Confirmed network path: \\LAB-DC01\DeptShare
- Simulated setting up a network share accessible to domain users

### Task 4 — Modified User Permissions
- Opened Security tab and selected jsmith
- Changed permissions from Read to Modify
- Applied changes
- Simulated a user promotion requiring elevated folder access

### Task 5 — Applied Deny Permission
- Opened Security tab and selected jsmith
- Checked Deny on Read permission
- Confirmed Windows warning that Deny overrides Allow
- Confirmed Deny takes priority over all Allow permissions
- Simulated blocking a specific user from accessing sensitive data

### Task 6 — Removed User Permissions
- Opened Security tab and selected jsmith
- Clicked Remove to remove jsmith entirely from permissions list
- Confirmed jsmith no longer appeared in permissions list
- Learned removal is cleaner and preferred over explicit Deny
- Simulated revoking access during employee offboarding

### Task 7 — Removed Network Share
- Opened Sharing tab → Advanced Sharing
- Unchecked Share this folder
- Confirmed folder no longer shared on network
- Simulated taking down a share that is no longer needed

## Key Concepts
- **Deny always overrides Allow** — even Full Control through group membership
- **Remove vs Deny** — removing is cleaner and preferred over explicit Deny
- **Least Privilege** — users should only have the access level they need
- **NTFS vs Share Permissions** — both must be configured correctly for network access
- **Network path format:** \\ServerName\ShareName
- **Domain users** can be added directly to folder permissions — more manageable than local accounts
- **Always confirm with manager** before removing access during offboarding

## Troubleshooting Access Denied
- Check Security tab for Deny entries first — these override everything
- Verify user or their group is listed with correct permission level
- Check Sharing tab to confirm folder is actually shared on the network
- Verify network path is correct and server is reachable
- Check both NTFS and Share permissions — both must allow access

## Interview Answer
When asked about file permissions and access denied tickets:

"I check the Security tab on the folder first and look for any explicit Deny entries since those override everything including group membership. Then I verify the user or their group has the correct permission level assigned. I also check the Sharing tab to confirm the folder is actually shared and the network path is correct. I follow least privilege — users only get the access level they need for their job, and I remove permissions entirely during offboarding rather than using Deny."

## Screenshots
See screenshots folder for documented evidence of each task.
