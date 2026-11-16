# HD-004 — DHCP and Network Configuration Troubleshooting

**Organization:** Northstar Solutions (Simulated)  
**Environment:** Windows Server 2025 / Oracle VirtualBox  
**Server Name:** NORTHSTAR-DC01  
**Category:** Help Desk / Network Troubleshooting  
**Status:** Static IP configuration verified

## 1. Problem Description

While preparing a Windows Server 2025 virtual machine for Active Directory Domain Services, I discovered that the server was not receiving an IPv4 address through DHCP.

The server automatically assigned itself the address `169.254.1.190`, indicating that DHCP address assignment had not succeeded.

## 2. Initial Investigation

I opened Network Connections and inspected the Ethernet adapter.

I reviewed the Internet Protocol Version 4 (TCP/IPv4) settings and found that the server was configured to obtain an IP address automatically.

I then opened Command Prompt and executed:

`ipconfig /all`

The output showed:

- IPv4 Address: 169.254.1.190
- Subnet Mask: 255.255.0.0
- DHCP Enabled: Yes
- Default Gateway: None

These findings indicated that Windows had assigned an APIPA address instead of receiving a DHCP lease.

## 3. Network Adapter Troubleshooting

I opened PowerShell and executed:

`Get-NetAdapter`

The Ethernet adapter was listed as Up.

This helped establish that Windows recognized the virtual network adapter and that its connection status was active.

I also inspected the virtual machine's network configuration in Oracle VirtualBox.

The adapter was connected to an Internal Network named `Northstar-Lab`.

An internal network does not automatically provide DHCP services, which explains why automatic IPv4 assignment may fail when no DHCP server is available.

## 4. Corrective Action

Because the server would be used for Active Directory and DNS, I configured a static IPv4 address.

The network configuration was:

- IP Address: 192.168.50.10
- Subnet Mask: 255.255.255.0
- Default Gateway: None
- Preferred DNS: 192.168.50.10

The server's preferred DNS address was configured to reference itself in preparation for installing the DNS Server role.

## 5. Verification

After configuring the static address, I used PowerShell to inspect the network settings.

The results confirmed:

- Interface Alias: Ethernet
- IPv4 Address: 192.168.50.10
- DNS Server: 192.168.50.10
- DHCP: Disabled
- Connection State: Connected

The static IPv4 configuration was successfully applied.

## 6. Outcome

The server no longer depended on DHCP for its IPv4 configuration.

I verified that the Ethernet interface had the intended static IPv4 address and DNS settings.

This completed the network configuration needed to proceed with the Active Directory Domain Services and DNS Server installation.

Domain name resolution and client connectivity will require separate verification after the server roles are configured.

## 7. Skills Demonstrated

- Windows Server administration
- IPv4 troubleshooting
- DHCP and APIPA troubleshooting
- Static IP configuration
- DNS configuration
- PowerShell network diagnostics
- VirtualBox network configuration
- Technical documentation

## 8. Lessons Learned

A `169.254.x.x` address can indicate that a computer failed to obtain an IPv4 address through DHCP.

When troubleshooting, it is important to check the adapter status, IPv4 configuration, and virtual network settings before making changes.

Servers running Active Directory and DNS generally benefit from stable, predictable IP addresses.

This project demonstrates my hands-on troubleshooting process in a simulated Windows Server environment.
