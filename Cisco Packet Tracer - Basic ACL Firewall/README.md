A simple yet effective router-based firewall project using Standard and Extended Access Control Lists (ACLs) in Cisco Packet Tracer.

This project demonstrates how a Cisco router can act as a basic firewall to control traffic between an "Outside" (Internet) network and an "Inside" (LAN) network.

Topology

🎯 Project Objectives
Understand how ACLs work as a basic firewall
Configure Standard ACL (source IP filtering)
Configure Extended ACL (source, destination, protocol & port filtering)
Learn ACL placement rules (inbound vs outbound)
Understand the implicit deny all rule
Test allowed and blocked traffic
🛠 Topology
Devices:

1 × Cisco 2911 Router (acting as Firewall)
2 × 2960 Switches
3 × PCs (PC0 = Outside, PC1 & PC2 = Inside)
Networks:

Outside Network: 192.168.10.0/24
Inside Network: 192.168.20.0/24
Full Topology

📋 IP Addressing Table
Device	Interface/PC	IP Address	Subnet Mask	Default Gateway
Router	G0/0 (Outside)	192.168.10.1	255.255.255.0	-
Router	G0/1 (Inside)	192.168.20.1	255.255.255.0	-
PC0	NIC	192.168.10.10	255.255.255.0	192.168.10.1
PC1	NIC	192.168.20.10	255.255.255.0	192.168.20.1
PC2	NIC	192.168.20.20	255.255.255.0	192.168.20.1
🔧 Configuration Highlights
1. Standard ACL (Source IP Filtering)
access-list 10 permit host 192.168.20.10
access-list 10 deny any

interface GigabitEthernet0/0
 ip access-group 10 out
