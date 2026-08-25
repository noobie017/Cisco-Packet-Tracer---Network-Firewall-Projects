# Windows Firewall - Restrict Inbound RDP Access

## Description
This configuration restricts inbound Remote Desktop Protocol (RDP) access on a Windows 10 endpoint.
The rule allows RDP connections only from the lab network (`192.168.10.0/24`) and blocks attempts from any external IP addresses. This follows the principle of least privilege for remote access.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Lab Network:** `192.168.10.0/24`
- **Port:** TCP 3389 (RDP)
- **Objective:** Allow inbound RDP only from the internal lab network

---

## Configuration Steps

1. Open **Windows Firewall with Advanced Security**:
   cmd
   wf.msc
   Name the rule: Allow RDP from Lab Network Only → Finish.
   Under Remote IP addresses, select These IP addresses
   Add: 192.168.10.0/24

Results Status: Successful Successfully created an inbound firewall rule restricting RDP access.
Verified that connections from the lab network are allowed.
Confirmed that the rule limits exposure of the RDP service.


