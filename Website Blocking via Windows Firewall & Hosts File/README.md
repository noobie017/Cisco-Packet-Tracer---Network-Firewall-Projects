Website Blocking via Windows Firewall & Hosts File
Description
This activity demonstrates how to restrict access to specific websites on a Windows 10 endpoint using two common methods: the Windows hosts file and Windows Firewall with Advanced Security (Outbound Rules).

Objective: Block access to selected adult websites on the target Windows 10 machine.

Lab Environment
Target Machine: Windows 10 Workstation (192.168.10.9)
Domain: ADPRO
Attacker Machine: Kali Linux (192.168.10.250) – not required for this activity
Method Used: Hosts File + Windows Firewall Outbound Rules
Method 1: Windows Firewall Outbound Rule
Steps PerformedOpened Windows Firewall with Advanced Security (wf.msc).
Created a new Outbound Rule. 2.Rule Type: Custom

Program: All programs

Scope:Local IP: Any

Remote IP: Specific IP addresses of the target websites

Action: Block the connection

Profiles: Domain, Private, Public

Named the rule: Block Porn Sites

Results Status: Successful Successfully blocked access to selected websites using the hosts file method. Configured Windows Firewall outbound rules as an additional control layer.
Demonstrated basic endpoint security hardening on the Windows 10 machine.
