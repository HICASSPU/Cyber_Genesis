# **Cyber Genesis - Day 6: Shodan: The Search Engine for Hackers** 🌐

Welcome to **Day 6 of the Cyber Genesis series!** 🚀  
Today, we explore **Shodan**, the search engine for Internet-connected devices. Shodan is a powerful tool used in cybersecurity to discover exposed services, vulnerable devices, and misconfigured systems. Let’s unlock its potential for reconnaissance, threat hunting, and monitoring! 🔍

---

## **What is Shodan?**

**Shodan** is a specialized search engine that indexes information about Internet-connected devices, including webcams, routers, servers, IoT devices, and industrial control systems (ICS). Unlike traditional search engines, Shodan focuses on metadata, like open ports, banners, and device configurations.

---

## **Key Features of Shodan**

1. **Device Discovery**  
   - Find webcams, printers, industrial systems, and more.  
   - Identify devices by banner information, services, or open ports.

2. **Port and Service Scanning**  
   - Search for open ports (e.g., `port:22`) or specific services (e.g., `ftp`, `http`).  
   - Example: `port:3389` shows devices running Remote Desktop Protocol (RDP).

3. **Geolocation Data**  
   - Locate devices based on IP address and physical location.  
   - Useful for tracking regional vulnerabilities.

4. **Filters**  
   - Use advanced filters like `country:`, `org:`, `product:`, and `os:` to refine results.  
   - Example: `country:"US" product:"Apache"` shows Apache servers in the US.

5. **SSL and Hostname Filtering**  
   - Search for specific SSL certificates or hostnames.  
   - Examples:  
     - `hostname:"target.com"`: Devices linked to a specific hostname.  
     - `ssl.cert.subject.cn:"target.com"`: Devices with SSL certificates issued for a target domain.

---

## **Shodan Filtering Commands**

Shodan offers a wide array of filters that allow you to narrow down search results for precise information. Below are examples of both basic and advanced filtering commands:

### **Basic Filters**
1. **Network and Location Filters**  
   - `net:192.168.1.0/24`: Search within a specific IP range.  
   - `country:"US"`: Filter results by country.  
   - `city:"Mumbai"`: Filter results by city.

2. **Service and Protocol Filters**  
   - `port:22`: Find devices running SSH.  
   - `product:"nginx"`: Filter by product name.  
   - `service:"http"`: Search for devices running HTTP services.

3. **Operating System Filters**  
   - `os:"Windows"`: Devices running a Windows OS.  

4. **Vulnerability Filters**  
   - `vuln:"CVE-2021-44228"`: Devices affected by a specific CVE.

---

### **Advanced Filtering Commands**

#### **Search for Specific SSL Information**  
```plaintext
ssl:"CERTIFICATE_NAME" -http.title:"Invalid URL" -http.title:"ERROR" -org:"HOSTING_PROVIDER_NAME"

```
Purpose: Search for devices using specific SSL certificates while excluding common error pages or results linked to certain hosting providers.
**Purpose**: Search for devices using specific SSL certificates while excluding common error pages or results linked to certain hosting providers.

#### **Combine Multiple Filters**  
```plaintext
hostname:"targetsite.com" port:443 -http.title:"Access Denied" -http.html:"Error Page"
```
**Purpose**: Focus on HTTPS servers of a specific site, excluding irrelevant or restricted pages.

#### **Target Misconfigured Services**  
```plaintext
port:21 "230 Login successful" -ftp.banner:"ProFTPD"
```
**Purpose**: Look for open FTP servers with successful login banners while excluding specific server types.

#### **Identify Vulnerable Systems by CVE**  
```plaintext
vuln:"CVE-2022-XXXXX" -org:"Specific Organization"
```
**Purpose**: Find systems affected by a particular vulnerability while excluding results from specific organizations.

#### **Search for IoT Devices with Open Ports**  
```plaintext
product:"Webcam" port:554 -http.html:"Login required"
```
**Purpose**: Locate IoT webcams running on RTSP (Real-Time Streaming Protocol) while excluding login-restricted results.

---

## **Shodan CLI**

The **Shodan CLI (Command-Line Interface)** enables users to perform Shodan searches and interact with its API directly from the command line, providing flexibility and automation capabilities.

### **Installation**
Install the Shodan CLI using Python’s pip:  
```bash
pip install shodan
```

### **Key Commands**
1. **Initialize the CLI**  
   Add your Shodan API key:  
   ```bash
   shodan init <API_KEY>
   ```

2. **Perform Searches**  
   Use the Shodan CLI to run queries:  
   ```bash
   shodan search apache country:US
   ```

3. **Scan IPs**  
   Scan a specific IP or domain for open ports:  
   ```bash
   shodan host <IP>
   ```

4. **Save Results**  
   Export search results to a file for analysis:  
   ```bash
   shodan search nginx --limit 100 --fields ip_str,port --separator , > results.csv
   ```

---

## **Shodan Monitoring**

**Shodan Monitoring** provides real-time tracking and alerts for your organization's Internet-facing assets. This feature ensures that you stay informed about vulnerabilities and new exposures.

### **How It Works**
1. **Asset Tracking**  
   - Monitor your IP ranges, domains, or network blocks for changes.  
   - Identify new devices or services added to your network.

2. **Alerts**  
   - Set up alerts for specific queries (e.g., open ports, services).  
   - Receive notifications when new results match your criteria.  

3. **Integration**  
   - Use Shodan Monitoring with third-party tools (e.g., Splunk, SIEMs) for enhanced visibility.  

### **Creating an Alert**
1. Log in to your Shodan account.  
2. Go to the **Alerts** section.  
3. Set a query (e.g., `org:"YourOrganization"` or `port:22`) and enable notifications.

---

## **Resources for Day 6**

### **Official Resources**
- [Shodan Official Website](https://www.shodan.io/)  
- [Shodan Filters and Syntax](https://help.shodan.io/)  

### **Interactive Labs**
- [Shodan Basics - TryHackMe](https://tryhackme.com/room/shodan)  
- [Exploring Shodan Data - Practical Lab](https://tryhackme.com/room/shodanexplorer)  

### **YouTube Tutorials**
- [Shodan for Beginners](https://www.youtube.com/watch?v=dtKv4IRnL-I&list=PLPeQDuymW04D4HUKJWBwoS61D4AVHvfNt)
- [How To Use Shodan For Bug Bounty Hunters](https://www.youtube.com/watch?v=4CL_8GRNVTE)
- [Power Of Shodan](https://www.youtube.com/watch?v=WgMGLlpznao)

### **Github Resources**
- [Github Repo](https://github.com/lothos612/shodan)

---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**
Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
