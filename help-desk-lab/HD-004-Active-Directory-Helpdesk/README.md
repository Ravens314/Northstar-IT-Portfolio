# HD-004 — Active Directory Help Desk Support

## Northstar Solutions | Simulated IT Environment

**Project Status:** Hands-on technical lab completed  
**Focus:** Help Desk Support, Active Directory, Windows Server, and Identity Administration

---

## 1. Project Overview

This project demonstrates hands-on experience configuring and administering a simulated Windows Server environment for Northstar Solutions.

The goal was to practice common Help Desk responsibilities, including troubleshooting network connectivity, managing Active Directory user accounts, resetting passwords, managing security groups, and verifying account configurations using PowerShell.

All activities were performed in a personal virtual lab environment rather than a production business network.

## 2. Lab Environment

| Component | Configuration |
|---|---|
| Virtualization | Oracle VirtualBox |
| Operating System | Windows Server 2025 Standard Evaluation |
| Server Name | NORTHSTAR-DC01 |
| Domain | northstar.test |
| Server IP Address | 192.168.50.10 |
| Directory Services | Active Directory Domain Services |
| DNS | Windows Server DNS |
| Administration | Active Directory Users and Computers |
| Command Line | Windows PowerShell |

## 3. Network Troubleshooting

During initial server configuration, the virtual machine experienced an IP address assignment problem.

### Problem Identified

The server received an automatic private IP address:

169.254.1.190

This indicated that the system had not received a usable IPv4 address from a DHCP server.

### Troubleshooting Performed

1. Reviewed the server's network configuration.
2. Used `ipconfig /all` to inspect IP address information.
3. Identified the APIPA address.
4. Inspected the network adapter using PowerShell.
5. Reviewed the VirtualBox internal network configuration.
6. Configured the server with a static IPv4 address.
7. Verified the assigned address and DNS configuration.

### Result

The server was configured with:

- Static IP: 192.168.50.10
- DNS server: 192.168.50.10
- Network: Northstar-Lab

The static IP configuration enabled continued lab setup without relying on automatic DHCP address assignment.

**Detailed troubleshooting documentation:**

[View DHCP Network Troubleshooting Report](DHCP-Network-Troubleshooting.md)

## 4. Active Directory Domain Configuration

Installed Active Directory Domain Services and DNS Server roles.

Promoted NORTHSTAR-DC01 to the first domain controller in a new forest.

### Domain Configuration

- Domain name: northstar.test
- NetBIOS name: NORTHSTAR
- Domain controller: NORTHSTAR-DC01
- DNS server role: Installed
- Global Catalog: Enabled

Verified the server's domain membership and accessed Active Directory Users and Computers.

## 5. Organizational Unit Management

Created the following organizational unit structure:

northstar.test
└── Northstar-Employees
    └── IT

This structure provides a foundation for organizing employee accounts and applying department-specific administrative policies.

## 6. Active Directory User Administration

Created a simulated employee account.

| Attribute | Value |
|---|---|
| Employee | James Carter |
| Username | jcarter |
| Domain | northstar.test |
| Department OU | IT |
| Parent OU | Northstar-Employees |
| Account Status | Enabled |

Configured the account to require a password change at the next sign-in.

## 7. Security Group Management

Created the following Active Directory security group:

**Northstar-IT-Staff**

Group configuration:

- Group scope: Global
- Group type: Security
- Organizational Unit: IT

Added James Carter to the security group.

Verified group membership using Active Directory Users and Computers and PowerShell.

## 8. Password Reset and Account Management

Practiced common Help Desk account administration tasks:

- Resetting an employee password.
- Requiring a password change at the next sign-in.
- Disabling an employee account.
- Re-enabling an employee account.
- Checking whether an account is locked.
- Verifying account properties.

These exercises demonstrate foundational identity lifecycle administration.

## 9. PowerShell Verification

Used PowerShell to inspect Active Directory account properties.

### Verify Account Status

Get-ADUser -Identity jcarter -Properties LockedOut,Enabled |
Select-Object Name,Enabled,LockedOut

Verified that the account was enabled and not locked.

### Verify Security Group Membership

Get-ADPrincipalGroupMembership -Identity jcarter |
Select-Object Name

Confirmed membership in:

- Domain Users
- Northstar-IT-Staff

### Verify Organizational Unit

Get-ADUser -Identity jcarter -Properties DistinguishedName |
Select-Object Name,DistinguishedName

Confirmed the account's location:

CN=James Carter,OU=IT,OU=Northstar-Employees,DC=northstar,DC=test

## 10. Screenshot Evidence

Screenshots documenting the Windows Server configuration, network troubleshooting, Active Directory installation, and user administration exercises are stored in the project folder.

[View Screenshot Evidence](screenshots/)

The evidence includes:

- VirtualBox server configuration
- Windows Server installation
- Server computer name
- DHCP/APIPA troubleshooting
- Static IP configuration
- Network adapter verification
- Active Directory and DNS installation
- Domain controller promotion
- Organizational unit creation
- Employee account creation
- Security group creation
- Group membership verification
- Password reset
- Account enable/disable administration
- PowerShell account verification

## 11. Skills Demonstrated

### Help Desk Skills

- Windows Server administration
- Network troubleshooting
- IPv4 configuration
- User account provisioning
- Password resets
- Account troubleshooting
- Technical documentation

### Identity and Access Management Foundations

- Active Directory administration
- Identity lifecycle management
- Security group management
- Organizational unit management
- Account status verification
- PowerShell identity administration

## 12. Project Outcome

Successfully configured a simulated Windows Server Active Directory environment and performed common Help Desk account administration tasks.

Investigated a DHCP/APIPA addressing problem and configured static networking to support the lab environment.

Created and managed a simulated employee account, assigned security group membership, performed password administration, and verified account settings using PowerShell.

This project demonstrates foundational hands-on Help Desk and IAM administration skills.

---

**Northstar Solutions is a fictional organization used for technical training and portfolio demonstration.**
