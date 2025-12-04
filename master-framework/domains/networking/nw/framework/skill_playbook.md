# Networking Playbook

## How to Debug Any Network Issue

### 1. Identify layer:

- L1: cables, NIC
- L2: MAC, ARP
- L3: IP routing
- L4: TCP/UDP
- L7: HTTP, DNS, TLS

### 2. Tools to use:

- `ping` → connectivity
- `traceroute` → routing path
- `nslookup/dig` → DNS
- `curl -v` → HTTP flow
- `tcpdump` → packet capture
- `wireshark` → deep analysis

### 3. Packet Flow Playbook

1. DNS lookup
2. TCP handshake
3. TLS handshake
4. HTTP request
5. Response
6. Connection close

### 4. TCP Performance Playbook

- Check handshake time
- Check RTT
- Check window size
- Check retransmissions
- Check congestion

### 5. HTTP Playbook

- Look at headers
- Identify latency contributors
- Check caching
- Check compression

### 6. Load Balancing Playbook

L4 → TCP/UDP based  
L7 → HTTP header/URL based
