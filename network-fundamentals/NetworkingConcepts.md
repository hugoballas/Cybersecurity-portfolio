## OSI Model
* OSI model is composed of seven layers
  * Physical Layer
  * Data Link Layer
  * Network Layer
  * Transport Layer
  * Session Layer
  * Presentation Layer
  * Application Layer
* Please Do Not Throw Spinach Pizza Away (PDNTSPA) - acronym

### Physical Layer
* deals with the physical connection between devices
* includes the medium, such as a wire, and the definition of the binary digits 0 and 1
* Data transmission can be via an electrical, optical, or wireless signal
* i.e: ethernet cable, optical fibre cable, WiFi radio bands, 2.4GHz band, 5GHz band and 6GHz band

### Data Link Layer
* represents the protocol that enables data transfer between nodes on the same network segment
* describes an agreement between the different systems on the same network segment on how to communicate
* network segment refers to a group of networked devices using a shared medium or channel for information transfer
* i.e: company office with ten computers connected to a network switch, thats a network segment
* i.e2: ethernet (802.3) and WiFi (802.11)

### Network Layer
* concerned with sending data between different networks
* the network layer handles logical addressing and routing
  * i.e: finding a path to transfer the netowrk packets between the diverse networks
* i.e: company has multiple offices distributed across various cities, countries, or even continents. The network layer is responsible for connecting the different offices together
* i.e of network layers: IP, ICMP, VPN ( IPSec and SSL/TLS VPN)

### Transpor Layer
* enables end-to-end communication between running applications on different hosts
  * i.e: Your web browser is connected to "website name" web server over the transport layer, which can support various functions like flow control, segmentation, and error correction
* i.e: TCP and UDP

### Session Layer
* responsible for establishing, maintaining, and synchronising communication between applications running on different hosts
* Establishing a session means initiating communication between applications and negotiating the necessary parameters for the session
* Data synchronisation ensures that data is transmitted in the correct order and provides mechanisms for recovery in case of transmission failures
* i.e: NFS and RPC

### Presentation Layer
* ensures the data is delivered in a form the application layer can understand
* handles data encoding, compression, and encryption
* i.e encoding: ASCII or Unicode

### Application Layer
* provides network services directly to end-user applications
* web browser would use the HTTP protocol to request a file, submit a form, or upload a file
* i.e: HTTP, FTP, DNS, POP3, SMTP and IMAP
