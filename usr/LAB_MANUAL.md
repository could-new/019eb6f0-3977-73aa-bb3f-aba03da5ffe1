# Computer Networks Lab Manual

## Table of Contents
1. [Lab 1: Introduction to Networking (LAN, WAN, Components)](#lab-1-introduction-to-networking)
2. [Lab 2: Network Topologies (Bus, Star, Ring, Mesh)](#lab-2-network-topologies)
3. [Lab 3: OSI & TCP/IP Models](#lab-3-osi--tcpip-models)
4. [Lab 4: Physical Layer (Transmission Media)](#lab-4-physical-layer)
5. [Lab 5: Data Link Layer & MAC Addressing](#lab-5-data-link-layer--mac-addressing)
6. [Lab 6: Multiple Access Techniques (CSMA/CD, CSMA/CA)](#lab-6-multiple-access-techniques)
7. [Lab 7: Switching Techniques (Circuit & Packet Switching)](#lab-7-switching-techniques)
8. [Lab 8: LAN Technologies & VLANs](#lab-8-lan-technologies--vlans)
9. [Lab 9: Networking Devices (Router, Switch, Hub)](#lab-9-networking-devices)
10. [Lab 10: IP Addressing (IPv4 & IPv6)](#lab-10-ip-addressing)
11. [Lab 11: Subnetting & CIDR](#lab-11-subnetting--cidr)
12. [Lab 12: Routing (Static Routing)](#lab-12-routing-static)
13. [Lab 13: Routing Protocols (RIP, OSPF)](#lab-13-routing-protocols)
14. [Lab 14: Transport Layer (TCP, UDP, Ports)](#lab-14-transport-layer)
15. [Lab 15: Flow & Congestion Control](#lab-15-flow--congestion-control)
16. [Lab 16: Application Layer Protocols (HTTP, FTP, DNS)](#lab-16-application-layer)
17. [Lab 17: Wireless Networks & IoT](#lab-17-wireless-networks--iot)
18. [Lab 18: Final Project (Network Design)](#lab-18-final-project)

---

## Lab 1: Introduction to Networking
**Objective:** Install Packet Tracer, identify networking devices, create basic topology.

**Procedure:**
1. Download and install Cisco Packet Tracer.
2. Open the application and explore the device palettes (Routers, Switches, End Devices).
3. Drag two PCs and one Switch to the workspace.
4. Use a Copper Straight-Through cable to connect the PCs to the Switch.

![Basic Topology](https://via.placeholder.com/600x300?text=Basic+Topology+Diagram)

---

## Lab 2: Network Topologies
**Objective:** Design and compare Bus, Star, Ring, and Mesh topologies.

**Procedure:**
1. **Star Topology:** Connect multiple PCs to a central Switch.
2. **Bus Topology:** Use a central backbone cable (represented by interconnected hubs or switches) to connect devices.
3. **Ring Topology:** Connect devices in a closed loop.
4. **Mesh Topology:** Connect every device to every other device. Observe the redundancy.

![Network Topologies](https://via.placeholder.com/600x300?text=Network+Topologies+(Star,+Mesh,+Ring))

---

## Lab 3: OSI & TCP/IP Models
**Objective:** Map protocols to layers, simulate data flow.

**Procedure:**
1. Open Simulation Mode in Packet Tracer.
2. Send a simple PDU (Ping) between two connected PCs.
3. Click on the captured packet to examine the OSI Model tab. Observe the encapsulation process from Layer 7 down to Layer 1.

![OSI Model Encapsulation](https://via.placeholder.com/600x300?text=OSI+Model+Simulation+Panel)

---

## Lab 4: Physical Layer (Transmission Media)
**Objective:** Identify cables, simulate physical connections.

**Procedure:**
1. Identify the difference between Copper Straight-Through (different devices) and Copper Cross-Over (similar devices) cables.
2. Connect two PCs directly using a Cross-Over cable.
3. Connect a PC and a Switch using a Straight-Through cable.
4. Examine Fiber Optic connections between two routers.

![Cabling Types](https://via.placeholder.com/600x300?text=Straight-Through+vs+Crossover+Cables)

---

## Lab 5: Data Link Layer & MAC Addressing
**Objective:** View MAC address using commands, simulate frame transmission.

**Procedure:**
1. On a PC in Packet Tracer, open the Command Prompt.
2. Run `ipconfig /all` to view the Physical Address (MAC Address).
3. In Simulation Mode, send a packet and inspect the Layer 2 Ethernet frame headers to see Source and Destination MAC addresses.

![MAC Address Inspection](https://via.placeholder.com/600x300?text=Command+Prompt+ipconfig+/all)

---

## Lab 6: Multiple Access Techniques (CSMA/CD, CSMA/CA)
**Objective:** Simulate collision detection scenarios.

**Procedure:**
1. Create a topology using a **Hub** connecting multiple PCs (Hubs broadcast to all ports, creating a single collision domain).
2. Attempt to ping simultaneously from multiple PCs in Simulation Mode.
3. Observe the collisions (fire icon in Packet Tracer) and the resulting CSMA/CD backoff algorithm action.

![Collision Simulation](https://via.placeholder.com/600x300?text=Packet+Collision+on+Hub)

---

## Lab 7: Switching Techniques (Circuit & Packet Switching)
**Objective:** Analyze packet switching performance.

**Procedure:**
1. Set up a topology with multiple switches.
2. Send packets from End Device A to End Device B.
3. Observe how switches populate their MAC Address Tables to efficiently switch packets, unlike hubs that broadcast.

![Packet Switching](https://via.placeholder.com/600x300?text=Switch+MAC+Address+Table)

---

## Lab 8: LAN Technologies & VLANs
**Objective:** Configure LAN, create and test VLANs.

**Procedure:**
1. Connect 4 PCs to a Switch.
2. Assign PC1 and PC2 to VLAN 10 (Sales), PC3 and PC4 to VLAN 20 (Marketing).
3. CLI Commands:
   ```text
   Switch> enable
   Switch# configure terminal
   Switch(config)# vlan 10
   Switch(config-vlan)# name Sales
   Switch(config)# interface range fa0/1-2
   Switch(config-if-range)# switchport access vlan 10
   ```
4. Verify that PCs in different VLANs cannot ping each other without a router.

![VLAN Configuration](https://via.placeholder.com/600x300?text=VLAN+Segmentation+Diagram)

---

## Lab 9: Networking Devices (Router, Switch, Hub)
**Objective:** Configure basic router settings.

**Procedure:**
1. Connect to a Router via Console cable from a PC.
2. Configure basic settings:
   ```text
   Router> enable
   Router# configure terminal
   Router(config)# hostname R1
   R1(config)# enable secret cisco
   R1(config)# interface gig0/0/0
   R1(config-if)# ip address 192.168.1.1 255.255.255.0
   R1(config-if)# no shutdown
   ```

![Router CLI](https://via.placeholder.com/600x300?text=Router+CLI+Configuration)

---

## Lab 10: IP Addressing (IPv4 & IPv6)
**Objective:** Assign IP addresses, test connectivity using ping.

**Procedure:**
1. Go to PC Desktop -> IP Configuration.
2. Assign IPv4: `192.168.1.10`, Subnet: `255.255.255.0`.
3. Assign IPv6: `2001:DB8:ACAD:1::10/64`.
4. Open Command Prompt and test connectivity: `ping 192.168.1.11` and `ping 2001:DB8:ACAD:1::11`.

![IP Configuration](https://via.placeholder.com/600x300?text=IPv4+and+IPv6+Configuration+Window)

---

## Lab 11: Subnetting & CIDR
**Objective:** Perform subnetting calculations, configure subnets.

**Procedure:**
1. Given network `192.168.1.0/24`, subnet it to support 4 networks (requires borrowing 2 bits -> `/26`).
2. Subnets: `192.168.1.0/26`, `192.168.1.64/26`, `192.168.1.128/26`, `192.168.1.192/26`.
3. Configure these subnets on different router interfaces and verify connectivity.

![Subnetting Table](https://via.placeholder.com/600x300?text=Subnetting+Calculation+Table)

---

## Lab 12: Routing (Static Routing)
**Objective:** Configure static routing between networks.

**Procedure:**
1. Connect Router 1 and Router 2. Connect different LANs to each router.
2. On Router 1, configure a route to Router 2's LAN:
   ```text
   R1(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2
   ```
3. Test end-to-end ping across the routers.

![Static Routing](https://via.placeholder.com/600x300?text=Static+Routing+Topology)

---

## Lab 13: Routing Protocols (RIP, OSPF)
**Objective:** Configure RIP, verify routing tables.

**Procedure:**
1. Remove static routes. Configure RIPv2:
   ```text
   R1(config)# router rip
   R1(config-router)# version 2
   R1(config-router)# network 192.168.1.0
   R1(config-router)# network 10.0.0.0
   ```
2. Run `show ip route` to verify RIP routes (marked with 'R').

![Routing Table](https://via.placeholder.com/600x300?text=Show+IP+Route+Output)

---

## Lab 14: Transport Layer (TCP, UDP, Ports)
**Objective:** Analyze connections using netstat, simulate TCP/UDP.

**Procedure:**
1. Open a Web Browser on a PC and access a server via HTTP.
2. Open PC Command Prompt and run `netstat`. Observe established TCP connections on Port 80.
3. In Simulation mode, observe the 3-way TCP handshake (SYN, SYN-ACK, ACK).

![Netstat Command](https://via.placeholder.com/600x300?text=Netstat+Output+Showing+TCP+Connections)

---

## Lab 15: Flow & Congestion Control
**Objective:** Simulate network traffic and congestion scenarios.

**Procedure:**
1. Create a bottleneck by routing traffic from a Gigabit link to an Ethernet (10 Mbps) link.
2. Use multiple PCs to generate traffic simultaneously towards a single server.
3. In Simulation mode, observe dropped packets and TCP window sliding/backoff behaviors.

![Congestion Control](https://via.placeholder.com/600x300?text=Packet+Drops+at+Bottleneck+Link)

---

## Lab 16: Application Layer Protocols (HTTP, FTP, DNS)
**Objective:** Simulate web server, FTP, and DNS resolution.

**Procedure:**
1. Add a Server device. Enable HTTP, FTP, and DNS services.
2. Add a DNS A-Record pointing `www.labtest.com` to the Server's IP.
3. On a PC, configure the DNS Server IP. Open the web browser and navigate to `www.labtest.com`.

![Application Protocols](https://via.placeholder.com/600x300?text=DNS+and+HTTP+Services+Config)

---

## Lab 17: Wireless Networks & IoT
**Objective:** Configure wireless network and connect devices.

**Procedure:**
1. Add a Wireless Router (Home Router).
2. Configure SSID and WPA2-PSK password in the Wireless GUI.
3. Add a Laptop and a Smartphone. Connect them to the SSID.
4. Add IoT devices (like a Smart Fan) and connect them to the wireless network.

![Wireless Topology](https://via.placeholder.com/600x300?text=Wireless+Router+and+IoT+Devices)

---

## Lab 18: Final Project (Network Design)
**Objective:** Design a complete network with IP scheme, routing, VLANs, and submit a report.

**Procedure:**
1. **Design:** Create a multi-department corporate network topology (e.g., HQ + Branch).
2. **IP Addressing:** Implement VLSM to assign IP blocks.
3. **Switching:** Implement VLANs (Sales, HR, IT) and Inter-VLAN routing.
4. **Routing:** Use OSPF to connect HQ and Branch routers.
5. **Services:** Deploy internal DNS and Web servers.
6. **Validation:** Ensure all PCs can ping the Web server and cross-branch PCs. 
7. **Report:** Document the topology, addressing scheme, and configurations.

![Final Project Topology](https://via.placeholder.com/600x300?text=Comprehensive+Final+Project+Topology)