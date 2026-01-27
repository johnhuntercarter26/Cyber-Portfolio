# Network Traffic Analysis (Wireshark)

## Objective
Capture and analyze real network traffic to understand how common protocols operate during normal web activity, with a focus on DNS resolution, TCP connection establishment, and TLS encryption.

## Environment
- Live traffic capture on a personal machine
- No virtual machines used
- Normal user activity (web browsing, email, speed tests)

## Tools Used
- Wireshark

---

## DNS Analysis
DNS traffic was analyzed to observe how domain names are resolved prior to web connections.

Observations:
- The system issued DNS queries to an external resolver (1.1.1.1)
- Queries were sent in plaintext and responses were readable
- CNAME records routed traffic through content delivery networks (CDNs)
- Multiple IP addresses were returned for a single domain, indicating load balancing
- HTTPS DNS records were observed, reflecting modern connection negotiation

This demonstrates that DNS metadata can reveal browsing behavior even when application data is later encrypted.

*(See: dns-query-response-opera.png)*

---

## TCP Analysis
TCP traffic was analyzed to observe connection establishment behavior.

Observations:
- A full TCP three-way handshake was captured
- SYN, SYN/ACK, and ACK packets confirm reliable session setup
- Connections were established prior to encrypted data transfer

This confirms how TCP ensures reliable communication before higher-layer protocols are used.

*(See: tcp-three-way-handshake.png)*

---

## TLS Analysis
TLS traffic was analyzed to confirm encryption of application data.

Observations:
- TLSv1.2 and TLSv1.3 sessions were observed
- Client Hello packets revealed Server Name Indication (SNI)
- Server Hello and Change Cipher Spec messages established secure sessions
- Application data payloads were encrypted and unreadable
- Metadata such as IP addresses and ports remained visible

This demonstrates how encryption protects data in transit while still exposing limited connection metadata.

*(See: tls-handshake-encrypted-traffic.png)*

---

## Security Takeaways
- DNS traffic can expose browsing behavior even when HTTPS is used
- TCP provides reliable connection establishment before encryption
- TLS effectively encrypts application data but does not hide all metadata
- Network traffic analysis can reveal system behavior without decrypting content

## Limitations
- Traffic was captured from a single host
- Payload decryption was not attempted in this lab
- Analysis focused on protocol recognition rather than deep inspection


