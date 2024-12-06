
# **Cyber Genesis - Day 7: Censys: The Search Engine for Internet Assets** 🌐

Welcome to **Day 7 of the Cyber Genesis series!** 🚀  
Today, we’re exploring **Censys**, an advanced search engine designed for discovering and analyzing internet assets. Censys specializes in identifying devices, services, and vulnerabilities across the internet, making it an essential tool for cybersecurity professionals. Let’s dive in! 🔍

---

## **What is Censys?**

**Censys** is a search engine that collects, analyzes, and indexes internet-facing systems, including servers, devices, and certificates. Unlike Shodan, which focuses on banners and device metadata, Censys provides detailed insights into the protocols, configurations, and vulnerabilities of internet assets.

---

## **Key Features of Censys**

1. **Internet-Wide Scans**  
   - Censys scans the entire IPv4 address space to discover internet-facing devices and services.  
   - Provides detailed protocol-level insights for ports like HTTP, HTTPS, SMTP, and more.

2. **SSL/TLS Certificate Search**  
   - Find SSL certificates issued to domains and identify potential misconfigurations.  
   - Analyze certificates for expiration, Common Name (CN), or fingerprint.

3. **Query Language**  
   - Use a powerful query language to filter results by IP, protocol, port, certificate details, and vulnerabilities.

4. **Vulnerability Insights**  
   - Identify exposed services and vulnerabilities, such as open databases, outdated software, or unpatched systems.

5. **Reports and Monitoring**  
   - Set up **Censys Alerts** to monitor specific IP ranges, domains, or queries for changes or new vulnerabilities.

---

## **Censys Query Language**

Censys uses an advanced query language to filter and refine searches. Below are some commonly used filters and examples:

### **Basic Filters**
1. **Search by IP Address**  
   ```plaintext
   ip:192.168.1.1
   ```

2. **Search by Port**  
   ```plaintext
   services.port:443
   ```

3. **Search by Protocol**  
   ```plaintext
   services.service_name:"http"
   ```

4. **Search by Domain**  
   ```plaintext
   domain:"example.com"
   ```

### **Advanced Filters**
1. **SSL Certificate Details**  
   - Search for certificates issued to a specific domain:  
     ```plaintext
     services.tls.certificates.leaf_data.subject.common_name:"example.com"
     ```  
   - Find certificates with specific fingerprints:  
     ```plaintext
     services.tls.certificates.leaf_data.fingerprint_sha256:"<fingerprint>"
     ```

2. **Vulnerable Systems**  
   - Identify systems with open Redis databases:  
     ```plaintext
     services.service_name:"redis"
     ```  
   - Search for systems running outdated software:  
     ```plaintext
     services.software.version:<specific_version>
     ```

3. **Combining Filters**  
   Combine multiple filters to refine searches:  
   ```plaintext
   services.port:22 AND services.service_name:"ssh"
   ```

---

## **Practical Use Cases**

### **1. Asset Discovery**  
- Identify all exposed services for a specific organization or domain.  
  Example:  
  ```plaintext
  autonomous_system.organization:"Your Organization"
  ```

### **2. Vulnerability Assessment**  
- Search for outdated or vulnerable systems.  
  Example:  
  ```plaintext
  services.software.product:"nginx" AND services.software.version<"1.19"
  ```

### **3. Certificate Analysis**  
- Locate misconfigured or expired SSL certificates.  
  Example:  
  ```plaintext
  services.tls.certificates.validation_level:"expired"
  ```

### **4. Monitoring and Alerts**  
- Set up alerts to track specific domains, IP ranges, or services for changes or vulnerabilities.

---

## **Censys CLI**

Censys also offers a **Command-Line Interface (CLI)** to perform queries, download results, and automate tasks.

### **Installation**
Install the Censys CLI using Python’s pip:  
```bash
pip install censys
```

### **Key Commands**
1. **Set Up API Key**  
   Add your Censys API key to the CLI:  
   ```bash
   censys config
   ```

2. **Run Queries**  
   Perform a search query from the command line:  
   ```bash
   censys search services.port:443
   ```

3. **Export Results**  
   Save query results to a file for analysis:  
   ```bash
   censys search services.service_name:"http" --output results.json
   ```

4. **View Account Information**  
   Check your API usage and account details:  
   ```bash
   censys account
   ```

---

## **Censys vs. Shodan**

| **Feature**            | **Censys**                          | **Shodan**                          |
|-------------------------|--------------------------------------|--------------------------------------|
| **Focus**              | Detailed protocol-level insights    | Device banners and metadata         |
| **Vulnerability Search**| Comprehensive                      | Basic                                |
| **Certificate Search** | Advanced certificate analysis       | Limited                             |
| **Monitoring**         | Alerts for domains and IP ranges    | Alerts for IP ranges                |
| **Query Language**     | Advanced                            | Moderate                            |

---

## **Practical Exercises**

### **1. Search for HTTPS Servers**
Run a query to identify HTTPS servers:  
```plaintext
services.service_name:"https"
```

### **2. Find Exposed Databases**
Search for open MongoDB databases:  
```plaintext
services.service_name:"mongodb"
```

### **3. Analyze SSL Certificates**
Find expired SSL certificates for a specific domain:  
```plaintext
services.tls.certificates.leaf_data.subject.common_name:"example.com" AND services.tls.certificates.validation_level:"expired"
```

---

## **Ethics and Legal Considerations**

**Responsible Use**: Like Shodan, Censys is a powerful tool that must be used responsibly. Ensure that:  
- **You have authorization** to assess systems you search.  
- **Your actions comply** with applicable laws and regulations.  
- **You respect privacy** and avoid exploiting sensitive information.

---

## **Resources for Day 7**

### **Official Resources**
- [Censys Official Website](https://censys.io/)  
- [Censys API Documentation](https://censys.io/api)  

### **Blogs**
- [Censys Intro Blog](https://warnerchad.medium.com/censys-search-engine-intro-d502d9839c1c) 

### **YouTube Tutorials**
- [Censys for Beginners](https://www.youtube.com/watch?v=6kuS_AFTcAM&list=PLM4JFCZlajSt5MLFlrnkRMNP9kZxtZ3mv)
---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
