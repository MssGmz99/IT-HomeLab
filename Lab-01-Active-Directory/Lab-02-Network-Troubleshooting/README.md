# Lab 02 — Network Connectivity Troubleshooting

## Overview
Performed a full network diagnostic workflow using built-in Windows command line tools to simulate real helpdesk troubleshooting scenarios.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Tools Used:** Command Prompt

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

## Troubleshooting Logic
- Ping the router first then the internet — isolates whether problem is local or upstream
- If 169.254.x.x appears as the IP, DHCP failed — perform a release and renew
- If ping to 8.8.8.8 works but websites don't load — DNS is the issue not connectivity
- If tracert shows * * * at a specific hop — traffic is dropping at that point

## Scenarios Practiced
- Diagnosed a machine with no internet connectivity
- Identified DHCP failure via 169.254.x.x IP address
- Used tracert to identify where traffic was dropping
- Used nslookup to confirm DNS resolution was working
- Flushed DNS cache to resolve stale record issues
- Performed IP release and renew to resolve IP conflict

## Key Concepts
- DHCP automatically assigns IP addresses to devices on the network
- DNS translates domain names like google.com into IP addresses
- Default Gateway is the router — the exit point to the internet
- DNS cache stores recently visited domain records locally

## Screenshots
See screenshots folder for command outputs and results.
