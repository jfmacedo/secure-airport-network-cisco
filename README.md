# Secure Airport Network (Cisco Packet Tracer)

## Overview

This project simulates a **secure airport network** designed to separate different areas of access using VLANs and includes a DMZ for public-facing services.
The topology demonstrates key concepts of **network segmentation, security, and traffic control** in a realistic environment.

---

## Project Overview

The network was built to demonstrate fundamental **network security and segmentation concepts** in an airport scenario.
Different user groups and services are isolated into separate VLANs to improve **organization, security, and performance**.

---

## ⚙️ Features

* VLAN segmentation for different airport zones:

  * **Authority VLAN** (internal trusted network)
  * **Guest VLAN** (public access)
  * **DMZ VLAN** (web server zone)
  * **Services VLAN** (internal services)

* Inter-VLAN routing using **Router-on-a-Stick**

* Trunk links between switches (**802.1Q**)

* Extended **Access Control Lists (ACLs)** for traffic filtering

* Web server deployed in the **DMZ**

* Connectivity testing using:

  * `ping`
  * `HTTP`

---

## Security Policy

* Guest network (**VLAN 30**) is allowed to:

  * Access the web server via **HTTP**
  * Ping the web server (ICMP)

* Guest network is **restricted from**:

  * Accessing internal networks (**Authority and Services VLANs**)

---

## Technologies Used

* Cisco Packet Tracer
* VLAN configuration (IEEE 802.1Q)
* Inter-VLAN Routing
* Extended ACLs
* Basic network security concepts
* DMZ deployment

---

## Network Segments

* **Authority VLAN**: Internal trusted devices
* **Guest VLAN**: Visitor/public access devices
* **DMZ VLAN**: Public-facing server zone
* **Services VLAN**: Internal services and infrastructure

---

## Objectives

* Separate network traffic using VLANs
* Control communication between segments using ACLs
* Host a secure web server in the DMZ
* Test connectivity between devices and services
* Apply real-world networking concepts in a practical scenario

---

## Testing

The following tests were performed:

* Device-to-device connectivity using `ping`
* Access to the DMZ web server via HTTP
* Verification of VLAN segmentation and routing behavior
* Confirmation that ACL rules correctly restrict unauthorized access

---

## 👨‍💻 Author

**João Filipe Macedo**
