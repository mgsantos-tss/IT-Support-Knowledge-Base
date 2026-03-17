# MG Santos SOPs for Tier 1 Helpdesk Common Issues
---
## Active Directory User Management

### 1. Password Reset Procedure
1. Open **Active Directory Users and Computers (ADUC)**.
2. Search for the user's name or username.
3. Right-click the user and select **Reset Password**.
4. Set a temporary password and ensure "User must change password at next logon" is checked.

### 2. Unlocking Accounts
1. Locate the user in ADUC.
2. Right-click -> **Properties** -> **Account** tab.
3. Check if the box "Unlock account. This account is currently locked out on this Active Directory Domain Controller" is active.
4. Check the box and click **Apply**.
---
## Network Troubleshooting Flowchart

### Issue: "No Internet Access"
1. **Verify Physical Layer**: Check Ethernet seating or Wi-Fi status.
2. **Command Line Diagnostics**:
   - `ipconfig /all` (Check for valid Gateway)
   - `ping 127.0.0.1` (Test NIC health)
   - `nslookup google.com` (Test DNS resolution)
3. **Flush Stack**:
   - `netsh winsock reset`
   - `ipconfig /flushdns`
---
## Incident Report: Outlook Integration Error

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
The conflicting Add-in was disabled, and the Office Installation was repaired via the Control Panel. 
**Result:** Outlook connected and synced successfully.
---
## Topic: Software & Productivity Suite Repairs

### Microsoft Teams "Sign-in Loop" or Loading Issues
**Scenario:** User is unable to log in or the app hangs on the loading screen.
1. **Close Teams**: Right-click the Teams icon in the taskbar and select **Quit**.
2. **Clear Cache**:
   - Press `Win + R`, type `%appdata%\Microsoft\Teams`, and hit Enter.
   - Delete all files and folders in this directory.
3. **Restart**: Relaunch Teams and attempt to sign in again.

### Outlook Data File Repair (.PST / .OST)
**Scenario:** Outlook is slow, freezing, or showing "Cannot open your default e-mail folders."
1. Close Outlook.
2. Open the **Control Panel** > **Mail** > **Data Files**.
3. Select the account and click **Open File Location**.
4. Use the `ScanPST.exe` tool (found in the Office installation folder) to repair the file.
   

### Browser Troubleshooting (Chrome/Edge)
1. **Incognito Test**: Ask the user to try the site in an Incognito/InPrivate window. 
   - *If it works*: The issue is likely a corrupted extension or cache.
2. **Clear Data**: Settings > Privacy > Clear Browsing Data (Clear "Cookies" and "Cached images").
---
## Topic: Essential Online Security Advice

### Reporting Phishing/Suspicious Emails
**Advice to End-User:**
- "Do not click any links or download attachments if the sender's address looks suspicious."
- "Check for 'External Sender' banners at the top of the email."
- **Action**: Use the "Report Phishing" button in Outlook or forward the email as an attachment to `security-incident@company.com`.

### Multi-Factor Authentication (MFA) Setup
**Scenario:** User is locked out because they got a new phone and cannot receive MFA codes.
1. **Verification**: Verify the user's identity via a secondary method (Manager approval or security questions).
2. **Reset MFA**: In the admin portal, "Require Re-registration" for MFA.
3. **Guidance**: Walk the user through downloading the **Microsoft Authenticator** app and scanning the new QR code.
   

### Workstation Security
- **Locking Screen**: Remind users to press `Win + L` every time they leave their desk.
- **Updates**: Ensure "Automatic Updates" are enabled to patch critical vulnerabilities.
