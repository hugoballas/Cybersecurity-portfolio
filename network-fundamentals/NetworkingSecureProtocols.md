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
