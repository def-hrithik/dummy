# Computer Network Course – Short Notes

## 1. Cisco SONA Architecture 🌐
Cisco SONA (Service-Oriented Network Architecture) is a framework for building intelligent, flexible network infrastructures that align IT with business goals. SONA integrates networked applications, services, and infrastructure into a service-oriented architecture.
- **Three Main Layers:**  
  - **Network Infrastructure Layer:** Physical components (routers, switches, servers) for connectivity, security, and data transport (LAN, WAN, MAN).  
  - **Interactive Services Layer:** Intelligent services like security, mobility, QoS, and load balancing, making networks application-aware.  
  - **Application Layer:** Business applications (ERP, CRM) that use infrastructure services for efficiency and security.
- **Benefits:** Simplifies network management, improves performance, promotes modularity, scalability.

## 2. Classful and Classless IPv4 Addressing 🖥️
**Classful Addressing:** Divides IPv4 space into Classes A, B, C, D, E, with default network/host boundaries and subnet masks.
- **Class Ranges & Masks:**  
  - Class A: 1.0.0.0, Mask 255.0.0.0 (/8)  
  - Class B: 128.0.0.0, Mask 255.255.0.0 (/16)  
  - Class C: 192.0.0.0, Mask 255.255.255.0 (/24)  
- **Drawback:** Wastes addresses, lacks Variable-Length Subnet Mask (VLSM) support.

**Classless Addressing (CIDR/VLSM):** Prefix length (e.g., /20) explicitly specified for efficient allocation.
- Address in format a.b.c.d/n, using VLSM for flexibility, reduced wastage, route summarization.

## 3. Cisco PPDIOO Network Design Methodology ⚙️
Cisco’s PPDIOO lifecycle:
- **Prepare:** Define organizational requirements, strategies, risk.  
- **Plan:** Project management, high/low-level designs, implementation plan.  
- **Design:** Network topology, device selection, technical specs.  
- **Implement:** Build/integrate/test the network per design.
- **Operate:** Day-to-day monitoring, maintenance, management.
- **Optimize:** Continuous improvement, upgrades, feedback-based changes.

## 4. Link State Routing 🗺️
Link State Routing is dynamic; routers build a map of the entire network.
- Routers recognize neighbors, measure link costs.
- Each creates a Link-State Packet (LSP), floods to all routers.
- Routers store LSPs in databases, run Dijkstra's algorithm to compute shortest paths.
- Updates on change only, faster network convergence, avoids loops.
- Examples: OSPF, IS-IS.

## 5. OSI Reference Model 🧱
OSI’s 7 conceptual layers standardize network communications:
- **Application (7):** End-user services (HTTP, FTP, DNS).
- **Presentation (6):** Data translation, encryption/decryption (SSL/TLS, JPEG).
- **Session (5):** Session establishment, maintenance, termination (NetBIOS, RPC).
- **Transport (4):** Reliable process-to-process delivery (TCP, UDP).
- **Network (3):** Logical addressing, routing (IP, ICMP).
- **Data Link (2):** Node-to-node reliability, frames, MAC addressing (Ethernet, PPP).
- **Physical (1):** Raw bit stream transmission (cables, connectors, hubs).

## 6. TCP/IP Reference Model and Comparison with OSI ⚖️
**TCP/IP Model:** Four layers—Application, Transport, Internet, Network Access—basis of the Internet.
- Application Layer combines OSI's Application, Presentation, Session.
- Transport Layer ensures reliable/unreliable delivery (TCP/UDP).
- Internet Layer manages logical addressing/routing via IP.
- Network Access handles data transmission/hardware addressing.

**Comparison Table:**
| Feature             | OSI (7 Layers)                                  | TCP/IP (4 Layers)                      |
|---------------------|------------------------------------------------|----------------------------------------|
| Development         | Theoretical reference model                     | Practical implementation               |
| Layer Structure     | 7 distinct layers                               | 4 layers; top 3 combined into one      |
| Protocol Dependency | Protocol-independent                            | TCP/IP, UDP based                      |
| Error Handling      | Data Link & Transport layers                    | Mostly Transport layer (TCP)           |
| Usage               | Reference for network design                    | Basis for Internet communications      |

## 7. IPv4 Header Format 📦
Header size: 20–60 bytes.
- Key fields: Version (4 bits), Header Length (4 bits), Total Length (16 bits), Identification (16 bits), Flags (3 bits), Fragment Offset (13 bits), TTL (8 bits), Protocol (8 bits), Header Checksum (16 bits), Source/Destination IP (32 bits), Options (variable, with padding).

## 8. Distance Vector Routing Algorithm ➡️
Dynamic routing using Bellman-Ford algorithm:
- Routers maintain distance-to-destination tables, periodically share with neighbors.
- Update via \( D_x(y) = \min_v \{C(x, v) + D_v(y)\} \).
- Converges over time but can have “count-to-infinity” issues; split horizon helps.

## 9. Sliding Window Protocol using Go-Back-N (GBN) 🪟
- Sender can send N frames before needing ACK (window size N).
- Receiver accepts only next expected frame (window size 1).
- Cumulative ACK for last in-order frame; on error, sender retransmits lost/all subsequent frames (“Go-Back-N”).
- Efficiency: \( \text{Efficiency} = \frac{N}{1+2a} \) (\(a = \frac{T_p}{T_t}\)).

## 10. TCP Header and 3-Way Handshake 🤝
**TCP Header:** 20–60 bytes (ports, seq & ack numbers, flags, window, checksum).
**3-Way Handshake:**
- Client sends SYN (seq=x)
- Server replies SYN-ACK (ack=x+1, seq=y)
- Client replies ACK (ack=y+1)
- Connection established.

## 11. Cisco Three-Layer Hierarchical Model 🏗️
- Access Layer: User access, resource sharing, switches/hubs.
- Distribution Layer: Routing, filtering, policy-based security, Layer-3 switches/routers.
- Core Layer: High-speed backbone linking distribution layers; redundancy.

## 12. Channel Allocation Problem and CSMA/CD 📡
**Channel Allocation:**
- Static: Fixed (FDM), best for small static networks.
- Dynamic: Central or distributed allocation, channels on demand.
**CSMA/CD:**
- Listen before send, transmit only if idle.
- Collisions detected during transmission, jam signal sent, random backoff, retry.
- Not effective for wireless networks.

## 13. Domain Name System (DNS) 🏷️
DNS translates human-readable names to numeric IP addresses.
- Components: Resolver, Root DNS, TLD server, Authoritative server, Local cache.
- Hierarchical, distributed lookup process.

## 14. Network Topologies 🔗
Topology defines physical/logical arrangement of devices.
- Physical: Cables/devices layout. Logical: Data paths.
- **Types:**  
  - Point-to-Point: Direct between two nodes.
  - Mesh: Every device interlinked (expensive but reliable).
  - Star: All connected to central hub (single point of failure).
  - Bus: Shared backbone cable (simple but one cable failure = network down).
  - Ring: Each connects to two neighbors, data circulates.

## 15. Routing and Desirable Characteristics of Routing Algorithms 🧭
Routing: Choosing paths for packet delivery.
- Characteristics: Correctness (loop-free), Optimality (efficient), Simplicity, Robustness (failure-resilient), Stability (no frequent changes), Efficiency, Adaptability (quick to changes), Fairness.

## 16. Guided Transmission Media 🧵
Physical paths for signals (cables).
- **Twisted Pair:** Two insulated wires twisted. UTP (unshielded), STP (shielded).
- **Coaxial:** Central conductor, insulation, shield, outer cover. Used in TV, durable.
- **Optical Fiber:** Light through glass core; high capacity, immune to interference, expensive.

## 17. Design Issues in Data Link Layer 🖼️
- Services: Unacknowledged, acknowledged connectionless, acknowledged connection-oriented.
- Framing: Splits data into frames, start/end markers.
- Flow Control: Keeps sender from overwhelming receiver.
- Error Control: Detects/corrects mistakes.
- Physical Addressing: Adds MAC (hardware) addresses in frames.

## 18. Subnetting and Default Subnet Masks 🧮
Subnetting: Divides IP networks for better management/security.
- **Purpose:** Efficient use, reduced congestion, improved security.
- **Subnet mask:** 32-bit number distinguishing network/host bits.
- **Default subnet masks:**

| Class  | IP Address Range                 | Default Subnet Mask     | CIDR Notation |
|--------|----------------------------------|------------------------|---------------|
| A      | 1.0.0.0 to 126.0.0.0             | 255.0.0.0              | /8            |
| B      | 128.0.0.0 to 191.255.0.0         | 255.255.0.0            | /16           |
| C      | 192.0.0.0 to 223.255.255.0       | 255.255.255.0          | /24           |
| D      | 224.0.0.0 to 239.255.255.255     | N/A (Multicast)        | N/A           |
| E      | 240.0.0.0 to 255.255.255.255     | N/A (Reserved)         | N/A           |

## 19. Wireless Transmission and Standards 📡
Wireless transmits without physical medium using electromagnetic waves (radio, microwave, infrared).
- **Standards:** IEEE 802.11 (Wi-Fi), Bluetooth, Zigbee.
- **Features:** Mobility, easy install, but susceptible to interference, security issues.

## 20. Network Security Basics 🔐
Protection of data, resources from unauthorized access.
- **Core Concepts:** Confidentiality, Integrity, Availability (CIA).
- **Mechanisms:** Firewalls, encryption, authentication, intrusion prevention.
- **Threats:** Malware, DoS attacks, data interception.

## 21. Virtual LAN (VLAN) 🖧
VLAN divides a physical LAN into multiple logical LANs for better control, efficiency.
- **VLAN tag/ID:** Identifies VLAN for each frame.
- **Benefits:** Isolates traffic, simplifies management, enhances security.

## 22. Network Address Translation (NAT) 🔄
NAT maps private IP addresses to a public address for Internet access.
- **Types:** Static NAT (one-to-one), Dynamic NAT (pool mapping), Port Address Translation (PAT - many-to-one).
- **Benefits:** Conserves addresses, hides internal network.

## 23. IPv6 Addressing and Header Format 🚀
IPv6 provides vast address space (128 bits), simplifies header for efficiency.
- **Header Fields:** Version, Traffic Class, Flow Label, Payload Length, Next Header, Hop Limit, Source/Destination Address (fixed 40 bytes).
- **Features:** Auto-configuration, improved security, no fragmentation, supports mobility.

