![](Networking/notes/assets/01-network-devices/firewall.png)

- **Primary Purpose:** A firewall is a dedicated security device designed to protect your network by monitoring and controlling traffic entering and exiting the network based on strict security rules.
- **Why They Are Vital:** Routers only provide very basic security features. Because of the constant threat of attackers on the Internet trying to steal information or damage corporate assets, networks require dedicated firewalls to drop unauthorized traffic while letting safe business data pass through.	- **Placement:** Firewalls are highly flexible. They can be placed "outside" the router (facing the raw Internet) or "inside" the network (facing your local devices), and sometimes networks use both placements.
- **Network vs. Host-Based:**
	- _Network Firewall:_ A dedicated hardware appliance that filters traffic moving between entire networks (this is the primary focus of this CCNA course).
    - _Host-Based Firewall:_ A software program installed directly on a single computer (like Windows Defender) to serve as a localized, extra line of defense.
- **Next-Generation Firewalls (NGFW):** These are modern firewalls that combine traditional traffic filtering with advanced security systems, such as an IPS (Intrusion Prevention System) to stop active threats.
- **Example Models:** Cisco ASA 5500-X (Cisco's classic firewall platform that now supports modern NGFW features) and the Cisco Firepower 2100 series.