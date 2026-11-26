#### commands
* -i INTERFACE
* ip address show/ip a s (list of available network interfaces)
* tcpdump -i INTERFACE (Captures packets on a specific network interface)
* tcpdump -w FILE	(Writes captured packets to a file)
* tcpdump -r FILE	(Reads captured packets from a file)
* tcpdump -c COUNT	(Captures a specific number of packets)
* tcpdump -n	(Don’t resolve IP addresses)
* tcpdump -nn	(Don’t resolve IP addresses and don’t resolve protocol numbers)
* tcpdump -v	(Verbose display; verbosity can be increased with -vv and -vvv)
    * i.e: sudo tcpdump -i ens5 -c 5 -n (sudo means "superuser do"; ens5 is the network interface)
    * tcpdump -i eth0 -c 50 -v (captures and displays 50 packets by listening on the eth0 interface, which is a wired Ethernet, and displays them verbosely)
    * tcpdump -i wlo1 -w data.pcap (captures packets by listening on the wlo1 interface (the WiFi interface) and writes the packets to data.pcap. It will continue till the user interrupts the capture by pressing CTRL-C)
    * tcpdump -i any -nn (captures packets on all interfaces and displays them on screen without domain name or protocol resolution)

### Saving Captured packets
* -w FILE (save the captured packets into a file) - extension of the file is most commonly set to .pcap

### Read Captured Packets from a file
* -r FILE (read packets from file)
* very useful for learning about protocol behaviour
* You can capture network traffic over a suitable time frame to inspect a specific protocol, then read the captured file while applying filters to display the packets you are interested in

### Limit the number of captured packets
* -c COUNT (specify the number of packets to capture)
* Without specifying a count, the packet capture will continue till you interrupt it (CTRL+C)

### Dont resolve IP Addresses and Port Numbers
* Tcpdump will resolve IP addresses and print friendly domain names where possible
* -n (if you dont want IP Addresses to be resolved) - to avoid making such DNS lookups
* -nn (if you dont want port numbers to be resolved) - port 80 being resolved to http

### Produce Verbose Output
* -v (produce a slightly more verbose output) - will print “the time to live, identification, total length and options in an IP packet” among other checks
* -vv (will produce more verbose output)
* -vvv (will provide even more verbosity)

