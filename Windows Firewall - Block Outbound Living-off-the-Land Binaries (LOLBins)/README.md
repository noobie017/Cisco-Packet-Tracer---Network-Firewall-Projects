# Windows Firewall - Block Outbound Living-off-the-Land Binaries (LOLBins)

## Description
This lab demonstrates how to create outbound firewall rules on a Windows 10 endpoint to block common living-off-the-land binaries (LOLBins) from making external network connections. 
These binaries are frequently abused by attackers for payload delivery, proxy execution, and data exfiltration.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Objective:** Restrict outbound network access from commonly abused Windows binaries

---

## Binaries Blocked

| Binary            | Full Path                                      | Common Abuse                     |
|-------------------|------------------------------------------------|----------------------------------|
| certutil.exe      | C:\Windows\System32\certutil.exe               | Download & decode payloads      |
| bitsadmin.exe     | C:\Windows\System32\bitsadmin.exe              | Download files via BITS         |
| mshta.exe         | C:\Windows\System32\mshta.exe                  | Execute remote HTA payloads     |
| regsvr32.exe      | C:\Windows\System32\regsvr32.exe               | Proxy execution of scripts      |
| rundll32.exe      | C:\Windows\System32\rundll32.exe               | Execute DLLs / scripts          |

---

## Configuration Steps

1. Open **Windows Firewall with Advanced Security**:
   cmd
   wf.msc


Action: Block the connection
Profiles: Domain, Private, Public
Name: Block <binary> Outbound (example: Block certutil Outbound)

Repeat the process for all listed binaries.

Results Status: Successful Successfully created outbound firewall rules for multiple commonly abused LOLBins.
Demonstrated a practical host-based control to reduce the effectiveness of living-off-the-land techniques.
Strengthened endpoint defenses against payload delivery and proxy execution methods previously used in the lab.

