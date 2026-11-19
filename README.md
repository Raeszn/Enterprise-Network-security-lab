# Enterprise-Network-security-lab
Cisco Packet Tracer enterprise network featuring VLAN segmentation, inter VLAN routing, DHCP, ACLs and DMZ


Project Overview

This project demonstrates the design and configuration of a segmented enterprise network using Cisco Packet Tracer.

The lab simulates a company network with separate departments, controlled inter-department communication, DHCP services and an isolated Demilitarized Zone (DMZ) hosting a web server.

The project was built to develop practical networking and introductory network security skills.

Project Objectives

* Design an enterprise network topology.
* Implement VLAN-based network segmentation.
* Configure inter-VLAN routing using router-on-a-stick.
* Configure DHCP for automatic IP allocation.
* Implement extended Access Control Lists (ACLs).
* Create a separate DMZ network.
* Apply traffic restrictions between network segments.
* Test connectivity and verify security policies.

Network Devices

Device	Model	Quantity
Router	Cisco 2911	1
Switch	Cisco 2960	2
Desktop PCs	PC-PT	6
Internal Server	Server-PT	1
DMZ Server	Server-PT	1

Network Segmentation

Department	VLAN	Network	Default Gateway
Administration	10	192.168.10.0/24	192.168.10.1
IT	20	192.168.20.0/24	192.168.20.1
Finance	30	192.168.30.0/24	192.168.30.1
Internal Servers	40	192.168.40.0/24	192.168.40.1
DMZ	50	192.168.50.0/24	192.168.50.1

Technologies and Concepts

* Cisco Packet Tracer
* VLAN configuration
* 802.1Q trunking
* Router-on-a-stick
* DHCP
* IPv4 addressing and subnetting
* Extended ACLs
* Network segmentation
* DMZ architecture
* HTTP server configuration
* Network troubleshooting

Security Implementation

1. Departmental Access Control

Extended ACLs were configured to restrict communication between Administration and Finance while allowing the intended access to IT.

2. DMZ Isolation

A separate DMZ network was created using VLAN 50.

The DMZ server was assigned:

* IP address: 192.168.50.10
* Subnet mask: 255.255.255.0
* Default gateway: 192.168.50.1

An extended ACL named DMZ-IN was configured on the router’s DMZ subinterface to restrict traffic from the DMZ to internal networks.

TCP rules using the established keyword were included for HTTP and HTTPS response traffic.

Security limitation: These ACLs provide stateless packet filtering. They are not a replacement for a dedicated stateful firewall.

Testing and Verification

The following tests were performed:

Test	Result
PC1 to Administration gateway	Successful
PC1 to IT gateway	Successful
PC1 to Finance gateway before ACL restrictions	Successful
PC1 to Finance after ACL restrictions	Blocked
IT to Finance	Successful
Finance to its default gateway	Successful
DMZ server to DMZ gateway	Successful
PC1 accessing DMZ website	Successful
DMZ server pinging Administration	Blocked
DMZ server pinging Finance	Blocked

ACL counters were also inspected using:

show access-lists DMZ-IN

Configuration Verification Commands

The following commands were used during configuration and troubleshooting:

show vlan brief
show interfaces trunk
show ip interface brief
show ip route
show access-lists
show running-config

Skills Developed

Through this project, I gained practical experience with:

* Configuring Cisco routers and switches.
* Creating and assigning VLANs.
* Configuring trunk links.
* Implementing inter-VLAN routing.
* Configuring DHCP pools.
* Writing and applying extended ACLs.
* Understanding network segmentation and DMZ architecture.
* Testing network connectivity.
* Troubleshooting network configuration issues.

Future Improvements

Potential improvements include:

* Implementing a dedicated stateful firewall.
* Adding a more detailed DMZ security policy.
* Configuring secure management access using SSH.
* Implementing network monitoring and logging.
* Exploring intrusion detection and prevention.
* Documenting additional security testing.

Project Environment

Cisco Packet Tracer

Author

Independent hands-on networking and cybersecurity learning project.
