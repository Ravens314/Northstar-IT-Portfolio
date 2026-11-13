# INC-003 — Network Connectivity Troubleshooting Report

**Company:** Northstar Solutions (Simulated)  
**Role:** IT Help Desk Technician (Lab Simulation)  
**Department:** Human Resources  
**Issue:** Employee Unable to Connect to the Internet  
**Operating System:** Windows 11  
**Ticket Status:** Investigation Completed

## 1. Reported Problem

An employee reported being unable to access websites and company resources.

**Objective:** Investigate potential network connectivity problems and document the findings.

## 2. Troubleshooting Investigation

### Investigation 1: IP Configuration

**Tool:** Windows PowerShell (`ipconfig`)

**Actions:**
- Reviewed the workstation's network configuration.
- Identified the active Wi-Fi adapter.
- Verified the workstation's IPv4 address and default gateway.

**Findings:**
- IPv4 address: `192.168.1.130`
- Subnet mask: `255.255.255.0`
- Default gateway: `192.168.1.254`

**Result:** Network configuration successfully identified.

**Evidence:** [View IP Configuration](screenshots/02-IP-Configuration.png.png)

### Investigation 2: Default Gateway Connectivity

**Tool:** Windows PowerShell (`ping`)

**Actions:**
- Initially tested `192.168.1.1`, which returned "Destination host unreachable."
- Used `ipconfig` to identify the correct default gateway.
- Repeated the connectivity test using `192.168.1.254`.

**Findings:**
- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Average response time: 3 ms

**Result: PASS — Default gateway connectivity confirmed.**

**Evidence:** [View Gateway Connectivity](screenshots/03-Gateway-Connectivity.png)

### Investigation 3: Internet Connectivity

**Tool:** Windows PowerShell (`ping 1.1.1.1`)

**Actions:**
- Tested connectivity to an external IP address.
- Reviewed packet loss and response times.

**Findings:**
- Packets sent: 4
- Packets received: 4
- Packet loss: 0%
- Minimum latency: 202 ms
- Maximum latency: 385 ms
- Average latency: 284 ms

**Result: PASS — External IP connectivity confirmed.**

**Performance Observation:** Elevated latency was observed during testing.

**Evidence:** [View Internet Connectivity](screenshots/04-Internet-Connectivity.png)

### Investigation 4: DNS Resolution

**Tool:** Windows PowerShell (`nslookup example.com`)

**Actions:**
- Tested DNS name resolution.
- Verified that the configured DNS server returned IP addresses.

**Findings:**
- DNS server: `dsldevice6.attlocal.net`
- Domain tested: `example.com`
- Successfully resolved two IPv4 addresses and two IPv6 addresses.

**Result: PASS — DNS resolution successful.**

**Evidence:** [View DNS Investigation](screenshots/05-DNS-Investigation.png)

### Investigation 5: Network Adapter Status

**Tool:** Windows 11 Network Settings

**Actions:**
- Reviewed the wireless network adapter.
- Checked adapter status and connection information.

**Findings:**
- Adapter: Intel(R) Wi-Fi 6 AX200 160MHz
- Media state: Enabled
- Wi-Fi link speed: 866 Mbps
- Network traffic: Data successfully sent and received

**Result: PASS — Wireless adapter enabled and connected.**

**Evidence:** [View Network Adapter Status](screenshots/06-Network-Adapter-Status.png)

## 3. Final Findings

The investigation confirmed that the workstation could communicate with its default gateway, reach an external IP address, resolve DNS queries, and maintain an active Wi-Fi connection.

An initial troubleshooting error was corrected after identifying the workstation's actual default gateway.

**Primary Observation:** Elevated external network latency averaging 284 ms.

**Root Cause:** Not determined.

**Corrective Actions:** No network configuration changes were performed.

**Resolution:** The simulated employee internet outage was not reproduced or resolved.

## 4. Recommended Next Steps

1. Repeat latency tests to determine whether the delays persist.
2. Compare results using a wired Ethernet connection, if available.
3. Check Wi-Fi signal quality and network congestion.
4. Investigate other affected devices to determine whether the issue is isolated.
5. Escalate persistent connectivity or performance problems to the network administrator or internet service provider as appropriate.

## 5. Skills Demonstrated

- Windows 11 network troubleshooting
- IP configuration analysis
- Default gateway verification
- ICMP connectivity testing
- DNS troubleshooting
- Wireless network diagnostics
- Help Desk incident documentation

## 6. Screenshot Evidence

[01 — Help Desk Ticket](screenshots/01-INC-003-Ticket.png)

[02 — IP Configuration](screenshots/02-IP-Configuration.png)
[03 — Gateway Connectivity](screenshots/03-Gateway-Connectivity.png)

[04 — Internet Connectivity](screenshots/04-Internet-Connectivity.png)

[05 — DNS Investigation](screenshots/05-DNS-Investigation.png)

[06 — Network Adapter Status](screenshots/06-Network-Adapter-Status.png)

## 7. Lab Disclaimer

This project is an educational Help Desk simulation conducted on a functioning Windows 11 workstation.

The fictional employee's internet outage was not reproduced. The investigation documents actual diagnostic commands and observations without claiming an unverified repair.

**Final Status: Educational Investigation Completed.**
