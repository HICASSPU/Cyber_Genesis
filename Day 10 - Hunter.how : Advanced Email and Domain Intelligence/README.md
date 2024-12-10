# **Cyber Genesis - Day 10: Hunter.how - Advanced Email and Domain Intelligence** 📧

Welcome to **Day 10 of the Cyber Genesis series!** 🚀  
Today, we’re exploring **Hunter.how**, a tool for email and domain reconnaissance. Hunter.how provides valuable insights into email addresses, associated domains, and their infrastructure, making it an essential tool for OSINT, penetration testing, and red teaming. Let’s wrap up this series with this powerful platform! 🔍

---

## **What is Hunter.how?**

**Hunter.how** is an advanced reconnaissance tool for collecting information about email addresses and domains. It enables cybersecurity professionals and researchers to:  
1. Discover publicly available email addresses associated with a target domain.  
2. Analyze domain infrastructure, including mail servers, DNS records, and SPF/DKIM configurations.  
3. Verify the validity of email addresses for potential use in phishing simulations or social engineering awareness.  

---

## **Key Features of Hunter.how**

1. **Email Address Discovery**  
   - Find email addresses associated with a specific domain.  
   - Extract patterns for email generation (e.g., `firstname.lastname@example.com`).  

2. **Domain Intelligence**  
   - Analyze mail server configurations (MX records, SPF, DKIM, DMARC).  
   - Identify potential vulnerabilities in email infrastructure.  

3. **Email Validation**  
   - Verify whether an email address exists and is deliverable.  

4. **Search Filters**  
   - Refine results based on job titles, departments, or keywords (e.g., `CEO@example.com`).  

5. **Exporting Results**  
   - Download search results for reporting and analysis.  

---

## **How to Use Hunter.how**

1. **Search for Email Addresses by Domain**  
   - Visit [Hunter.how](https://hunter.how/).  
   - Enter your target domain (e.g., `example.com`) in the search bar.  
   - The results will display email addresses, associated names, and sources.

2. **Analyze Domain Infrastructure**  
   - Check MX, SPF, DKIM, and DMARC records to assess email security.  

3. **Email Verification**  
   - Validate email addresses to check their existence and deliverability.  

4. **Filter Results**  
   - Use filters to search for specific roles or departments (e.g., `admin@example.com` or `HR@example.com`).  

---

## **Practical Use Cases**

### **1. OSINT for Reconnaissance**  
**Purpose**: Gather publicly available email addresses for a target organization.  
**Example**:  
Search for `example.com` to find:  
- `admin@example.com`  
- `john.doe@example.com`  

### **2. Social Engineering Preparation**  
**Purpose**: Identify high-value targets for simulated phishing campaigns.  
**Example**: Filter results to find C-suite executives or IT staff.  

### **3. Domain Email Security Audit**  
**Purpose**: Assess the email infrastructure of a domain for misconfigurations.  
**Example**: Check SPF, DKIM, and DMARC records to identify gaps in email security.  

### **4. Email Validation**  
**Purpose**: Verify if email addresses are valid and active.  
**Action**: Use the email validation feature to check if `ceo@example.com` exists.  

---

## **Automating Hunter.how Searches**

### **Python Script for Email Discovery**
Below is a Python script to automate email address discovery using Hunter.how’s API:  

```python
import requests

API_KEY = "your_api_key_here"
domain = input("Enter the target domain: ")

def search_emails(domain):
    url = f"https://hunter.how/api/v1/search?domain={domain}&api_key={API_KEY}"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        for result in data['emails']:
            print(f"Email: {result['value']} | Name: {result['first_name']} {result['last_name']}")
    else:
        print(f"Error: {response.status_code} - Unable to fetch results.")

search_emails(domain)
```

### **Bash Script for Quick Results**
Use **curl** to fetch emails from a domain:  
```bash
curl -s "https://hunter.how/api/v1/search?domain=example.com&api_key=your_api_key_here" | jq '.emails[] | .value'
```

---

## **Hunter.how vs Other Tools**

| **Feature**             | **Hunter.how**                 | **EmailPermutator**           | **OSINT Framework Tools**     |
|--------------------------|-------------------------------|--------------------------------|--------------------------------|
| **Email Discovery**      | Advanced                     | Limited                       | Varies by tool                |
| **Email Validation**     | Yes                          | No                            | No                            |
| **Domain Infrastructure**| Detailed Insights            | Not Available                 | Limited                       |
| **Filters**              | Role-Based                   | Not Applicable                | Moderate                      |
| **Ease of Use**          | Simple Web & API Access      | Basic Tool                    | Depends on the framework      |

---

## **Practical Exercises**

### **1. Discover Email Patterns**  
Search for emails at `example.com` to identify patterns like:  
```plaintext
firstname.lastname@example.com
```

### **2. Perform Email Validation**  
Verify if `ceo@example.com` is active and deliverable.

### **3. Analyze Domain Email Security**  
Check SPF, DKIM, and DMARC configurations for a domain.  

---

## **Ethics and Legal Considerations**

**Responsible Use**: Hunter.how is a powerful tool for gathering email and domain intelligence but must be used responsibly. Ensure that:  
- **You have authorization** for the domains you are analyzing.  
- **You respect privacy** and do not misuse sensitive information.  
- **Your actions comply** with applicable laws and regulations.  

---

## **Resources for Day 10**

### **Official Resources**
- [Hunter.how](https://hunter.how/) - Advanced Email and Domain Intelligence Tool.  
- [Hunter.how API Documentation](https://hunter.how/api).  

### **Interactive Labs**
- Explore tools and platforms like TryHackMe for email OSINT challenges.  

---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
