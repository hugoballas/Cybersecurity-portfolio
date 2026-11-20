## Networking Secure Protocols
* HTTPS
* POP3S
* SMTPS
* IMAPS

### TLS
* cryptographic protocol operating at the OSI model’s transport layer
* allows secure communication between a client and a server over an insecure network
* TLS ensures that no one can read or modify the exchanged data

### HTTPS
#### HTTP over TLS
* HTTPS stands for Hypertext Transfer Protocol Secure. It is basically HTTP over TLS. Consequently, requesting a page over HTTPS will require the following three steps:
    * Establish a TCP three-way handshake with the target server
    * Establish a TLS session
    * Communicate using the HTTP protocol; for example, issue HTTP requests, such as GET / HTTP/1.1
* if one tries to follow the stream of packets and combine all their contents, they will only get gibberish
* The exchanged traffic is encrypted

#### Encryption Key
* Adding TLS to HTTP leads to all the packets being encrypted
* We can no longer see the contents of the exchanged packets unless we get access to the private key

## SMTPS, POP3S and IMAPS
* Using these protocols over TLS is no different than using HTTP over TLS; therefore, almost all the points from the HTTPS discussion apply to these protocols

#### Secure versions use the following TCP por numbers by default
* HTTPS: 443
* SMTPS:"465 and 587
* POP3S: 995
* IMAPS: 993

### SSH
* SSH server listens on port 22

#### Benefits
* Secure authentication: Besides password-based authentication, SSH supports public key and two-factor authentication
* Confidentiality: OpenSSH provides end-to-end encryption, protecting against eavesdropping. Furthermore, it notifies you of new server keys to protect against man-in-the-middle attacks.
* Integrity: In addition to protecting the confidentiality of the exchanged data, cryptography also protects the integrity of the traffic
* Tunneling: SSH can create a secure “tunnel” to route other protocols through SSH. This setup leads to a VPN-like connection.
* X11 Forwarding: If you connect to a Unix-like system with a graphical user interface, SSH allows you to use the graphical application over the network.

#### commands
* ssh username@hostname to connect to an SSH server (If the username is the same as your logged-in username, you only need ssh hostname)
* ssh 192.168.124.148 -X (The argument -X is required to support running graphical interfaces)

### SFTP and FTPS
* SFTP stands for SSH File Transfer Protocol and allows secure file transfer
* SFTP listens on port number 22
* If enabled in the OpenSSH server configuration, you can connect using a command such as sftp username@hostname
* Once logged in, you can issue commands such as get filename and put filename to download and upload files
* SFTP commands are Unix-like and can differ from FTP commands
* SFTP should not be confused with FTPS
-
* FTPS is secured using TLS, just like HTTPS
* While FTP uses port 21, FTPS usually uses port 990
* It requires certificate setup, and it can be tricky to allow over strict firewalls as it uses separate connections for control and data transfer
