# Cisco Packet Tracer - DMZ Firewall Project

A classic **three-tier firewall design** with Outside, DMZ, and Inside zones. Built in Cisco Packet Tracer using a Router as the firewall with extended ACLs.

## 🎯 Project Objectives

- Implement a secure **DMZ (Demilitarized Zone)** architecture
- Control traffic between three security zones using ACLs
- Allow public access to DMZ web server while protecting the internal LAN
- Understand real-world firewall zoning and security policies

## 🛠 Topology

- **Outside** (Internet): PC0 (192.168.10.0/24)
- **DMZ**: Web Server (172.16.1.0/24) — accessible from outside
- **Inside** (LAN): PC1 (192.168.20.0/24) — trusted network

**Router** acts as the firewall with three interfaces.

## 📋 IP Addressing Table

|
 Zone      
|
 Device              
|
 IP Address          
|
 Default Gateway    
|
|
-----------
|
---------------------
|
---------------------
|
--------------------
|
|
 Outside   
|
 PC0                 
|
 192.168.10.10       
|
 192.168.10.1       
|
|
 Outside   
|
 Router G0/0         
|
 192.168.10.1        
|
 
-
|
|
 DMZ       
|
 Web Server          
|
 172.16.1.10         
|
 172.16.1.1         
|
|
 DMZ       
|
 Router G0/1         
|
 172.16.1.1          
|
-
|
|
 Inside    
|
 PC1                 
|
 192.168.20.10       
|
 192.168.20.1       
|
|
 Inside    
|
 Router G0/2         
|
 192.168.20.1        
|
-
|

## 🔧 Key Configuration (Router as Firewall)

### ACL Policy
- Outside → DMZ: Only HTTP (port 80) allowed to Web Server
- Outside → Inside: All traffic blocked
- Inside → Anywhere: Full access

### Main ACL
```bash
ip access-list extended OUTSIDE_IN
 permit tcp any host 172.16.1.10 eq 80
 deny ip any any
