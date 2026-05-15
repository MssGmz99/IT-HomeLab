# Lab 02 — Network Connectivity Troubleshooting

## Overview
Performed a full network diagnostic workflow using built-in Windows command line tools to simulate real helpdesk troubleshooting scenarios. These are the exact commands a T1 tech runs when a user reports they cannot connect to the internet.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Command Prompt

## How to Open
Start Menu → type CMD → Run as Administrator

## Commands Used

| Command | Purpose | What to Look For |
|---|---|---|
| ipconfig | Check IP address, subnet mask, gateway | 169.254.x.x = DHCP failed |
| ping 192.168.1.1 | Test router connectivity | 4/4 replies = local network OK |
| ping 8.8.8.8 | Test internet connectivity | 4/4 replies = internet OK |
| tracert 8.8.8.8 | Trace path traffic takes | * * * = packet dropped at that hop |
| nslookup google.com | Check DNS resolution | No IP returned = DNS issue |
| ipconfig /release | Drop current IP address | Temporarily loses connectivity |
| ipconfig /renew | Request fresh IP from router | Gets new IP from DHCP server |
| ipconfig /flushdns | Clear cached DNS records | Forces fresh DNS lookup |

## Tasks Performed

### Task 1 — ipconfig
- Ran ipconfig to check network configuration
- Confirmed IPv4 address in 192.168.1.x range — valid DHCP assigned address
- Confirmed Subnet Mask: 255.255.255.0
- Confirmed Default Gateway: 192.168.1.1 — home router
- Verified machine has valid network configuration

### Task 2 — Ping Router
- Ran ping 192.168.1.1 to test local network connectivity
- Confirmed 4/4 replies with 0% packet loss
- Confirmed response times under 5ms — healthy local connection
- Verified machine can communicate with router

### Task 3 — Ping Internet
- Ran ping 8.8.8.8 to test internet connectivity
- Confirmed 4/4 replies with 0% packet loss
- Confirmed internet connectivity is working
- Verified traffic is routing correctly beyond the local network

### Task 4 — Tracert
- Ran tracert 8.8.8.8 to trace full network path
- Identified Hop 1 as home router at 192.168.1.1
- Identified ISP hops in the middle of the trace
- Confirmed traffic reached destination at 8.8.8.8
- No * * * timeouts observed — clean path end to end

### Task 5 — nslookup
- Ran nslookup google.com to verify DNS resolution
- Confirmed DNS server responded with valid IP address for google.com
- Verified DNS is functioning correctly
- Learned that if ping to 8.8.8.8 works but nslookup fails — DNS is the issue

### Task 6 — Flush DNS
- Ran ipconfig /flushdns
- Confirmed message: Successfully flushed the DNS Resolver Cache
- Cleared locally cached DNS records to force fresh lookups
- Simulated fix for user who can reach some sites but not others

## Troubleshooting Logic
- Ping router first then internet — isolates whether problem is local or upstream
- If 169.254.x.x appears as IP — DHCP failed, perform release and renew
- If ping to 8.8.8.8 works but websites don't load — DNS is the issue not connectivity
- If tracert shows * * * at a specific hop — traffic is dropping at that point
- If nslookup fails but ping works — flush DNS or point user to alternate DNS server

## Key Concepts
- **Private IP (192.168.x.x)** — internal network address, not routable on the internet
- **Public IP** — assigned by ISP, what websites see — NOT shown in ipconfig
- **DHCP** — automatically assigns IP addresses to devices on the network
- **DNS** — translates domain names like google.com into IP addresses
- **Default Gateway** — your router, the exit point to the internet
- **DNS cache** — stores recently visited domain records locally

## Screenshots
See screenshots folder for documented evidence of each task.
