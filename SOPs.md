# MG Santos SOPs for Tier 1 Helpdesk Common Issues
---
# Active Directory User Management

## 1. Password Reset Procedure
1. Open **Active Directory Users and Computers (ADUC)**.
2. Search for the user's name or username.
3. Right-click the user and select **Reset Password**.
4. Set a temporary password and ensure "User must change password at next logon" is checked.

## 2. Unlocking Accounts
1. Locate the user in ADUC.
2. Right-click -> **Properties** -> **Account** tab.
3. Check if the box "Unlock account. This account is currently locked out on this Active Directory Domain Controller" is active.
4. Check the box and click **Apply**.

# Network Troubleshooting Flowchart

## Issue: "No Internet Access"
1. **Verify Physical Layer**: Check Ethernet seating or Wi-Fi status.
2. **Command Line Diagnostics**:
   - `ipconfig /all` (Check for valid Gateway)
   - `ping 127.0.0.1` (Test NIC health)
   - `nslookup google.com` (Test DNS resolution)
3. **Flush Stack**:
   - `netsh winsock reset`
   - `ipconfig /flushdns`

   # Incident Report: Outlook Integration Error

**Ticket ID:** #99821  
**Priority:** Medium  
**Category:** Software / Productivity Tools

### Description
User reported that Outlook stays in "Disconnected" mode despite having a stable internet connection.

### Troubleshooting Steps
1. Checked for Windows Updates (None pending).
2. Attempted to open Outlook in **Safe Mode** (`outlook.exe /safe`).
3. Found a corrupted Add-in causing the hang.

### Resolution
Disabled the conflicting Add-in and repaired the Office Installation via Control Panel. 
**Result:** Outlook connected and synced successfully.
