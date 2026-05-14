# Lab 08 — Ticketing System Simulation

## Overview
Practiced writing and resolving helpdesk tickets for real-world T1 scenarios. Good ticketing documentation is just as important as technical ability — it shows how a technician thinks, communicates, and protects themselves and their team.

## Environment
- **Platform:** Written Documentation
- **Tools Used:** Ticket writing practice — no software required

## Anatomy of a Great Ticket

| Field | What It Should Contain |
|---|---|
| Title | Short specific summary of the issue |
| User | Full name and department |
| Priority | Low / Medium / High / Critical — pick one |
| Description | Full story of what the user reported in their words |
| Steps Taken | Every step with specific tool names and numbers |
| Resolution | What caused it and exactly what fixed it |
| Status | Open / In Progress / Resolved |
| Notes | Follow-up actions or escalation flags |

## Priority Guide

| Priority | When to Use |
|---|---|
| Low | Minor inconvenience — user can still work fully |
| Medium | Impacting work but user can still function |
| High | User is completely down or time-sensitive |
| Critical | Multiple users down or active security incident |

## Tickets Completed

### Ticket 1 — Printer Showing Offline
- **User:** Sarah Johnson, Accounting Department
- **Priority:** Medium
- **Issue:** Printer showing offline despite being powered on
- **Resolution:** Use Printer Offline was accidentally enabled — unchecked to restore online status
- **Key Learning:** Always check Use Printer Offline before escalating printer issues

### Ticket 2 — Slow Workstation
- **User:** David Martinez, Sales Department
- **Priority:** Medium
- **Issue:** Workstation running slow all morning, slow to open applications
- **Resolution:** ChatGPT desktop app consuming 380MB at startup — disabled from startup programs, ended background process. Memory dropped from 87% to 61%
- **Key Learning:** Include specific process names and before/after metrics in tickets

### Ticket 3 — Account Lockout with Urgency
- **User:** Jennifer Wu, HR Department
- **Priority:** High
- **Issue:** User locked out of account with meeting in 20 minutes
- **Resolution:** Verified identity via security questions, unlocked account in Active Directory, reset password with force change on next logon
- **Key Learning:** Always verify identity before any account action — especially in sensitive departments like HR. Communicate ETA immediately when ticket is time-sensitive

## Key Rules
- Verify identity before any account action
- Communicate ETA immediately when a ticket is time-sensitive
- Be specific — name the process, the percentage, the error code
- Always confirm the fix with the user before closing the ticket
- Document everything — if it is not in the ticket it did not happen
- Leave notes about anything that may need follow up

## Key Concepts
- Specific over vague — name the process, the number, the tool used
- Close the loop — always confirm fix with user before closing
- Protect yourself — detailed tickets protect you if an issue recurs
- Think ahead — notes about potential follow up show maturity

## Screenshots
See screenshots folder for sample tickets and documentation.
