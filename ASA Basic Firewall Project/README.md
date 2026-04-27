## ASA Basic Firewall Project

### Description
A basic Cisco ASA 5505 firewall separating an **Inside** (trusted) network from an **Outside** (untrusted/Internet) network.

- **Inside Network**: 192.168.20.0/24 (security-level 100)
- **Outside Network**: 192.168.10.0/24 (security-level 0)
- Demonstrates security levels, VLAN configuration on ASA 5505, and basic NAT/PAT.

### Key Features
- Proper ASA 5505 VLAN + SVI configuration
- Security levels (100 vs 0)
- Dynamic NAT/PAT for inside devices
- ICMP allowed from inside to outside
- Traffic from outside to inside is blocked by default

### Topology
- 1 × ASA 5505 Firewall
- 1 × PC on Outside network
- 1 × PC on Inside network

![Topology](asa-basic-firewall/screenshots/topology.png)

### Configuration Highlights

**ASA Key Commands:**
```bash
interface Ethernet0/0
 switchport access vlan 2
 no shutdown

interface Ethernet0/1
 switchport access vlan 1
 no shutdown

interface Vlan1
 nameif inside
 security-level 100
 ip address 192.168.20.1 255.255.255.0

interface Vlan2
 nameif outside
 security-level 0
 ip address 192.168.10.1 255.255.255.0

object network INSIDE-NET
 subnet 192.168.20.0 255.255.255.0
 nat (inside,outside) dynamic interface
