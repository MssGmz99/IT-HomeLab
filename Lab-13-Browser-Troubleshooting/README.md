# Lab 13 — Browser Troubleshooting

## Overview
Practiced the full browser troubleshooting workflow using Google Chrome on Windows 11. Browser issues are among the most frequent user complaints on any helpdesk. Knowing the right order to apply fixes makes a T1 tech fast and effective on the job.

## Environment
- **Platform:** Windows 11 Home (Host Machine)
- **Device:** Dell Inspiron 14 7420 2-in-1
- **Browser:** Google Chrome
- **Tools Used:** Chrome Settings, Chrome Extensions, Command Prompt

## How to Open Key Tools
- Clear Cache: Ctrl + Shift + Delete
- Extensions: chrome://extensions
- Update Check: chrome://settings/help
- Reset Chrome: chrome://settings/reset
- Incognito Mode: Ctrl + Shift + N

## Troubleshooting Order

| Step | Action | What It Rules Out |
|---|---|---|
| 1 | Clear cache and cookies | Outdated or corrupted browser data |
| 2 | Test in Incognito mode | Extension or cache issue |
| 3 | Try a different browser | Chrome-specific issue |
| 4 | Check if site is down (downforeveryoneorjustme.com) | Server-side issue |
| 5 | Flush DNS (ipconfig /flushdns) | Cached DNS record issue |
| 6 | Disable extensions one by one | Specific extension causing the problem |
| 7 | Reset Chrome settings | Corrupted Chrome configuration |

## Diagnostic Logic

| Result | What It Means |
|---|---|
| Works in Incognito, not regular Chrome | Extension or cached data is the culprit |
| Doesn't work in Incognito either | Not an extension — check DNS or network |
| Works in Edge but not Chrome | Chrome-specific issue — reset Chrome settings |
| Doesn't work in any browser | Network issue or site is down |

## Tasks Performed

### Task 1 — Clear Cache and Cookies
- Opened Clear browsing data via Ctrl + Shift + Delete
- Set time range to All time
- Selected Browsing history, Cookies and site data, Cached images and files
- Confirmed data cleared successfully
- Simulated fix for user reporting slow or broken website behavior

### Task 2 — Extension Management
- Navigated to chrome://extensions
- Reviewed all installed extensions:
  - Claude in Chrome — legitimate Anthropic extension, kept enabled
  - Google Docs Offline — legitimate Google extension, kept enabled
  - McAfee WebAdvisor — legitimate security tool, kept enabled
- Confirmed no suspicious or unknown extensions present
- Learned extensions are a common cause of browser slowness and crashes

### Task 3 — Chrome Version Check
- Navigated to chrome://settings/help
- Confirmed Chrome was fully up to date
- Verified no pending updates
- Learned outdated browsers are a security risk and common cause of site compatibility issues

### Task 4 — Incognito Mode Diagnostics
- Opened Incognito window via Ctrl + Shift + N
- Reviewed what Incognito does and does not do
- Confirmed Incognito disables all extensions automatically
- Confirmed Incognito starts with no cached data
- Used as isolation tool to rule out extensions and cache as cause of issue

### Task 5 — Chrome Reset Page
- Navigated to chrome://settings/reset
- Reviewed Restore settings to original defaults option
- Confirmed reset clears extensions, cookies, and custom settings
- Confirmed reset keeps bookmarks and saved passwords
- Learned to always inform user what will be affected before running reset

## Key Concepts
- **Cache** stores old versions of websites locally — clearing forces a fresh load
- **Incognito** disables all extensions and starts with no cache — essential for isolation testing
- **Chrome reset** keeps bookmarks and saved passwords — always tell user before running
- **Always keep browser up to date** — outdated browsers are a security risk
- **Extensions** are a common cause of browser slowness and unexpected behavior
- **Try different browser** to isolate whether issue is Chrome-specific or system-wide

## Screenshots
See screenshots folder for documented evidence of each task.
