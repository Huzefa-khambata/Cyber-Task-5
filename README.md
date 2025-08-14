Cyber-Task-5
Task – Basic Packet Capture and Analysis Using Wireshark

Objective
Capture and analyze live network traffic using **Wireshark** to understand different network protocols and packet structures.

Tools Used
- Wireshark – Open-source packet capture and analysis tool.
- Linux OS (commands provided for Debian/Ubuntu-based systems).

---

Steps Performed

1. Install Wireshark
```bash
sudo apt update
sudo apt install wireshark -y
```
During installation, allow non-root users to capture packets if prompted.

---

2. Start Capturing on Active Network Interface
- Open Wireshark from the application menu or run:
```bash
wireshark &
```
- Select your **active network interface** (e.g., `eth0`, `wlan0`) and click **Start**.

---

3. Generate Traffic
While capture is running, generate some traffic:
```bash
ping google.com -c 4
```
Or open a web browser and visit any website.

---

4. Stop Capture
After ~1 minute of activity, click the **Stop** button in Wireshark.

---

5. Filter Captured Packets by Protocol
In the filter bar, try:
- `http` – show only HTTP traffic.
- `dns` – show only DNS traffic.
- `tcp` – show only TCP packets.

---

6. Identify at Least 3 Different Protocols
From the capture, you might see:
- **DNS** – name resolution requests/responses.
- **TCP** – connection-oriented traffic (e.g., HTTP over port 80, HTTPS over port 443).
- **ICMP** – ping requests/replies.
- **HTTP/HTTPS** – website requests and encrypted traffic.

---

7. Export Capture as `.pcap`
Go to:
`File → Save As` → choose `.pcap` format → name it (e.g., `network_capture.pcap`).

---

8. Summary of Findings (Example)
| Protocol | Description | Observation |
|----------|-------------|-------------|
| DNS      | Resolves domain names to IP addresses | Queries to `8.8.8.8` and `1.1.1.1` |
| TCP      | Reliable transport for application data | Seen in HTTP and HTTPS connections |
| ICMP     | Internet Control Message Protocol | Ping packets to `google.com` |

---

## Key Learnings
- Wireshark helps visualize and understand network traffic in real-time.
- Filtering allows quick isolation of specific protocols for troubleshooting.
- Different protocols serve different layers of communication.

---

## Interview Questions

1. What is Wireshark used for?**  
A tool to capture, inspect, and analyze network packets for troubleshooting, monitoring, and security analysis.

2. What is a packet?**  
A small unit of data transmitted over a network, containing both payload and header information.

3. How to filter packets in Wireshark?**  
Using the display filter bar with syntax like `http`, `dns`, `tcp.port==80`.

4. What is the difference between TCP and UDP?**  
- TCP: Connection-oriented, reliable, ensures delivery (e.g., HTTP, FTP).  
- UDP: Connectionless, faster, no delivery guarantee (e.g., DNS, streaming).

5. What is a DNS query packet?**  
A request sent from a client to a DNS server asking for the IP address of a domain.

6. How can packet capture help in troubleshooting?**  
It reveals delays, dropped packets, incorrect configurations, and malicious activity.

7. What is a protocol?**  
A set of rules defining how data is transmitted between devices over a network.

8. Can Wireshark decrypt encrypted traffic?**  
Yes, but only if you have the encryption keys or use protocols that support decryption in Wireshark (e.g., SSL/TLS with session keys).

---

