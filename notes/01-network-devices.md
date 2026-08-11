# Network Devices - Introduction

## Summary
This note lesson serves as the foundation for the entire CCNA (Cisco Certified Network Associate) 200-301 course. The course is completely free and covers everything on the official Cisco exam topics list, though it is also includes extra context to help build general networking intuition. You do need any prior background in networking, IT, or programming to get started; the only requirement is a basic familiarity with computers.

To study effectively, Jeremy recommends using three primary resources alongside the lectures:
- **End-of-video quizzes** to practice Cisco-style exam questions.
- **Packet Tracer practice labs** to get hands-on experience with Cisco's network simulation software.
- **Anki flashcards** to help memorize technical details. For efficiency, Jeremy suggests creating one central "CCNA" deck and transferring new cards into it, rather than keeping dozens of separate mini-decks.
## Key Concepts
### What is a [[Network]]?
Academic definition can sometimes feel overly complicated. For example, Wikipedia defines a computer network as a digital telecommunications network that allows nodes to share resources.

To make this easier to understand, Jeremy explains that a network is 

### End Hosts: Client & Server
- **Client**: a device that accesses a service made available by a server.
- **Server**: a device that provides functions or services for clients.
- The same device can act as a client in one situation and a server in another. For example, in an AirDrop transfer, the sending iPhone acts as the server and the receiving iPhone acts as the client.

### Network Devices

#### Switch
<img src="./assets/01-network-devices/switch.png" alt="" width=300>

- Connects end hosts (PCs, servers, printers, etc.) within the same **LAN (Local Area Network)**.
- Has many interfaces/ports, typically 24 or more.
- Cannot provide connectivity between different LANs or to the Internet.
- Example models: Cisco Catalyst 9200, 3650.

#### Router
![router](./assets/01-network-devices/router.png)
- Provides connectivity **between LANs** and forwards traffic to and from the Internet.
- Has fewer interfaces compared to switches.
- Example models: Cisco ISR 900, 1000, 4000 series.

#### Firewall
![firewall](./assets/01-network-devices/firewall.png)
- A security device that monitors and controls traffic entering and exiting a network based on configured rules.
- Can be placed **outside** the router, facing the Internet, or **inside** the network, facing end hosts, or both.
- **Network firewall**: hardware appliance that filters traffic between networks (the focus of this course).
- **Host-based firewall**: software running on an individual end host, such as the built-in firewall on a PC.
- **Next-generation firewall (NGFW)**: combines traditional firewall filtering with advanced features such as IPS (Intrusion Prevention System). Example models: Cisco ASA 5500-X, Firepower 2100.

### Device Categories
- **Network devices** (manage and direct traffic): switch, router, firewall.
- **End hosts / endpoints** (exchange data with each other): server, client.

### Quick Comparison

| Device | Primary Function | Number of Interfaces |
|---|---|---|
| Switch | Connect hosts within a single LAN | Many (24+) |
| Router | Connect LANs and forward to the Internet | Few |
| Firewall | Filter inbound and outbound traffic | Varies |

## Example Data Flow (Branch-to-Branch)
![Example Dataflow](./assets/01-network-devices/01-example-dataflow.png)

## Personal Notes
This lesson introduces five foundational node types: 3 network devices (switch, router, firewall) that manage and direct traffic, and 2 end hosts (server, client) that exchange data with each other. This is not an exhaustive list, since additional device types, such as access points and load balancers, will be covered later in the course.

## References
- Jeremy's IT Lab: [Network Devices - Introduction](https://youtu.be/H8W9oMNSuwo?si=il1AoiYuEDuoPdFW)