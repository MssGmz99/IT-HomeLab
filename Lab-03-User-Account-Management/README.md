# Lab 03 — User Account Management

## Overview
Practiced the full user account lifecycle using both the Windows Settings GUI and Command Prompt. Skills directly transfer to Active Directory Users and Computers in a domain environment.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Settings GUI, Command Prompt (Administrator)

## Commands Used

| Command | Purpose |
|---|---|
| net user JDoe Password123! /add | Create a new user account |
| net user JDoe /active:no | Disable a user account |
| net user JDoe /active:yes | Re-enable a user account |
| net user JDoe NewPassword123! | Reset a user password |

## Tasks Performed

### Account Creation
- Created local user accounts via Settings GUI
- Created local user accounts via net user /add command
- Simulated onboarding a new employee

### Account Management
- Disabled user accounts to simulate employee termination or leave
- Re-enabled accounts to simulate return from leave or access restoration
- Reset user passwords using Command Prompt
- Changed account types between Standard User and Administrator
- Applied least privilege principle — users only get access they need

### Account Offboarding
- Deleted user accounts to simulate employee offboarding
- Discussed disable before delete best practice to preserve user data

## Key Concepts
- **Least Privilege:** Users only get the access level they need — nothing more
- **Disable Before Delete:** Preserve data and settings before permanently removing an account
- **Identity Verification:** Always verify user identity before resetting any password
- **Force Password Change:** Require users to change password on next logon after every reset
- **Active Directory:** These same tasks are performed through AD Users and Computers on a domain

## Screenshots
See screenshots folder for documented evidence of each task.
