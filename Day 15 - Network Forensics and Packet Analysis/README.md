# **Cyber Genesis - Day 15: Network Forensics and Packet Analysis** 🌐📡

Welcome to **Day 15 of the Cyber Genesis series!** 🚀  
Today, we dive into **Network Forensics and Packet Analysis**, where we learn how to investigate network traffic to detect anomalies, trace intrusions, and uncover malicious activities. This essential skill is crucial for identifying threats in real time and reconstructing past incidents.

---

## **What is Network Forensics?**

**Network Forensics** is the process of capturing, recording, and analyzing network traffic to identify security incidents, detect data breaches, or troubleshoot network performance issues.

---

### **Why is Network Forensics Important?**

1. **Incident Detection and Response**  
   - Identify unauthorized access, data exfiltration, or malware communication.  

2. **Tracing Intrusion Sources**  
   - Analyze attack paths and trace malicious actors back to their origin.  

3. **Evidence Collection**  
   - Provide actionable insights and evidence for legal or remediation purposes.  

---

## **Key Concepts in Network Forensics**

1. **Packet Capture (PCAP)**  
   - Capturing raw network traffic for analysis.  

2. **Protocols to Analyze**  
   - HTTP, HTTPS, FTP, DNS, TCP, UDP, and ICMP.  

3. **Indicators of Compromise (IoCs)**  
   - Suspicious IPs, unusual ports, unexpected protocols, and malicious payloads.  

4. **File Extraction from Traffic**  
   - Extracting files (e.g., images, executables) embedded in network traffic.  

---

## **Tools for Network Forensics and Packet Analysis**

### **1. Wireshark**  
**Description**: A powerful GUI-based tool for packet capture and analysis.  
- **Features**:  
  - Inspect packets for protocols like HTTP, DNS, TCP, and ICMP.  
  - Reconstruct streams to view entire conversations.  
  - Filter traffic using powerful display filters.  

**Example Wireshark Filter**:  
```plaintext
http.request or tcp.port == 443
```

---

### **2. Tcpdump**  
**Description**: A command-line tool for capturing and analyzing packets.  
- **Usage**:  
   - Capture all traffic on interface `eth0`:  
     ```bash
     tcpdump -i eth0 -w capture.pcap
     ```  
   - Display DNS queries:  
     ```bash
     tcpdump -i eth0 port 53
     ```

---

### **3. Zeek (formerly Bro)**  
**Description**: A network security monitoring tool for analyzing network logs.  
- **Features**:  
   - Generate logs for protocols (e.g., HTTP, DNS).  
   - Detect anomalies in network traffic.  

---

### **4. NetworkMiner**  
**Description**: A forensic analysis tool for extracting files and metadata from PCAPs.  
- **Features**:  
   - File extraction: Extract files embedded in network traffic.  
   - Metadata analysis: View details like IP addresses and hostnames.  

---

### **5. Suricata**  
**Description**: An open-source intrusion detection and prevention system (IDS/IPS).  
- **Features**:  
   - Analyze packets for signatures of known threats.  
   - Detect unusual patterns in real-time traffic.

---

## **Network Forensics Workflow**

### **Step 1: Capture Traffic**  
- Use tools like **Wireshark** or **Tcpdump** to collect network traffic.  
- Save the traffic in `.pcap` format for further analysis.

### **Step 2: Filter and Inspect Traffic**  
- Use Wireshark or Tcpdump filters to narrow down traffic based on protocols or IPs.  
- Example: Filter HTTP requests in Wireshark:  
  ```plaintext
  http.request
  ```

### **Step 3: Extract Artifacts**  
- Use tools like **NetworkMiner** to extract files or credentials from the traffic.  

### **Step 4: Detect Suspicious Patterns**  
- Look for unusual traffic, like communication with unknown IPs or abnormal protocol usage.  
- Use tools like **Zeek** or **Suricata** to identify anomalies.

---

## **Practical Exercise**

### **Scenario**:  
A company suspects that sensitive files are being exfiltrated over the network.  

#### **Steps to Investigate**:
1. **Capture Traffic**  
   - Use **Wireshark** to monitor the company’s network.  

2. **Analyze Packets**  
   - Filter for suspicious traffic, like large data uploads:  
     ```plaintext
     tcp.len > 1000
     ```  
   - Check DNS queries for unusual domain lookups:  
     ```plaintext
     dns.qry.name contains "example.com"
     ```  

3. **Reconstruct the Traffic**  
   - Use **NetworkMiner** to extract files from the captured packets.

4. **Identify IoCs**  
   - Use **Zeek** or **Suricata** to detect unusual patterns and generate logs.

---

## **Key Commands for Tcpdump and Wireshark**

- **Tcpdump**:  
   - Capture all traffic on interface:  
     ```bash
     tcpdump -i eth0 -w traffic.pcap
     ```  
   - Filter for DNS queries:  
     ```bash
     tcpdump -i eth0 port 53
     ```  

- **Wireshark Filters**:  
   - Filter for HTTP requests:  
     ```plaintext
     http.request
     ```  
   - Display traffic from a specific IP:  
     ```plaintext
     ip.addr == 192.168.1.100
     ```  

---

## **Resources for Day 15**

### **Official Tools and Documentation**  
- [Wireshark Official Site](https://www.wireshark.org/)  
- [Tcpdump Manual](https://www.tcpdump.org/manpages/tcpdump.1.html)  
- [Zeek Documentation](https://docs.zeek.org/en/current/)  

### **Interactive Labs**  
- **TryHackMe**: [Wireshark](https://tryhackme.com/r/module/wireshark).
---

## **Ethics and Legal Considerations**

1. **Authorization**: Always ensure you have permission to capture and analyze network traffic.  
2. **Privacy**: Avoid inspecting private or sensitive data without consent.  
3. **Integrity**: Preserve the original traffic data for legal and investigative purposes.

---

## **Created by:**

**Varad Mene**

---

## **Contributing**  
Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
