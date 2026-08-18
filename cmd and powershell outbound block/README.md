# Windows Firewall - Block Outbound PowerShell & CMD

## Description
This lab demonstrates how to create outbound firewall rules on a Windows 10 endpoint to block `powershell.exe` and `cmd.exe` from making external network connections. This control helps mitigate living-off-the-land techniques commonly used for reverse shells and data exfiltration.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Objective:** Restrict outbound internet access from PowerShell and Command Prompt

---

## Configuration Steps

### 1. Open Windows Firewall with Advanced Security
cmd
wf.msc

### 2. Create Outbound Rule for PowerShellRule Type: Program
Program Path: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
Action: Block the connection
Profiles: Domain, Private, Public
Rule Name: Block PowerShell Outbound

### 3. Create Outbound Rule for CMDRule Type: Program
Program Path: C:\Windows\System32\cmd.exe
Action: Block the connection
Profiles: Domain, Private, Public
Rule Name: Block CMD Outbound

Status: Successful
Successfully created outbound firewall rules blocking external network access from powershell.exe and cmd.exe.
Verified the effectiveness of the rules through connectivity tests.
Confirmed that internal lab communication remains functional.


