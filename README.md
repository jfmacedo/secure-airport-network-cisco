# Secure Airport Network (Cisco Packet Tracer)

## Overview

Modern airport infrastructures face a critical challenge: they must support a high volume of diverse users—ranging from administrative staff to international passengers—while protecting sensitive flight management systems from cyber threats.
This project addresses these challenges by simulating a secure, scalable, and multi-layered airport network. By implementing robust VLAN segmentation, a dedicated DMZ for public services, and firewall-backed perimeter security, the design ensures that guest traffic remains entirely isolated from operational data. The inclusion of a VPN-connected remote data center further demonstrates a realistic enterprise-level solution for data redundancy and secure remote access.
---

## Network Topology

<p align="center">
  <img src="https://raw.githubusercontent.com/jfmacedo/secure-airport-network-cisco/1b6804c9563c52222f06ce29eb7df5dc2f2fc82d/screenshots/Figure%208-%20Update%20Topology.jpg" width="1200">
</p>

---

## Project Overview

This network was designed to simulate a real airport infrastructure, where different departments and user groups require secure and controlled access to network resources. 
The network is organized into four primary zones (VLANs), ensuring data traffic is isolated according to the security requirements of each group:
- VLAN 10 – Airport Authority: A restricted zone housing administrative workstations and the central flight management server.
- VLAN 20 – Flight Service Providers: Dedicated to third-party vendors and operational services, with controlled access to central resources.
- VLAN 30 – Guest Network: An isolated segment for passengers, providing connectivity via wired terminals and Wireless Access Points (WAPs) for mobile devices and laptops.
- VLAN 40 – DMZ (Demilitarized Zone): A security buffer hosting externally accessible services, such as Web and DNS servers, shielding the internal network from direct internet threats.

Topology and Technical Infrastructure
The design employs a Hybrid Topology, combining an extended star structure with a high-performance switching core.
- Network Core: A Layer 3 Multilayer Switch (3560) acts as the backbone of the network, handling inter-VLAN routing and connecting the various subnets.
- Perimeter Security: The network edge features a dedicated Firewall and an Edge Router to manage the WAN/Internet gateway.
- Remote Connectivity: A VPN Tunnel has been implemented to link the local network to a Remote Data Center, ensuring secure data synchronization and off-site backups.
- Addressing Management: Devices obtain IP addresses dynamically via DHCP services configured on specific servers for each segment, streamlining connectivity for the high volume of users in the Guest VLAN.

---

## Objectives

- Implement VLAN segmentation for different network zones  
- Configure inter-VLAN routing  
- Protect internal resources using ACLs  
- Provide controlled internet access using NAT  
- Simulate a realistic enterprise-level network design  
- Validate connectivity and security through testing  

---

## Network Design

The network is divided into multiple logical segments:

- **VLAN 10 – Staff Network**
- **VLAN 20 – Operations Network**
- **VLAN 30 – Guest Network**
- **VLAN 40 – DMZ (Web Server)**

Each VLAN is isolated and controlled through routing and ACL policies.

---

## Network Segments

| VLAN | Network | Purpose |
|------|--------|--------|
| VLAN 10 | 192.168.10.0/24 | Staff |
| VLAN 20 | 192.168.20.0/24 | Operations |
| VLAN 30 | 192.168.30.0/24 | Guest |
| VLAN 40 | 192.168.40.0/24 | DMZ |
| Data Center | 10.10.10.0/24 | Internal Servers |

---

## Traffic Flow Example

<p align="center">
  <img src="https://raw.githubusercontent.com/jfmacedo/secure-airport-network-cisco/f112b94a9e3925f80dc4c15974d618ad573b4f4c/screenshots/Figure%209%20-%20Traffic%20Flow%20Diagram.jpg" width="900">
</p>

1. Guest user sends HTTP request to Web Server  
2. Traffic is routed through the Core Switch  
3. ACL allows HTTP access to the DMZ  
4. Response is returned to the Guest  

---

## Security Policy

Access Control Lists (ACLs) were configured to enforce strict network segmentation.

- Guest Network is **blocked** from accessing the Data Center  
- Internal VLANs are isolated from each other  
- Only required traffic is allowed  
- DMZ services are accessible under controlled conditions  

---

## Network Address Translation (NAT)

To enable communication between internal VLANs and external networks, NAT (Network Address Translation) was configured on the Edge Firewall router.

The internal private networks were defined using an access control list (ACL), including the following VLAN subnets:

- 192.168.10.0/24 (Staff Network)  
- 192.168.20.0/24 (Operations Network)  
- 192.168.30.0/24 (Guest Network)  
- 192.168.40.0/24 (DMZ Network)  

All internal subinterfaces were configured as NAT inside, while the external interface connected to the ISP was configured as NAT outside.

Port Address Translation (PAT) was implemented using NAT overload, allowing multiple internal devices to share a single public IP address.

The NAT configuration was validated using translation tables and connectivity tests, confirming correct operation.

---

## Security Validation – Guest Network Isolation

To validate the security of the network, connectivity tests were performed from a Guest Network device.

A ping test was executed from a Guest PC (VLAN 30) to the Data Center server (10.10.10.10). The result showed 100% packet loss, confirming that access is successfully blocked by the configured ACL rules.

In contrast, a second test was performed to verify external connectivity. The Guest PC was able to successfully ping the ISP router (200.0.0.1), demonstrating that internet access is allowed through NAT.

This confirms:
- Proper network segmentation  
- Enforcement of security policies  
- Protection of sensitive infrastructure  

---

## Testing and Validation

The network configuration was validated through multiple connectivity tests:

- Internal communication between VLAN gateways  
- External connectivity using NAT  
- Successful translation entries in NAT table  
- Security validation through blocked access attempts  

These tests confirm that the network behaves as expected.

---

## Technologies Used

- Cisco Packet Tracer  
- VLAN Configuration  
- Inter-VLAN Routing  
- Access Control Lists (ACL)  
- NAT / PAT  
- DMZ Architecture  
- Basic Network Security Principles  

---

## Conclusion

This project demonstrates the design and implementation of a secure, segmented network based on real-world enterprise principles.

Through the use of VLANs, ACLs, NAT, and a DMZ architecture, the network ensures both efficient communication and strong security controls. The successful testing of connectivity and access restrictions confirms that the network behaves as expected in a realistic airport scenario.

---

## Author

Joao Filipe Macedo
