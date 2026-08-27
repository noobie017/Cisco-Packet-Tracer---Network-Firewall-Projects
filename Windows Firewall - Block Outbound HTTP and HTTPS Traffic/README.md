# Windows Firewall - Block Outbound HTTP and HTTPS Traffic

## Description
This configuration blocks outbound traffic on TCP ports 80 (HTTP) and 443 (HTTPS) from a Windows 10 endpoint. 
The goal is to prevent the system from accessing web services on the internet while still allowing other types of network communication.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Lab Network:** `192.168.10.0/24`
- **Objective:** Block outbound web traffic (HTTP/HTTPS)

---

## Configuration Steps

1. Open **Windows Firewall with Advanced Security**:
   cmd
   wf.msc
   Select TCP and specify remote ports: 80, 443 → Next.
   Action: Block the connection → Next.
   Profiles: Domain, Private, and Public → Next.
   Name the rule: Block Outbound HTTP-HTTPS → Finish.


Results Status: Successful Successfully created an outbound firewall rule blocking HTTP and HTTPS traffic.
Verified that external web access is restricted.
Confirmed that internal lab connectivity is unaffected.

