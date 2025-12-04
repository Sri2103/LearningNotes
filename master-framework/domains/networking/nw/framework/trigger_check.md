# Networking Trigger Checklist

- High latency → check DNS, RTT, congestion
- Connection refused → firewall/NAT
- Slow API → TCP retransmits or queueing
- Packet loss → congestion or MTU issue
- HTTPS issues → certificate/TLS handshake
- Load issues → LB health checks
- Random failures → DNS caching or TTL
