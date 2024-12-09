
# **Cyber Genesis - Day 9 : crt.sh - Exploring Certificate Transparency Logs** 🔐

Welcome to **Day 9 of the Cyber Genesis series!** 🚀  
Today, we’ll explore **crt.sh**, a powerful tool for accessing **Certificate Transparency (CT) logs**. This search engine provides insights into SSL/TLS certificates issued for specific domains, making it a vital resource for discovering subdomains, monitoring domain security, and identifying potential misconfigurations. Let’s dive in! 🌐

---

## **What is crt.sh?**

**crt.sh** is a free online platform that provides access to **Certificate Transparency (CT) logs**, which are public records of SSL/TLS certificates issued by Certificate Authorities (CAs).  
It allows users to:  
1. Discover **subdomains** linked to a target domain.  
2. Monitor unauthorized or rogue certificates issued for their domain.  
3. Analyze certificate details, such as issuer, validity, and fingerprints.  

---

## **Key Features of crt.sh**

1. **Subdomain Enumeration**  
   - Lists all subdomains associated with a target domain by searching for SSL/TLS certificates.  

2. **Certificate Details**  
   - Provides detailed information about certificates, including:  
     - Issuer.  
     - Validity period.  
     - Serial number and fingerprints.  

3. **Rogue Certificate Detection**  
   - Identifies suspicious or unauthorized certificates issued for a domain.  

4. **Historical Data**  
   - Tracks the history of certificates issued for a domain, making it useful for monitoring changes.  

---

## **How to Use crt.sh**

1. **Search for Certificates by Domain**  
   - Visit [crt.sh](https://crt.sh/).  
   - Enter your target domain (e.g., `example.com`) in the search bar.  
   - The results will display certificates issued for the domain, including subdomains.

2. **Filter Results**  
   - Use advanced queries to refine your searches:  
     - `%.example.com`: Search for all subdomains of `example.com`.  
     - `%example.com`: Search for `example.com` and any subdomains.  

3. **Analyze Results**  
   - Click on a certificate to view detailed information, such as:  
     - Issuer Organization.  
     - Validity period (start and expiry dates).  
     - Public Key Algorithm.  
     - Certificate fingerprints (SHA256, SHA1, MD5).  

---

## **Practical Use Cases**

### **1. Subdomain Enumeration**  
**Purpose**: Identify subdomains associated with a target domain for reconnaissance.  
**Example**:  
Search for `%.example.com` on crt.sh to uncover subdomains like:  
- `admin.example.com`  
- `mail.example.com`  
- `api.example.com`  

### **2. Monitoring Domain Security**  
**Purpose**: Detect unauthorized or rogue certificates issued for your domain.  
**Action**: Regularly search for your domain on crt.sh to identify certificates that shouldn’t exist.  

### **3. Investigating Certificate Misconfigurations**  
**Purpose**: Ensure certificates are issued by trusted Certificate Authorities (CAs) and are valid.  
**Example**: Verify that certificates for `example.com` are issued by legitimate providers like Let’s Encrypt or DigiCert.

---

## **Automating crt.sh with Scripts**

### **Python Script for Subdomain Enumeration**
Below is a Python script that automates subdomain enumeration using crt.sh:  
```python
import requests
from bs4 import BeautifulSoup

def fetch_subdomains(domain):
    url = f"https://crt.sh/?q=%25.{domain}&output=json"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        subdomains = set()
        for entry in data:
            subdomains.add(entry['name_value'])
        return subdomains
    else:
        print(f"Error: Unable to fetch data for {domain}")
        return []

domain = input("Enter the domain: ")
subdomains = fetch_subdomains(domain)

if subdomains:
    print(f"Subdomains for {domain}:")
    for subdomain in sorted(subdomains):
        print(subdomain)
else:
    print(f"No subdomains found for {domain}.")
```

### **Automating with Bash**  
You can use tools like **curl** to fetch results from crt.sh in the terminal:  
```bash
curl -s "https://crt.sh/?q=%.example.com&output=json" | jq '.[] | .name_value' | sort -u
```

---

## **crt.sh vs Other Tools**

| **Feature**            | **crt.sh**                   | **Sublist3r**                | **Amass**                     |
|-------------------------|------------------------------|------------------------------|--------------------------------|
| **Focus**              | Certificate Transparency Logs| Subdomain Enumeration        | Comprehensive Enumeration     |
| **Real-Time Monitoring**| No                           | No                           | Yes                            |
| **Ease of Use**         | Web Interface & Scripts      | CLI Tool                     | CLI/Automated                 |
| **Historical Data**     | Extensive                   | Limited                      | Limited                       |

---

## **Practical Exercises**

### **1. Find Subdomains**  
Search for all subdomains of a target domain:  
```plaintext
%.example.com
```

### **2. Detect Rogue Certificates**  
Regularly monitor crt.sh for unauthorized certificates issued for your domain.  

### **3. Analyze Historical Data**  
Use crt.sh to track how your organization’s certificates have evolved over time.  

---

## **Ethics and Legal Considerations**

**Responsible Use**: crt.sh is a powerful tool for reconnaissance and monitoring but must be used responsibly. Ensure that:  
- **You have authorization** to analyze the domain(s) you are investigating.  
- **You respect privacy** and do not misuse sensitive data.  
- **Your actions comply** with applicable laws and regulations.  

---

## **Resources for Day 9**

### **Official Resources**
- [crt.sh](https://crt.sh/) - Certificate Transparency Search Engine.  

### **Interactive Labs**
- Explore tools and platforms like TryHackMe or HackTheBox to practice subdomain enumeration.  

### **YouTube Tutorials**
- [crt.sh for Beginners](https://youtu.be/x-IUl6LgINw?si=bgH6zMYXfvQgfDL9)  
---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
