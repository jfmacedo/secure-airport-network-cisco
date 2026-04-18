# Secure Airport Network (Cisco Packet Tracer)

## Overview

This project simulates a **secure and scalable airport network** using VLAN segmentation, a DMZ for public-facing services, firewall protection, and a remote data center connected via VPN.

The topology demonstrates key concepts of **network segmentation, security, and traffic control** in a realistic enterprise environment.

---

## Project Overview

The network was built to demonstrate fundamental **network security and segmentation concepts** in an airport scenario.

Different user groups and services are isolated into separate VLANs to improve **organization, security, and performance**, while controlled communication is enforced through routing and access control lists (ACLs).

A **DMZ** is used to host public services, and a **remote data center** simulates off-site infrastructure connected via a VPN tunnel.

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