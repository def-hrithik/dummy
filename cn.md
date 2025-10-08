# Computer Networks Notes

## Q1. Network Layer Primitives
Network layer primitives define the basic operations for communication at the network layer. The main primitives include:

- **SEND:** Initiates sending of data from the source to the destination network layer.
- **RECEIVE:** Collects incoming data at the destination.
- **CONNECT:** Establishes a logical path between source and destination before data transmission.
- **DISCONNECT:** Terminates the established connection after data transfer.

These primitives enable important functions like routing, addressing, and error handling in the network layer. They serve as building blocks for network protocols like IP.

---

## Q2. Link State Routing Algorithm, ARP, Distance Vector Routing, Classful and Classless Addressing

- **Link State Routing Algorithm:** Each router discovers its neighbors and learns the entire topology. It advertises its link state to all routers, which build a complete map and calculate shortest paths using algorithms like Dijkstra’s.

- **Address Resolution Protocol (ARP):** ARP translates an IP address to a MAC address on a local area network, enabling IP-based communication over Ethernet.

- **Distance Vector Routing:** Each router sends its routing table to its immediate neighbors. Routers update their tables based on neighbors' information using the Bellman-Ford algorithm.

- **Classful Addressing:** IP addresses are divided into classes (A, B, C) with predefined sizes and network/host bits.

- **Classless Addressing (CIDR):** Allows flexible division of IP addresses using variable-length subnet masks, improving IP address usage.

---

## Q3. IPv4 Header Format
The IPv4 header consists of several fields:

- **Version (4 bits):** Indicates IP version.
- **IHL (4 bits):** Header length.
- **Type of Service (8 bits):** Specifies priority.
- **Total Length (16 bits):** Size of packet.
- **Identification (16 bits):** Identifies fragments.
- **Flags (3 bits):** Controls fragmentation.
- **Fragment Offset (13 bits):** Specifies fragment position.
- **TTL (8 bits):** Lifespan of packet.
- **Protocol (8 bits):** Indicates protocol (TCP/UDP).
- **Header Checksum (16 bits):** Error checking.
- **Source IP (32 bits):** Sender’s IP.
- **Destination IP (32 bits):** Receiver’s IP.
- **Options (variable):** Optional settings.

This structure enables efficient packet delivery and fragmentation handling in IPv4 networks.

---

## Q4. TCP Three-Way Handshake
The TCP three-way handshake establishes a reliable connection:

1. **SYN:** Client sends SYN to server to start connection.
2. **SYN-ACK:** Server replies with SYN-ACK to acknowledge.
3. **ACK:** Client sends ACK to confirm connection.

Only after this handshake do both sides start data transfer, ensuring reliability and synchronization.

---

## Q5. Network Traffic Congestion and Control
Network traffic congestion occurs when too much data overloads the network, causing delays, packet loss, and reduced performance.

**Congestion control methods:**
- Buffer management: Dropping excess packets.
- Congestion avoidance algorithms: TCP uses slow start, congestion avoidance, fast retransmit, and fast recovery.
- Load balancing: Distributing traffic evenly.
- Quality of Service (QoS): Prioritizing critical traffic.

---

## Q6. TCP Segment Header and Importance of Sequencing
The TCP segment header contains sequence numbers that:

- Ensure data arrives in order.
- Handle lost or out-of-order packets.
- Enable reliable data transfer.

Sequence numbers are fundamental for applications like file transfer or web browsing.

---

## Q7. Comparison of IPv4 and IPv6

| Feature | IPv4 | IPv6 |
|----------|------|------|
| Address Size | 32-bit (4 bytes) | 128-bit (16 bytes) |
| Header Size | Variable | Fixed (40 bytes) |
| Address Format | Decimal, dot-separated | Hexadecimal, colon-separated |
| Security | Optional (IPSec) | Mandatory (IPSec) |
| Fragmentation | Sender & routers | Only sender |
| Broadcast | Supported | Not supported (uses multicast) |
| NAT Required | Yes | No |

---

## Q8. Link State Routing Example
Link State Routing works like this:

1. Each router measures the cost to its neighbors.
2. It sends out “link state packets” to all other routers.
3. All routers compile this data to create a full network map.
4. Using Dijkstra’s algorithm, each router calculates shortest paths.

**Example:** If routers A, B, C, D connect in a square, each exchanges link cost info; routers build identical tables and route packets via the most efficient path.

---

## Q9. SMTP (Simple Mail Transfer Protocol)
- Standard protocol for sending emails across networks.
- Works at the application layer.
- Uses TCP port 25 by default.
- Transfers mail from client to server and between servers.
- Not designed for mail retrieval (POP, IMAP do that).
- Defines commands for mail sending, forwarding, and delivery.

---

## Q10. Domain Name System (DNS)
**Need:** Humans prefer names (like www.example.com) over IP addresses.

**How DNS works:**
1. User enters website name.
2. DNS resolver contacts a root server.
3. Root points to TLD (top-level domain) server.
4. TLD points to authoritative server.
5. Authoritative server returns IP address.
6. Browser connects using that IP.

---

## Q11. Short Notes

- **TCP Timers:** Used for retransmission, connection setup, and closing (e.g., timeout, keepalive).
- **HTTP:** Hypertext Transfer Protocol for web pages, uses TCP port 80.
- **Telnet:** Remote login protocol, uses TCP port 23 (not secure).
- **FTP:** File Transfer Protocol for exchanging files, uses ports 20 (data) & 21 (control).
- **SMTP:** Protocol for email transmission over TCP port 25.

---

## Q12. Sockets and Types
Sockets are software endpoints for network communication.

- **Stream sockets:** Use TCP for reliable, ordered data.
- **Datagram sockets:** Use UDP for fast, connectionless transfer.
- **Raw sockets:** Access to lower-layer protocols (for custom networking).

---

## Q13. Use of DNS in Networking
DNS translates domain names into IP addresses, enabling:

- Easy website access.
- Scalable Internet growth.
- Email delivery and other name-based services.

---

## Q14. ARP Protocol and Packet Header
**ARP (Address Resolution Protocol):** Finds MAC address for a given IP address in a local network.

**ARP Header Fields:**
- Hardware type: Ethernet (1)
- Protocol type: IP (0x0800)
- Hardware size: MAC address length (6)
- Protocol size: IP address length (4)
- Opcode: Request (1) or Reply (2)
- Sender MAC address
- Sender IP address
- Target MAC address
- Target IP address
