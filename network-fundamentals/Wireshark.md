* Wireshark is an open-source, cross-platform network packet analyser tool capable of sniffing and investigating live traffic and inspecting packet captures (PCAP)

### Uses
* Detecting and troubleshooting network problems, such as network load failure points and congestion
* Detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic
* Investigating and learning protocol details, such as response codes and payload data

### GUI and Data
* Toolbar: The main toolbar contains multiple menus and shortcuts for packet sniffing and processing, including filtering, sorting, summarising, exporting and merging.
* Display Filter Bar: The main query and filtering section.
* Recent Files: List of the recently investigated files. You can recall listed files with a double-click
* Capture Filter and Interfaces: Capture filters and available sniffing points (network interfaces).  The network interface is the connection point between a computer and a network. The software connection (e.g., lo, eth0 and ens33) enables networking hardware.
* Status Bar: Tool status, profile and numeric packet information

### Loading PCAP Files
* Packet List Pane: Summary of each packet (source and destination addresses, protocol, and packet info). You can click on the list to choose a packet for further investigation. Once you select a packet, the details will appear in the other panels.
* Packet Details Panel: Detailed protocol breakdown of the selected packet
* Packet Bytes Pane: Hex and decoded ASCII representation of the selected packet. It hightlights the packet field depending on the clicked section in the details pane


## Packet Dissection
* Packet dissection is also known as protocol dissection, which investigates packet details by decoding available protocols and fields

#### Layers
* Frame/packet (details specific to the Physical Layer)
* source [MAC] (Data link layer)
* source [IP] (Network Layer)
* protocol (Transport layer)
* protocol errors (Transport layer)
* application protocol (application layer)
* application data (application layer)


## Expert info
* Chat (severity) - Blue (colour) - Information on usual workflow (info)
* Note - cyan - notable events like application error codes
* Warn - yellow - warnings like unusual error codes or problem statements
* Error - red - problems like malformed packets

## Packet Filtering
* there is a golden rule for analysts who don't want to write queries for basic tasks: "If you can click on it, you can filter and copy it"
* Wireshark has a powerful filter engine that helps analysts to narrow down the traffic and focus on the event of interest
* Wireshark has two types of filtering approaches: capture and display filters

#### Capture filters
* used for "capturing" only the packets valid for the used filter
#### Display filters
* used for "viewing" the packets valid for the used filter

### Apply as Filter
* most basic way of filtering traffic
* you can click on the field you want to filter and use the "right-click menu" or "Analyse --> Apply as Filter" menu to filter the specific value

### Conversation Filter
* suppose you want to investigate a specific packet number and all linked packets by focusing on IP addresses and port numbers. In that case, the "Conversation Filter" option helps you view only the related packets and hide the rest of the packets easily

### Colourise Conversation
* highlights the linked packets without applying a display filter and decreasing the number of viewed packets
* You can use the "right-click menu" or "View --> Colourise Conversation" menu to colourise a linked packet in a single click

### Prepare as Filter
* helps analysts create display filters using the "right-click" menu
* unlike the previous one, this model doesn't apply the filters after the choice. It adds the required query to the pane and waits for the execution command (enter) or another chosen filtering option by using the ".. and/or.." from the "right-click menu"

### Apply as Column
* You can use the "right-click menu" or "Analyse --> Apply as Column" menu to add columns to the packet list pane
* Once you click on a value and apply it as a column, it will be visible on the packet list pane
* This function helps analysts examine the appearance of a specific value/field across the available packets in the capture file

### Follow Stream
* it is possible to reconstruct the streams and view the raw traffic as it is presented at the application level
* streams help analysts recreate the application-level data and understand the event of interest
* It is also possible to view the unencrypted protocol data like usernames, passwords and other transferred data
* You can use the"right-click menu" or "Analyse --> Follow TCP/UDP/HTTP Stream" menu to follow traffic streams
  * packets originating from the server are highlighted with blue, and those originating from the client are highlighted with red

### Simple Display Filter Queries
* The easiest way to filter quickly the huge amount of packets, is by applying a display filter using the "Apply a display filter"

#### Filter by protocol name
* type in the protocol name and hit enter or click on the arrow button at the right hand side of the display filter bar, i.e: http

#### Filter by protocol port number
* use the structure "tcp.port == <port number>" or "udp.port == <port number>"
    * see only http packets, you would use the filter "tcp.port == 80"

#### Filter by IP
* To filter for a specific IP, you can use the structure "ip.addr == <IP address>"
