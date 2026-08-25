# Windows Firewall - Block All Outbound Traffic Except Lab Network

## Description
This configuration implements a restrictive outbound firewall policy on a Windows 10 endpoint.
The goal is to allow network communication only within the lab network (`192.168.10.0/24`) while blocking all other outbound internet traffic. This follows the security principle of **Default Deny Outbound**.

---

## Lab Environment

- **Target Machine:** Windows 10 Workstation (`192.168.10.9`)
- **Domain:** ADPRO
- **Lab Network:** `192.168.10.0/24`
- **Objective:** Restrict outbound traffic to the internal lab network only

---

## Configuration Steps

### 1. Create Allow Rule for Lab Network

Open **Windows Firewall with Advanced Security**:
   cmd
   wf.msc
Scope:Local IP addresses: Any IP address
Remote IP addresses: These IP addresses → Add 192.168.10.0/24

Action: Allow the connection
Profiles: Domain, Private, Public
Name: Allow Lab Network Only


Status: Successful Successfully restricted outbound traffic to the lab network only.
Verified that communication with internal lab systems remains functional.
Confirmed that external internet access is blocked.


