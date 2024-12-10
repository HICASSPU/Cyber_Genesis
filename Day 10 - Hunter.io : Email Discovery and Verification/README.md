# **Cyber Genesis - Day 10: Hunter.io - Email Discovery and Verification** 📧

Welcome to **Day 10 of the Cyber Genesis series!** 🚀  
Today, we’ll explore **Hunter.io**, an essential tool for discovering, verifying, and managing professional email addresses. Whether you’re performing reconnaissance, conducting OSINT investigations, or building contact lists, Hunter.io is a go-to solution. Let’s dive into its features and practical applications! 🔍

---

## **What is Hunter.io?**

**Hunter.io** is an email discovery and verification platform that collects publicly available information to identify professional email addresses associated with domains. It’s widely used for:  
- Discovering organizational email addresses.  
- Verifying email deliverability and authenticity.  
- Building and managing outreach campaigns.  

---

## **Key Features of Hunter.io**

1. **Domain Search**  
   - Finds all publicly available email addresses associated with a specific domain.  
   - Displays information like names, email patterns, and sources.

2. **Email Finder**  
   - Identifies a single email address based on a name and domain.

3. **Email Verification**  
   - Verifies the deliverability of an email address by checking:  
     - Format validity.  
     - Mail server existence.  
     - Inbox availability.

4. **Bulk Email Search**  
   - Allows you to upload domain lists or names for mass email discovery.  

5. **Campaigns**  
   - Helps manage email outreach campaigns with templates and tracking features.

---

## **How to Use Hunter.io**

### **1. Domain Search**  
- Enter the target domain (e.g., `example.com`) in the **Domain Search** bar.  
- The results include:  
  - Email addresses.  
  - Associated names and positions.  
  - Confidence scores.  
  - Sources where the email was found.

### **2. Email Finder**  
- Provide a name and domain (e.g., `John Doe` and `example.com`).  
- Hunter.io generates a likely email address (e.g., `john.doe@example.com`) with a confidence score.

### **3. Email Verification**  
- Enter an email address to verify its authenticity.  
- Hunter.io will display verification results, such as:  
  - **Valid**: Deliverable email address.  
  - **Invalid**: Nonexistent or undeliverable address.  
  - **Risky**: May exist but could result in a bounce.

### **4. Bulk Tasks**  
- Upload a list of domains, names, or email addresses for bulk discovery or verification.  
- Download results in CSV format for analysis or integration.

---

## **Practical Use Cases**

### **1. Reconnaissance**  
- Discover email addresses associated with a target organization during a penetration test or OSINT investigation.  
  **Example**: Search for emails linked to `target.com` to identify key personnel for phishing simulation or contact enumeration.

### **2. Email Verification**  
- Verify the validity of email addresses before launching email campaigns to reduce bounce rates.  

### **3. Social Engineering Preparation**  
- Identify specific email patterns (e.g., `firstname.lastname@domain.com`) to create realistic phishing emails.  

### **4. Threat Hunting**  
- Check for leaked or compromised email addresses by comparing Hunter.io results with known breach databases.

---

## **Automating Hunter.io with API**

Hunter.io provides an API for integrating its functionality into your workflows.

### **Example Python Script**
```python
import requests

API_KEY = "your_api_key_here"
DOMAIN = "example.com"

url = f"https://api.hunter.io/v2/domain-search?domain={DOMAIN}&api_key={API_KEY}"
response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    emails = data.get("data", {}).get("emails", [])
    print(f"Email addresses found for {DOMAIN}:")
    for email in emails:
        print(email["value"])
else:
    print(f"Error: Unable to fetch data for {DOMAIN}")
```

### **Automating Bulk Verification**
Use the API to verify email addresses in bulk:  
```bash
curl "https://api.hunter.io/v2/email-verifier?email=john.doe@example.com&api_key=your_api_key_here"
```

---

## **Hunter.io vs Other Tools**

| **Feature**              | **Hunter.io**                | **EmailHippo**             | **Voila Norbert**           |
|---------------------------|------------------------------|----------------------------|-----------------------------|
| **Email Discovery**       | Comprehensive                | Limited                    | Moderate                   |
| **Email Verification**    | Advanced                     | Advanced                   | Basic                      |
| **Bulk Search**           | Yes                          | Yes                        | No                         |
| **Campaign Management**   | Integrated                   | No                         | No                         |

---

## **Practical Exercises**

### **1. Domain Search**
Use Hunter.io to find all email addresses linked to a domain:  
- Search for `targetdomain.com` and analyze the results.

### **2. Verify Emails**
Enter an email address like `john.doe@target.com` to check if it’s valid.

### **3. Analyze Patterns**
Look for common patterns in email addresses (e.g., `firstname.lastname@domain.com`) to predict additional addresses.

### **4. Automate Tasks**
Use the Python script provided to automate email discovery for a list of domains.

---

## **Ethics and Legal Considerations**

**Responsible Use**: While Hunter.io is a powerful tool, it must be used responsibly. Always ensure:  
- **You have authorization** to investigate domains and email addresses.  
- **You comply** with GDPR, CAN-SPAM Act, and other email-related laws.  
- **You respect privacy** and avoid misusing the data for malicious purposes.

---

## **Resources for Day 10**

### **Official Resources**
- [Hunter.io Official Website](https://hunter.io/)  
- [Hunter.io API Documentation](https://hunter.io/api)  

### **Interactive Labs**
- Explore related labs on platforms like TryHackMe or HackTheBox.

---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
