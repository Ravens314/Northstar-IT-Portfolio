# HD-004 — Active Directory Help Desk Support

## Northstar Solutions (Simulated)

This folder contains screenshots documenting hands-on
Windows Server and Active Directory Help Desk training.

## Screenshot Evidence Checklist

- [ ] 01-VirtualBox-Server-Configuration.png
- [ ] 02-Windows-Server-Installation.png
- [ ] 03-Windows-Server-2025-Desktop.png
- [ ] 04-Server-Computer-Name.png
- [ ] 05-Server-Network-Configuration.png
- [ ] 06-Active-Directory-Installation.png
- [ ] 07-Domain-Controller-Configuration.png
- [ ] 08-Employee-Account-Creation.png
- [ ] 09-Employee-Password-Reset.png
- [ ] 10-Employee-Account-Unlock.png
- [ ] 11-Security-Group-Management.png

## Skills Being Developed

- Windows Server administration
- Active Directory navigation
- Employee account creation
- Password resets
- Account unlocking
- Security group membership management
- Help Desk ticket documentation

All activities are performed in a simulated
training environment.


---

## Network Troubleshooting: DHCP/APIPA Investigation

### Lab Environment
- Company: Northstar Solutions (Simulated)
- Server: NORTHSTAR-DC01
- Operating System: Windows Server 2025 Standard Evaluation
- Virtualization Platform: Oracle VirtualBox
- Network Type: Internal Network (Northstar-Lab)
- Static IPv4 Address: 192.168.50.10
- Subnet Mask: 255.255.255.0
- Preferred DNS Server: 192.168.50.10

### Problem Identified

During Windows Server configuration, the server received an
Automatic Private IP Address (APIPA) of 169.254.1.190.

This indicated that the server did not receive a usable IPv4
address from a DHCP server.

Because the virtual machine was connected to an isolated
VirtualBox internal network, DHCP service availability needed
to be investigated.

### Troubleshooting Steps Performed

1. Opened Network Connections to inspect the Ethernet adapter.
2. Reviewed the adapter's IPv4 configuration.
3. Ran `ipconfig /all` to inspect network addressing.
4. Identified the APIPA address 169.254.1.190.
5. Inspected the VirtualBox network configuration.
6. Confirmed the adapter was connected to the Northstar-Lab
   internal network.
7. Used PowerShell `Get-NetAdapter` to verify the Ethernet
   adapter was operational.
8. Configured a static IPv4 address of 192.168.50.10.
9. Configured the subnet mask as 255.255.255.0.
10. Configured the preferred DNS server as 192.168.50.10.
11. Used PowerShell to verify the assigned IPv4 address.
12. Used `Get-NetIPInterface` to verify DHCP was disabled.

### Investigation Results

- Initial IPv4 address: 169.254.1.190 (APIPA)
- Configured IPv4 address: 192.168.50.10
- Subnet mask: 255.255.255.0
- Preferred DNS server: 192.168.50.10
- Ethernet adapter status: Up
- DHCP status after configuration: Disabled

The server's static IPv4 configuration was verified.

This resolved the server's local IP-address configuration issue
and prepared the environment for Active Directory setup.

The screenshots do not establish that a DHCP server was
repaired or that connectivity to another machine was tested.

### Skills Demonstrated

- Windows Server network troubleshooting
- DHCP and APIPA investigation
- Static IPv4 configuration
- DNS configuration
- PowerShell troubleshooting
- Network adapter diagnostics
- VirtualBox internal networking
- Technical documentation

### Screenshot Evidence

- [VirtualBox Internal Network](screenshots/05-VirtualBox-Internal-Network.png)
- [DHCP/APIPA Problem](screenshots/06-DHCP-APIPA-Problem.png)
- [Ethernet Adapter Status](screenshots/07-Ethernet-Adapter-Status.png)
- [Static IP Verification](screenshots/08-Static-IP-Verification.png)

### Project Status

Network troubleshooting and static IP configuration completed.

Active Directory Domain Services and DNS installation
configuration is in progress.
