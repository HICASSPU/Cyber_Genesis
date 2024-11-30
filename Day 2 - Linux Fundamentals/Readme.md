# **Complete Beginner: Cybersecurity Essentials**

Welcome to the **Complete Beginner's Guide**! This repository is designed to provide foundational knowledge for those stepping into the world of cybersecurity. It covers essential tools, techniques, and methodologies required to master the basics of Linux, networking, process management, and more.

---

## **Table of Contents**

1. [Linux Fundamentals](#linux-fundamentals)  
2. [Networking Concepts](#networking-concepts)  
3. [Nmap and Port Scanning](#nmap-and-port-scanning)  
4. [Process Management in Linux](#process-management-in-linux)  
5. [Text Editors and File Operations](#text-editors-and-file-operations)  
6. [Cybersecurity Labs and Practice Pathways](#cybersecurity-labs-and-practice-pathways)  

---

## **Linux Fundamentals**

Master the most popular operating system used in cybersecurity: **Linux**.

### **Key Commands**
- **Navigation:**
  - `ls`, `cd`, `pwd`: Navigate directories.
  - `find`, `grep`: Search for files or specific text.
- **File Operations:**
  - `cat`, `touch`, `cp`, `mv`: View, create, copy, and move files.
- **User Management:**
  - `chmod`: Change file permissions (e.g., `chmod 755 file.txt`).
  - `su`: Switch users.

### **Shell Operators**
- `&`: Run commands in the background.  
- `>`: Redirect output to a file (overwrites).  
- `>>`: Append output to a file.

### **File Transfers**
- **Wget:** Download files (`wget <URL>`).  
- **SCP:** Securely transfer files over SSH.

---

## **Networking Concepts**

Understand the foundation of how devices communicate.

### **OSI Model**

A layered model explaining how applications communicate over a network:  
1. **Application Layer**: End-user interaction.  
2. **Transport Layer**: Data flow control (TCP/UDP).  
3. **Network Layer**: IP addressing and routing.

### **Networking Tools**
- **Ping:** Test connectivity (`ping <IP/Domain>`).  
- **Traceroute:** Trace packet paths (`traceroute <Destination>`).  
- **Whois:** Retrieve domain registration info (`whois <domain>`).  
- **Dig:** Perform DNS lookups (`dig <domain>`).

---

## **Nmap and Port Scanning**

Discover open ports and vulnerabilities on a target system.

### **Port Types**
- **Well-Known Ports:** 0-1023 (e.g., HTTP on port 80).  
- **Registered Ports:** 1024-49151.  
- **Dynamic Ports:** 49152-65535, often used for temporary connections.

### **Why Nmap?**
- Identifies open, closed, or filtered ports on a target system.
- Enumerates services and vulnerabilities on open ports.

### **Scan Types**
- **TCP Connect Scan (-sT):** Full three-way handshake.  
- **SYN Scan (-sS):** Faster "half-open" scan.  
- **UDP Scan (-sU):** Probes UDP ports for responses.

### **Useful Switches**
- `-p`: Specify ports.  
- `-A`: Enable OS and version detection.  
- `--top-ports`: Scan top-used ports.

---

## **Process Management in Linux**

Manage and monitor system processes.

### **Viewing Processes**
- **Commands:**
  - `ps`: View active processes (`ps aux`).  
  - `top`: Real-time process monitoring.

### **Killing Processes**
- `kill <PID>`: Terminate a process by its ID.  
- `killall <Name>`: Terminate all processes by name.  
- **Signals:**
  - `SIGTERM`: Graceful termination.  
  - `SIGKILL`: Forceful termination.

---

## **Text Editors and File Operations**

Learn to edit files and manage data efficiently.

### **Text Editors**
- **Nano:** Beginner-friendly. Example: `nano file.txt`.  
- **VIM:** Advanced editor for power users.

### **File Commands**
- `touch`: Create a file.  
- `rm`: Remove files or directories.  
- `cp`, `mv`: Copy and move files.

---

## **Cybersecurity Labs and Practice Pathways**

Hands-on learning for practical experience.

### **Recommended Resources**
1. **Linux Fundamentals:**  
   - [TryHackMe: Linux Fundamentals](https://tryhackme.com/module/linux-fundamentals)  
2. **YouTube Playlist - Linux Essentials:**  
   - [Linux Essentials YouTube Playlist](https://www.youtube.com/watch?v=Byx4sgLR88E&list=PL0tP8lerTbX1m-Z1Dj7M-k-PuKDNJkRul)  
3. **OverTheWire Wargames:**  
   - [OverTheWire: Wargames](https://overthewire.org/wargames/)

---

## **Created by:**
**menevarad**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.


