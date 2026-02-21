# Computer Networks Interview Questions

## Basic Level

**Q1: What is a Computer Network?**
**Answer:**
A network is a collection of computers and devices connected together using communication devices and transmission media to share resources (like internet, printers, and files).

**Q2: What is an IP Address and what is its purpose?**
**Answer:**
An IP (Internet Protocol) address is a unique numerical label assigned to every device connected to a network. Its main purposes are:
* **Host Identification:** Identifying a specific device.
* **Location Addressing:** Providing the path to reach that device on the network.

**Q3: Describe the main differences between TCP and UDP.**
**Answer:**
* **TCP (Transmission Control Protocol):** Connection-oriented, highly reliable. It guarantees delivery of packets in the correct order using acknowledgments and retransmissions. Slower due to overhead. Used for web browsing (HTTP), emails, and file transfers.
* **UDP (User Datagram Protocol):** Connectionless, unreliable ("fire and forget"). It does not guarantee delivery or order, but it is much faster. Used for live video streaming, online gaming, and VoIP.

## Intermediate Level

**Q4: Can you list the 7 layers of the OSI model in order?**
**Answer:**
1. **Physical Layer:** Bits to signals over cables/wireless.
2. **Data Link Layer:** MAC addresses and error detection (Switches).
3. **Network Layer:** IP addresses and routing (Routers).
4. **Transport Layer:** TCP/UDP, ports, and data flow.
5. **Session Layer:** Establishing and terminating connection sessions.
6. **Presentation Layer:** Data encryption, compression, and formatting.
7. **Application Layer:** Network applications (HTTP, FTP, DNS).

**Q5: What is DNS and how does it work?**
**Answer:**
DNS (Domain Name System) is the phonebook of the internet. 
Computers use IP addresses to communicate, but humans use names (like `google.com`). DNS translates human-readable domain names into the IP addresses required to route data to the correct servers.

**Q6: What is a Subnet Mask and why is it used?**
**Answer:**
A subnet mask is a 32-bit number that masks an IP address. It is used to divide an IP address into two parts: the **Network Address** (identifying the specific network) and the **Host Address** (identifying the specific device on that network). It helps in dividing large networks into smaller, manageable subnets.

## Advanced Level

**Q7: How does the TCP Three-Way Handshake work?**
**Answer:**
It is the process used to establish a reliable TCP connection:
1. **SYN:** The client sends a Synchronize (SYN) packet to the server to request a connection.
2. **SYN-ACK:** The server acknowledges the request by sending back a Synchronize-Acknowledgment (SYN-ACK) packet.
3. **ACK:** The client replies with an Acknowledgment (ACK) packet. The connection is now established.

**Q8: Explain what BGP (Border Gateway Protocol) is.**
**Answer:**
BGP is the core routing protocol of the global internet. While internal routers use protocols like OSPF to find the best path within a single company's network, BGP is used by Internet Service Providers (ISPs) to announce which IP addresses they own and to determine the best path to route traffic across the massive global web of different ISPs. 

**Q9: What is the difference between a Hub, a Switch, and a Router?**
**Answer:**
* **Hub (Layer 1):** Dumb physical device. It receives a packet on one port and blindly broadcasts it to all other connected ports. Highly inefficient.
* **Switch (Layer 2):** Smart local device. It learns the MAC addresses of connected devices and forwards packets *only* to the specific intended port.
* **Router (Layer 3):** Network device. It reads IP addresses and forwards packets between entirely *different* networks, determining the best global path.
