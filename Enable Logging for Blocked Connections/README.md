# Windows Firewall - Enable Logging for Blocked Connections

## Description
This lab demonstrates how to enable logging of dropped (blocked) packets on a Windows 10 endpoint using Windows Firewall with Advanced Security. 
Logging blocked connections is a fundamental defensive practice that helps with monitoring, troubleshooting, and detecting potentially malicious outbound or inbound traffic.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Objective:** Enable and configure Windows Firewall to log blocked connections

---

## Configuration Steps

### Method 1: Graphical Interface (wf.msc)

1. Open **Windows Firewall with Advanced Security**:
   cmd
   wf.msc
   Windows Firewall with Advanced Security on Local Computer → Properties.
   For each profile (Domain, Private, and Public)
   Set the following:Log dropped packets: Yes
   Log file path: %systemroot%\system32\LogFiles\Firewall\pfirewall.log

Method 2: Command Linecmd

netsh advfirewall set allprofiles logging droppedconnections enable
netsh advfirewall set allprofiles logging filename %systemroot%\system32\LogFiles\Firewall\pfirewall.log
netsh advfirewall set allprofiles logging maxfilesize 4096

Results Status: Successful Successfully enabled logging of blocked connections across all firewall profiles.
Configured an appropriate log size limit.
Verified the log file location and accessibility.

