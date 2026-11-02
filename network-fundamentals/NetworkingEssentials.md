## Concepts
* DHCP (Dynamic Host Configuration Protocol)
* ARP (Address Resolution Protocol)
* NAT (Network Address Translation)
* ICMP (Internet Control Message Protocol)
    * Ping
    * Traceroute

### other
* Whenever we want to access a network, at the very least, we need to configure the following:
    * IP address along with subnet mask
    * Router (or gateway)
    * DNS server

## DHCP
* application-level protocol that relies on UDP
* follow 4 steps: (DORA)
    * Discover (The client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists)
    * Offer (The server responds with a DHCPOFFER message with an IP address available for the client to accept)
    * Request (The client responds with a DHCPREQUEST message to indicate that it has accepted the offered IP)
    * Acknowledge (The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client)

## ARP
* Whenever one host needs to communicate with another host on the same Ethernet or WiFi, it must send the IP packet within a data link layer frame. Although it knows the IP address of the target host, it needs to look up the target’s MAC address so the proper data link header can be created.
* Makes it possible to find the MAC address of another device on the Ethernet
* An ARP Request or ARP Reply is not encapsulated within a UDP or even IP packet; it is encapsulated directly within an Ethernet frame
* ARP is considered layer 2 because it deals with MAC addresses
* ARP allows the translation from layer 3 addressing to layer 2 addressing

## ICMP
* mainly used for network diagnostics and error reporting
* Two popular commands rely on ICMP, and they are instrumental in network troubleshooting and network security:
    * ping - uses ICMP to test connectivity to a target system and measures the round-trip time (RTT)
    * traceroute - is called traceroute on Linux and UNIX-like systems and tracert on MS Windows systems. It uses ICMP to discover the route from your host to the target
### ping
* The ping command sends an ICMP Echo Request (ICMP Type 8)
* The computer on the receiving end responds with an ICMP Echo Reply (ICMP Type 0)
* Many things might prevent us from getting a reply. In addition to the possibility of the target system being offline or shut down, a firewall along the path might block the necessary packets for ping to work
### traceroute
* The Internet protocol has a field called Time-to-Live (TTL) that indicates the maximum number of routers a packet can travel through before it is dropped
* When the TTL reaches zero, the router drops the packet and sends an ICMP Time Exceeded message (ICMP Type 11)
* "time" is measured in the number of routers
* there is always a possibility that an ICMP Time Exceeded message gets blocked and never reaches us.

## Routing
* OSPF (Open Shortest Path First)
* EIGRP (Enhanced Interior Gateway Routing Protocol)
* BGP (Border Gateway Protocol)
* RIP (Routing Information Protocol)
### OSPF
* routing protocol that allows routers to share information about the network topology and calculate the most efficient paths for data transmission
* It does this by having routers exchange updates about the state of their connected links and networks
* each router has a complete map of the network and can determine the best routes to reach any destination
### EIGRP
* Cisco proprietary routing protocol that combines aspects of different routing algorithms
* allows routers to share information about the networks they can reach and the cost (like bandwidth or delay) associated with those routes
* Routers then use this information to choose the most efficient paths for data transmission
### BGP
* the primary routing protocol used on the Internet
* allows different networks (like those of Internet Service Providers) to exchange routing information and establish paths for data to travel between these networks
* BGP helps ensure data can be routed efficiently across the Internet, even when traversing multiple networks
### RIP
* simple routing protocol often used in small networks
* Routers running RIP share information about the networks they can reach and the number of hops (routers) required to get there
* each router builds a routing table based on this information, choosing the routes with the fewest hops to reach each destination


## NAT
* The idea behind NAT lies in using one public IP address to provide Internet access to many private IP addresses
* Unlike routing, which is the natural way to route packets to the destination host, routers that support NAT must find a way to track ongoing connections
* NAT-supporting routers maintain a table translating network addresses between internal and external networks
* Generally, the internal network would use a private IP address range, while the external network would use a public IP address
