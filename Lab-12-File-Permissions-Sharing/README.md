# Lab 12 — File Permissions & Sharing

## Overview
Practiced viewing, modifying, and removing file and folder permissions on a Windows machine. File permissions are at the core of every access-related helpdesk ticket — understanding Allow vs Deny and how to share folders on a network are essential T1 skills.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** File Explorer, Security Tab, Command Prompt

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

### Viewing Permissions
- Created a practice folder called PermissionsLab on the Desktop
- Right clicked folder and opened Properties → Security tab
- Identified three default entries: SYSTEM, current user, Administrators
- Read permission levels assigned to each entry
- Confirmed current user had Full Control as folder owner

### Adding a User with Permissions
- Created TestUser account via net user command
- Opened Security tab and clicked Edit → Add
- Added TestUser to the permissions list
- Set TestUser permissions to Read only
- Applied least privilege principle

### Deny Permissions
- Applied Deny on Read permission to TestUser
- Observed Windows warning that Deny overrides Allow
- Confirmed Deny takes priority over all Allow permissions including group membership
- Learned to use Deny sparingly — removal is preferred over Deny

### Removing Permissions
- Removed TestUser from permissions list entirely
- Learned removal is cleaner and preferred over explicit Deny
- Confirmed user no longer appeared in permissions list

### Network Folder Sharing
- Opened Properties → Sharing tab on folder
- Clicked Share and added TestUser with Read permission
- Noted network path format: \\ComputerName\SharedFolder
- Practiced removing a user from a share
- Practiced removing the entire share via Advanced Sharing

## Key Concepts
- Deny always overrides Allow — even Full Control through a group membership
- Remove vs Deny — removing is cleaner and preferred over using Deny
- Least Privilege — users should only have the access level they need for their job
- Network path format: \\ComputerName\SharedFolder
- Users need a valid account on the machine to access shared folders over the network
- Advanced Sharing gives more granular control than the basic sharing wizard

## Troubleshooting Access Denied
- Check Security tab for Deny entries first — these override everything
- Verify user or group is listed with correct permission level
- Check Sharing tab to confirm folder is actually shared on the network
- Verify network path is correct and machine is reachable

## Screenshots
See screenshots folder for documented evidence of each task.
