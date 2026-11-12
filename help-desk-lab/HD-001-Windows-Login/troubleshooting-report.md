# INC-001 — Windows Login Troubleshooting

**Company:** Northstar Solutions (Simulated)  
**Role:** IT Help Desk Technician (Lab Simulation)  
**Issue:** Employee Unable to Sign In  
**Operating System:** Windows 11  
**Ticket Status:** Investigation Completed

## 1. Reported Problem

An employee reported being unable to sign in to their Windows 11 workstation.

**Objective:** Investigate potential account, authentication, and network-related causes.

## 2. Troubleshooting Investigation

### Investigation 1: User Account Verification
**Tool:** Command Prompt (`whoami`)

- Identified the currently signed-in Windows account.
- Reviewed the account identification process.

**Result:** Account identification procedure documented.

### Investigation 2: Windows Login Settings
**Tool:** Windows Settings → Sign-in Options

- Reviewed available authentication methods.
- Examined Windows Hello PIN settings.

**Result:** Sign-in configuration reviewed. No changes performed.

### Investigation 3: Network Configuration
**Tool:** Command Prompt (`ipconfig`)

- Examined network adapter configuration.
- Reviewed IP address and default gateway information.

**Result:** Network configuration investigation documented.

### Investigation 4: Network Connectivity
**Tool:** Command Prompt (`ping 1.1.1.1`)

- Performed a basic network connectivity test.
- Investigated whether network communication could affect authentication.

**Result:** Connectivity test performed. Actual success or failure must be confirmed from the command output.

### Investigation 5: Local Windows Accounts
**Tool:** Command Prompt (`net user`)

- Reviewed local Windows accounts.
- Investigated available account information.

**Result:** Local account investigation documented.

## 3. Final Findings

The investigation covered five key troubleshooting areas: user accounts, authentication settings, network configuration, connectivity, and local account information.

Testing was performed on a functioning Windows 11 computer as part of an educational simulation.

**Root Cause:** Not confirmed.  
**Corrective Actions:** None required or performed.  
**Resolution:** Investigation completed; fictional employee login issue not reproduced or resolved.

## 4. Skills Demonstrated

- Windows 11 troubleshooting
- User account identification
- Windows Hello authentication settings
- Basic network diagnostics
- Command Prompt
- Help Desk ticket documentation

## 5. Supporting Evidence

Screenshots are available in the `screenshots` folder and document the troubleshooting procedures performed.

**Final Status:** Educational Lab Completed.
**Resolution:** No corrective changes were performed.

**Final Ticket Status:** Educational investigation completed; employee login issue not verified as resolved.
