### 🔧 Incident — Network Discovery and Port Analysis

**Objective:**  
Identify active hosts and exposed services within the network.

**Detection:**  
Performed network scan using Nmap to discover live hosts and open ports.

**Investigation:**  
- Executed network scan: nmap -sS 192.168.1.0/24

- Identified active devices within the network  
- Performed port analysis on discovered hosts  

**Findings:**  
- Detected multiple active hosts  
- Identified open ports including:
- FTP (21)
- Telnet (23)
- HTTP (80)
- SSH (22)
- Printer services (515, 9100)
- Observed management and application ports on network devices  

**Risk Insight:**  
- Telnet (23) is insecure and should be replaced with SSH  
- FTP (21) may expose sensitive data  
- Open management ports increase attack surface  

**Resolution:**  
Validated expected services and identified potential areas for security improvement.

**Validation:**  
Confirmed network visibility and service availability across multiple hosts.

## 🔎 Packet Analysis (Wireshark)

### 🔧 Incident — Detection of Unencrypted HTTP Traffic

**Objective:**  
Identify insecure web traffic within the network.

**Detection:**  
Applied Wireshark filter: tcp.port == 80


**Investigation:**  
- Captured network traffic using Wireshark  
- Filtered for HTTP traffic on port 80  
- Observed unencrypted web communication  

**Findings:**  
- Detected HTTP traffic transmitting data without encryption  
- Confirmed absence of TLS/HTTPS  

**Risk Insight:**  
- Traffic is visible in plaintext  
- Sensitive data could be intercepted  
- Indicates insecure communication channels  

**Resolution:**  
Recommended enforcing HTTPS and disabling HTTP where possible.

**Validation:**  
Confirmed ability to identify insecure traffic using packet analysis.
