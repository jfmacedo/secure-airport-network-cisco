# Secure Airport Network (Cisco Packet Tracer)

## Overview

This project simulates a **secure and scalable airport network** using VLAN segmentation, a DMZ for public-facing services, firewall protection, and a remote data center connected via VPN.

The topology demonstrates key concepts of **network segmentation, security, and traffic control** in a realistic enterprise environment.

---
<p align="center">
  <img src="https://raw.githubusercontent.com/jfmacedo/secure-airport-network-cisco/1b6804c9563c52222f06ce29eb7df5dc2f2fc82d/screenshots/Figure%208-%20Update%20Topology.jpg" width="1200">
</p>

## Project Overview

The network was built to demonstrate fundamental **network security and segmentation concepts** in an airport scenario.

Different user groups and services are isolated into separate VLANs to improve **organization, security, and performance**, while controlled communication is enforced through routing and access control lists (ACLs).

A **DMZ** is used to host public services, and a **remote data center** simulates off-site infrastructure connected via a VPN tunnel.

---

## Problem & Solution

This project simulates a real airport network scenario where different user groups require controlled access to services.

### Challenges
The main challenges addressed in this project include:

- Isolating guest users from internal systems  
- Securing public services (web & DNS)  
- Allowing controlled external connectivity  
- Simulating enterprise architecture with remote infrastructure  

### Solution
To solve these challenges, the following technologies and strategies were implemented:

- **VLAN segmentation** to isolate different network zones  
- **Access Control Lists (ACLs)** to restrict guest traffic  
- **DMZ (Demilitarized Zone)** to expose only necessary services (Web & DNS)  
- **Firewall configuration** to control traffic between networks  
- **VPN connectivity** to securely connect a remote data center  

---

## Traffic Flow Example

Traffic Flow

This example demonstrates how controlled access is enforced between the Guest Network and the DMZ using VLAN segmentation and ACL policies.

1. A guest device initiates an HTTP request to the DMZ Web Server  
2. The request is forwarded through the Guest VLAN and reaches the Core Switch  
3. ACL policies permit only specific traffic (HTTP/ICMP) to access the DMZ  
4. The Web Server processes the request and sends the response back to the Guest device  

<p align="center">
  <img src="https://raw.githubusercontent.com/jfmacedo/secure-airport-network-cisco/f112b94a9e3925f80dc4c15974d618ad573b4f4c/screenshots/Figure%209%20-%20Traffic%20Flow%20Diagram.jpg" width="900">
</p>

This flow highlights how the network design ensures security while allowing controlled access to public services.

---

## Features

* VLAN segmentation for different airport zones:

  * **Authority VLAN** (internal trusted network)
  * **Flight Services VLAN** (operational systems)
  * **Guest VLAN** (public access)
  * **DMZ VLAN** (web & DNS servers)

* Inter-VLAN routing using **Router-on-a-Stick**

* Trunk links between switches (**802.1Q**)

* Extended **Access Control Lists (ACLs)** for traffic filtering

* Web and DNS servers deployed in the **DMZ**

* Simulated **Firewall** controlling traffic between internal and external networks

* **ISP Router** to simulate Internet access

* **Remote Data Center** connected via **VPN tunnel**, containing:
  * Application Server
  * Database Server

* Connectivity testing using:

  * `ping`
  * `HTTP`

---

## Security Policy

* Guest network (**VLAN 30**) is allowed to:

  * Access the web server via **HTTP**
  * Ping the web server (ICMP)

* Guest network is **restricted from**:

  * Accessing internal networks (**Authority and Flight Services VLANs**)

---

## Technologies Used

* Cisco Packet Tracer
* VLAN configuration (IEEE 802.1Q)
* Inter-VLAN Routing (Router-on-a-Stick)
* Extended ACLs
* Network Segmentation
* DMZ Design
* Basic Firewall Simulation
* VPN Concept (Site-to-Site)

---

## Network Address Translation (NAT)

To enable communication between internal VLANs and external networks, NAT (Network Address Translation) was configured on the Edge Firewall router.

The internal private networks were defined using an access control list (ACL). These networks were marked as NAT inside, allowing their traffic to be translated when accessing external resources. The interface connected to the ISP was configured as NAT outside, representing the public-facing side of the network.
Port Address Translation (PAT) was implemented using NAT overload, allowing multiple internal devices to share a single public IP address. This approach improves scalability and reduces the need for multiple public IPs.
The NAT translation process dynamically maps internal (private) IP addresses to a public IP address using different port numbers. This ensures that multiple devices can communicate simultaneously with external networks. Verification of the NAT configuration was performed using the `show ip nat translations` command. The output confirmed that internal addresses were successfully translated into the public IP address.
Connectivity tests using ICMP (ping) were also conducted from internal devices to external networks. The successful responses confirmed that NAT was correctly configured and operational.

In conclusion, NAT plays a critical role in this network design by enabling secure and efficient communication between private internal networks and external resources while hiding internal IP addressing.

---

## Network Segments

* **Authority VLAN**: Internal trusted devices
* **Flight Services VLAN**: Operational systems
* **Guest VLAN**: Visitor/public access devices
* **DMZ VLAN**: Public-facing server zone
* **Remote Data Center**: External infrastructure connected via VPN

---

## Objectives

* Separate network traffic using VLANs
* Control communication between segments using ACLs
* Host secure public services in the DMZ
* Simulate enterprise-level architecture with firewall and VPN
* Test connectivity between devices and services
* Apply real-world networking concepts in a practical scenario

---

## Testing

The following tests were performed:

* Device-to-device connectivity using `ping`
* Access to the DMZ web server via HTTP
* Verification of VLAN segmentation and routing behavior
* Confirmation that ACL rules correctly restrict unauthorized access
* Validation of connectivity to the remote data center via VPN

---

## Author

**João Filipe Macedo**
