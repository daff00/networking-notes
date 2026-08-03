# Network Devices - Introduction

## Summary
This is the introductory lesson of the CCNA 200-301 course, laying the foundation for the rest of the material. It defines what a computer network is (a system that allows nodes to share resources) and introduces the basic building blocks of a network: switches, routers, firewalls, servers, and clients. Using simple diagrams (two PCs connected by a cable, an enterprise network spanning two branch offices), the lesson shows how these devices work together to let end hosts communicate locally and across the Internet.

## Key Concepts

### Client & Server
- **Client**: a device that accesses a service made available by a server.
- **Server**: a device that provides functions or services for clients.
- The same device can act as a client in one situation and a server in another (e.g., in an AirDrop transfer, the sending iPhone is the server and the receiving iPhone is the client).

### Switch
- Connects end hosts (PCs, servers, printers, etc.) within the same **LAN (Local Area Network)**.
- Has many interfaces/ports, typically 24 or more.
- Cannot provide connectivity between different LANs or to the Internet.
- Example models: Cisco Catalyst 9200, 3650.

### Router
- Provides connectivity **between LANs** and forwards traffic to/from the Internet.
- Has fewer interfaces compared to switches.
- Example models: Cisco ISR 900, 1000, 4000 series.

### Firewall
- A security device that monitors and controls traffic entering/exiting a network based on configured rules.
- Can be placed **outside** the router (facing the Internet) or **inside** the network (facing end hosts) — or both.
- **Network firewall**: hardware appliance that filters traffic between networks (the focus of this course).
- **Host-based firewall**: software running on an individual end host (e.g., the built-in firewall on a PC).
- **Next-generation firewall (NGFW)**: combines traditional firewall filtering with advanced features such as IPS (Intrusion Prevention System). Example models: Cisco ASA 5500-X, Firepower 2100.

### Device Categories
- **Network devices** (manage/direct traffic): switch, router, firewall.
- **End hosts / endpoints** (exchange data with each other): server, client.

### Quick Comparison

| Device | Primary Function | Number of Interfaces |
|---|---|---|
| Switch | Connect hosts within a single LAN | Many (24+) |
| Router | Connect LANs / forward to the Internet | Few |
| Firewall | Filter inbound/outbound traffic | Varies |

### Example Data Flow (Branch-to-Branch)
![Example Dataflow](./notes/assets/01-network-devices/01-example-dataflow.png)

## Personal Notes
There are 5 foundational nodes in a network: 3 network devices (switch, router, firewall) that manage and direct traffic, and 2 end hosts (server, client) that exchange data with each other. This is not an exhaustive list — additional device types (e.g., access points, load balancers) will be covered later in the course.

## References
- Jeremy's It Lab: https://youtu.be/H8W9oMNSuwo?si=il1AoiYuEDuoPdFW