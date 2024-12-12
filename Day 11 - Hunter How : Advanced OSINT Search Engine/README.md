# **Cyber Genesis - Day 11 : Hunter.How - Advanced OSINT Search Engine** 🌐

Welcome to **Day 11 of the Cyber Genesis series!** 🚀  
Today, we’re exploring **Hunter How**, an advanced OSINT (Open-Source Intelligence) search engine. Designed for cybersecurity professionals and OSINT enthusiasts, Hunter How aggregates and organizes public data to uncover valuable insights about domains, IPs, and more. Let’s dive into this powerful tool! 🔍

---

## **What is Hunter.How?**

**Hunter How** is an OSINT search engine that simplifies the process of collecting and analyzing public data. It enables users to search for critical information about:  
- **Domains**: Ownership, associated subdomains, and server details.  
- **IPs**: Geolocation, service banners, and open ports.  
- **Certificates**: SSL/TLS details and transparency logs.  

Hunter How is an essential tool for reconnaissance, vulnerability assessment, and threat hunting.

---

## **Key Features of Hunter How**

1. **Domain Information**  
   - Collects ownership details, DNS records, and subdomains associated with a target domain.

2. **IP Analysis**  
   - Provides information on IP geolocation, open ports, and running services.  

3. **SSL/TLS Certificate Insights**  
   - Tracks certificates issued for domains, their validity, and potential misconfigurations.  

4. **Search Customization**  
   - Supports filters and advanced queries for refining search results.  

5. **Historical Data**  
   - Tracks historical changes for domains, IPs, and certificates, useful for monitoring and investigations.

---

## **How to Use Hunter How**

### **1. Domain Search**  
- Enter the target domain (e.g., `example.com`) to uncover:  
  - Subdomains.  
  - DNS records (A, MX, CNAME, etc.).  
  - Associated IP addresses.

### **2. IP Search**  
- Input an IP address to gather:  
  - Location details.  
  - Open ports and services running on them.  
  - Associated domains or reverse DNS records.

### **3. Certificate Analysis**  
- Discover SSL/TLS certificates issued for a domain.  
- Verify certificate validity and look for expired or misconfigured certificates.

---

## **Practical Use Cases**

### **1. Reconnaissance**  
**Purpose**: Gather detailed information about a target organization.  
**Action**: Search for `example.com` to uncover subdomains, associated IPs, and DNS records.

### **2. Threat Hunting**  
**Purpose**: Identify exposed assets or misconfigured services.  
**Action**: Search for open ports on a specific IP range.

### **3. Monitoring Domain Security**  
**Purpose**: Detect changes in DNS records, certificates, or newly discovered subdomains.  
**Action**: Regularly search for updates related to a domain.

---

## **Hunter How vs Other Tools**

| **Feature**              | **Hunter How**                | **Shodan**                 | **crt.sh**                 |
|---------------------------|-------------------------------|----------------------------|----------------------------|
| **Focus**                | Comprehensive OSINT Data      | Device Metadata            | Certificate Transparency   |
| **Subdomain Enumeration**| Advanced                      | Moderate                   | Basic                      |
| **Port Scanning**        | Yes                           | Yes                        | No                         |
| **Certificate Details**  | Yes                           | Limited                    | Advanced                   |

---

## **Automating Hunter How**

### **Python Script for Domain Recon**
Below is a Python script for automating domain recon using Hunter How's API:  
```python
import requests

API_KEY = "your_api_key_here"
DOMAIN = "example.com"

url = f"https://hunter.how/api/search?domain={DOMAIN}&api_key={API_KEY}"
response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    print(f"Results for {DOMAIN}:")
    for record in data.get("records", []):
        print(record)
else:
    print(f"Error: Unable to fetch data for {DOMAIN}")
```

---

## **Practical Exercises**

### **1. Domain Reconnaissance**  
Search for a target domain (`example.com`) and analyze:  
- Subdomains.  
- DNS records.  
- Associated IPs.  

### **2. SSL/TLS Certificate Analysis**  
Find certificates issued to a domain and check for misconfigurations or expiry dates.

### **3. Threat Assessment**  
Search for open ports and services on a specific IP (`192.168.1.1`).

---

## **Ethics and Legal Considerations**

**Responsible Use**: Hunter How provides powerful OSINT capabilities that must be used responsibly. Always ensure:  
- **You have authorization** to investigate domains, IPs, or certificates.  
- **You comply with laws and regulations** related to data usage and privacy.  
- **You avoid malicious or unethical behavior** while using the tool.

---

## **Resources for Day 11**

### **Official Resources**
- [Hunter How Official Website](https://hunter.how/)  

### **Interactive Labs**
- Explore OSINT challenges on platforms like TryHackMe or HackTheBox using Hunter How.  

---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
