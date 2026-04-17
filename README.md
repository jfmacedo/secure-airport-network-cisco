# Secure Airport Network (Cisco Packet Tracer)

This project simulates a secure and segmented airport network using Cisco Packet Tracer.  
The network was designed to separate different areas of access through VLANs and includes a DMZ for public services.

## Project Overview
The topology was built to demonstrate fundamental network security and segmentation concepts in a realistic airport scenario.  
Different user groups and services are isolated into separate VLANs to improve organization, security, and traffic management.

## Features
- VLAN segmentation for different airport zones:
  - **Authority**
  - **Guest**
  - **DMZ**
- Trunk links between switches
- Inter-VLAN routing
- Web server deployed in the DMZ
- Connectivity testing using:
  - `ping`
  - `HTTP`

## Technologies Used
- Cisco Packet Tracer
- VLAN configuration
- Trunking
- Inter-VLAN Routing
- Basic network security concepts
- DMZ deployment

## Network Segments
- **Authority VLAN**: Internal trusted devices
- **Guest VLAN**: Visitor/public access devices
- **DMZ VLAN**: Public-facing server zone

## Objectives
- Separate network traffic using VLANs
- Allow controlled communication between segments
- Host a web server in the DMZ
- Test connectivity between devices and services
- Practice Cisco networking fundamentals in a real-world style project

## Testing
The following tests were performed:
- Device-to-device connectivity with `ping`
- Access to the DMZ web server through HTTP
- Verification of VLAN segmentation and routing behavior

## Author
**João Filipe Macedo**