# Lab 03 — User Account Management in Active Directory

## Overview
Practiced the full user account lifecycle inside a live Active Directory environment running on Windows Server 2012 R2. All tasks performed in Active Directory Users and Computers (ADUC) on domain lab.local — matching real-world enterprise helpdesk workflows.

## Environment
- **Platform:** Windows Server 2012 R2 VM (VirtualBox)
- **Domain:** lab.local
- **Tools Used:** Active Directory Users and Computers (ADUC)
- **Server:** Lab-DC01

## How to Open
Server Manager → Tools → Active Directory Users and Computers

## AD Structure Used

| OU | Purpose |
|---|---|
| IT | Information Technology staff |
| HR | Human Resources staff |
| Production | Production floor staff |
| Primary Executives | Senior leadership |
| Special Projects | Project-based staff |
| Users | General domain users |

## Tasks Performed

### Task 1 — Create a New User Account
- Selected IT OU in ADUC
- Created new user: James Carter (jcarter)
- Set initial password with User must change password at next logon enabled
- Simulated onboarding a new IT department employee

### Task 2 — Disable a User Account
- Right clicked jcarter and selected Disable Account
- Confirmed account showed disabled icon (down arrow on user icon)
- Simulated terminating access for an employee on leave or terminated

### Task 3 — Re-enable a User Account
- Right clicked jcarter and selected Enable Account
- Confirmed disabled icon disappeared
- Simulated restoring access after leave or administrative error

### Task 4 — Reset a User Password
- Right clicked jcarter and selected Reset Password
- Set new password with User must change password at next logon checked
- Received confirmation — password reset successfully
- Simulated most common T1 helpdesk ticket

### Task 5 — Unlock a User Account
- Opened jcarter Properties → Account tab
- Located Unlock account checkbox
- Identified where account unlocks are performed in AD
- Simulated resolving an account lockout after failed login attempts

### Task 6 — Move a User Between OUs
- Moved jcarter from IT OU to HR OU
- Confirmed jcarter appeared in HR OU
- Moved jcarter back to IT OU
- Simulated an employee changing departments

### Task 7 — Add and Remove User from Security Group
- Right clicked jcarter and selected Add to a group
- Added jcarter to IT-Admins security group
- Confirmed via group Members tab that jcarter was listed
- Removed jcarter from IT-Admins group
- Simulated granting and revoking elevated permissions

### Task 8 — Delete a User Account
- Right clicked jcarter and selected Delete
- Confirmed deletion via dialog prompt
- Verified jcarter no longer appeared in IT OU
- Simulated final step of employee offboarding

## Key Concepts
- **Disable Before Delete** — always disable first, wait for manager confirmation, then delete
- **Identity Verification** — always verify user identity before resetting any password
- **Force Password Change** — always check User must change password at next logon after every reset
- **Least Privilege** — add users to groups only when access is needed, remove when no longer required
- **Move vs Delete** — when an employee changes departments move their account, never delete and recreate
- **Account Lockouts** — check Account tab in user Properties to unlock — also check Event Viewer for Event ID 4625 to investigate cause

## Screenshots
See screenshots folder for documented evidence of each task.
