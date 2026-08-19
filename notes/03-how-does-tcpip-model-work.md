## Summary
The Internet Protocol Suite (commonly known as TCP/IP) is the universal family of rules that makes communication over the Internet and modern computer networks possible. Instead of treating networking as one single, massive process, TCP/IP divides communication into distinct, manageable layers. Each layer has a highly specialized responsibility and provides services to the layer directly above it while relying on the services of the layer directly below it. This modular architecture makes modern networks scalable and interoperable, allowing devices from completely different vendors to communicate seamlessly because they implement the same open standards.

---
## Key Concepts
### The Importance of Protocols and Standards
In network engineering, we rely on established rules to make communication possible. 
- **[[Protocol]]:** A set of rules that define how devices communicate over a network. Protocols are essentially the languages that computers use to talk. Computer using different protocols cannot exchange data.
- **[[Standard]]:** An agreed specification describing how a protocol or technology should work. When manufacturers follow these open, vendor-neutral standards, devices of all types can work together on the same network.
---
### A Brief History of TCP/IP
Understanding how the modern Internet came to be helps clarify why we use these specific rules today.
- **The Early Days (ARPANET):** Funded by the US Department of Defense, the ARPANET came online in 1969 to connect massive mainframe computers (powerful, centralized computers used by large organizations) at universities and laboratories. It originally used a rule set called the Network Control Program (NCP).
- **The Development of TCP:** In 1974, Vint Cerf and Bob Kahn began developing the Transmission Control Program. This program was later split into two separate protocols that we still use today: the Transmission Control Protocol (TCP) and the Internet Protocol (IP).
- **The Great Transition:** The ARPANET officially switched over to TCP/IP on January 1, 1983. Because TCP/IP was published as a set of open standards that any company could implement, and because it could run over many different types of networks, it quickly became the dominant global standard over competing vendor-owned options.
---
### Standards Organizations
Most network standards are created by independent organizations rather than a single manufacturer, allowing engineers from different companies to collaborate. Two of the most important groups are:
- **IEEE (Institute of Electrical and Electronics Engineers)** 
  - Defines physical transmission and local network technologies (physical cable types, wireless radio frequencies, and how signals are sent over physical mediums).
  - Known for: Standardizing Ethernet (IEEE 802.3) and Wi-Fi (IEEE 802.11)
  - Defines physical transmission and local network technologies.
- **IETF (Internet Engineering Task Force)** 
  - Defines core Internet protocols.
  - Publishes standards as **RFC (Request for Comments)** documents.
  - Examples:
    - IP
    - TCP
    - UDP
    - HTTP
    - DNS

---
### The Postal Mail Analogy
To understand how network layers work without getting lost in technical jargon, Jeremy uses the analogy of mailing a physical letter to a friend.

Imagine writing a letter addressed to your friend, Bob. You put the letter in an envelope, write his home address on the front, and drive it to your local post office. The post office loads your envelope into a truck and drives it to a sorting center, which then ships it to Bob's local post office. From there, a mail carrier delivers the envelope to Bob's house, where he opens it and reads your message.

This simple physical mail system maps beautifully to the five layers of the TCP/IP network model:
<center><img src="./assets/03-tcp-ip-model/mail-analogy.png" width="300" /></center>
- **The Letter Content:** This represents the **Application Layer** (Layer 5), which is the actual data you want to convey.
- **The Recipient (To: Bob):** This represents the **Transport Layer** (Layer 4), which identifies exactly which person (or software process) inside the destination house should receive the message.
- **The House Address:** This represents the **Internet Layer** (Layer 3), which is the permanent, unique end-to-end destination of the building (or host computer).
- **The Vehicles (Cars, Trucks, or Planes):** This represents the **Local Network Layer** (Layer 2), which physically moves the envelope from one specific point (or hop) to the next along the journey.
- **The Roads and Flight Paths:** This represents the **Physical Layer** (Layer 1), which is the physical infrastructure that the vehicles travel on.

**Why this analogy matters:** Just like in the mail system, what happens inside one layer does not disrupt the others. If you change the contents of your letter, the postal carrier does not have to change their driving route. Similarly, if the post office upgrades their delivery trucks to airplanes, the content of your letter remains completely unaffected. This independence is the core benefit of a modular, layered network.

--- 
### TCP/IP Five-Layer Model
In this course, we use a five-layer model to map out how networks operate. 

| Layer | Name                                                                   |
| ----- | ---------------------------------------------------------------------- |
| 5     | [[Application Layer\|Application Layer]]                               |
| 4     | [[Networking/knowledge-base/Transport Layer\|Transport Layer]]         |
| 3     | [[Networking/knowledge-base/Internet Layer\|Internet Layer]]           |
| 2     | [[Networking/knowledge-base/Local Network Layer\|Local Network Layer]] |
| 1     | [[Networking/knowledge-base/Physical Layer\|Physical Layer]]           |

---
### Layer Responsibilities

| Layer         | Responsible For                  | Uses                 |
| ------------- | -------------------------------- | -------------------- |
| Application   | Application communication        | HTTP, DNS, FTP       |
| Transport     | Process-to-process communication | TCP, UDP, Ports      |
| Internet      | Host-to-host communication       | IP, Routers          |
| Local Network | Hop-to-hop communication         | Ethernet, Wi-Fi, MAC |
| Physical      | Signal transmission              | Cables, Fiber, Radio |

---
### [[Networking/knowledge-base/Encapsulation|Encapsulation]]
To understand how a single message contains all of this layered information, we look at how data is packaged and unpackaged. 
#### Encapsulation (Sending Data)
As a message moves down the network stack on the sending device, each layer wraps the data in a **header** containing the address and control information needed for that layer.
1. **Application Data (Layer 5):** The software application prepares the raw message, like an HTTP web request. 
2. **Transport Header (Layer 4):** The Transport Layer wraps the application data with a header containing source and destination port numbers. 
3. **Internet Header (layer 3):** The internet layer wraps the transport segment with a header containing source and destination IP addresses.
4. **Local Network Header + Trailer (Layer 2):** The Local Network layer wraps the packet with a header containing local MAC addresses, and it also adds a **trailer** at the end. The receving device uses this trailer to run checks and detect if any transmission errors occured on the cable. 
5. **Physical Signals (Layer 1):** The physical layer takes the completed frame and transmits its bits as physical signals across the medium.
### [[Networking/knowledge-base/Decapsulation|Decapsulation]]
The receiving host processes the incoming stream of bits by reversing the encapsulation steps, moving up the network stack:
1. The Physical layer receives the raw bits and passes them up.
2. The Local Network layer reads the Layer 2 header and trailer to verify the local address and check for errors, then strips them off.
3. The Internet layer reads the Layer 3 header to verify the IP address, then strips it off.
4. The Transport layer reads the Layer 4 header to find the correct port number, then strips it off.
5. The raw application data is delivered directly to the target software process.

---

### Layer Interaction

#### Adjacent-Layer Interaction
Each layer:
- Uses services from the layer below.
- Provides services to the layer above.

Example:
- Layer 3 relies on Layer 2.
- Layer 4 relies on Layer 3.

---

#### Same-Layer Interaction
Equivalent layers communicate logically.

Examples:
- HTTP to HTTP
- TCP to TCP
- IP to IP
- Ethernet to Ethernet

---

### Benefits of Layering

- Separation of responsibilities
- Easier troubleshooting
- Vendor interoperability
- Modular protocol replacement
- Scalability
- Easier protocol development

Example:
- HTTP can be replaced with FTP without changing IP or Ethernet.
- Ethernet can be replaced with Wi-Fi without affecting TCP or HTTP.

---

### TCP/IP vs OSI Model

| TCP/IP (5 Layer) | OSI (7 Layer) |
|------------------|---------------|
| Application | Application |
| Application | Presentation |
| Application | Session |
| Transport | Transport |
| Internet | Network |
| Local Network | Data Link |
| Physical | Physical |

Notes:
- TCP/IP is the protocol suite used in real networks.
- OSI is mainly a conceptual reference model.
- Many networking resources still refer to layers using OSI numbering (e.g., Layer 2, Layer 3, Layer 7).

---

### Important Protocols by Layer

| Layer | Common Protocols |
|--------|------------------|
| Application | HTTP, HTTPS, DNS, FTP, TFTP |
| Transport | TCP, UDP |
| Internet | IPv4, IPv6, ICMP |
| Local Network | Ethernet, Wi-Fi |
| Physical | Copper, Fiber, Radio |

---

### Exam Focus (CCNA)

Know:
- The purpose of each TCP/IP layer.
- Encapsulation and decapsulation.
- PDU names (Segment, Datagram, Packet, Frame).
- Difference between hop-to-hop and end-to-end communication.
- MAC addresses vs IP addresses vs Port numbers.
- Adjacent-layer interaction.
- Same-layer interaction.
- Basic differences between TCP/IP and OSI.

---

## Personal Notes
- Think of networking as a **delivery service**, where each layer handles one responsibility.
- Remember the addressing hierarchy:
  - **Port Number leads to Application/Process**
  - **IP Address leads to Host**
  - **MAC Address leads to Next Hop**
- Routers mainly operate at **Layer 3 (Internet)**.
- Switches mainly operate at **Layer 2 (Local Network)**.
- Physical devices transmit **bits**, not packets or frames.
- Focus on understanding the responsibilities of each layer rather than memorizing every protocol immediately.
- A useful memory flow:
  - **Application leads to Process**
  - **Transport leads to Ports**
  - **Internet leads to IP**
  - **Local Network leads to MAC**
  - **Physical leads to Bits**

## References
- Jeremy's IT Lab: [How the TCP/IP Model Actually Works | CCNA Day 3](https://youtu.be/yM-XNq9ADlI?si=pC_pcz3AbsZqwqQx)