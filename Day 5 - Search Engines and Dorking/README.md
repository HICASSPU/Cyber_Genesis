# **Cyber Genesis - Day 5: Search Engine and Dorking** 🔍

Welcome to **Day 5 of the Cyber Genesis series!** 🚀  
Today, we’ll explore the fascinating world of **Search Engines and Dorking**, a powerful reconnaissance technique used in cybersecurity and OSINT. Dorking involves crafting advanced search queries to extract specific information from public sources. Let’s dive in!

---

## **1. What is Dorking?**

**Dorking** (also known as Google Hacking) is a technique used to extract sensitive or hidden information from public search engines by using advanced operators and specific search queries. This method takes advantage of misconfigurations, indexing errors, and poorly managed data on websites.

### **Key Uses of Dorking**:
- Identifying exposed sensitive files (e.g., `.pdf`, `.xls`, `.doc`).  
- Finding login portals, admin panels, or error pages.  
- Searching for misconfigured databases or IoT devices.  
- Gathering reconnaissance data during penetration testing or OSINT investigations.

### **Examples of Dorking**:
- Find confidential PDFs: `site:example.com filetype:pdf confidential`  
- Discover login pages: `inurl:login site:example.com`  
- Exposed directories: `intitle:"index of" "passwords"`

---

## **2. 20 Common Dorks**

Below are 20 useful dorks categorized by their purpose:

### **File Discovery**:
1. `filetype:pdf site:example.com` - Search for PDF files on a site.  
2. `filetype:docx confidential` - Find Word documents marked as confidential.  
3. `filetype:xls "email"` - Look for Excel files containing email addresses.

### **Open Directories**:
4. `intitle:"index of" "backup"` - Find directories containing backups.  
5. `intitle:"index of" "private"` - Locate private directories.

### **Login Pages**:
6. `inurl:admin site:example.com` - Search for admin login pages on a site.  
7. `intitle:"login" site:example.com` - Locate general login pages.

### **Configuration Files**:
8. `filetype:env DB_PASSWORD` - Look for `.env` files exposing database credentials.  
9. `filetype:yaml credentials` - Discover YAML files containing credentials.  

### **Vulnerable Devices**:
10. `inurl:camera intitle:"webcam"` - Search for exposed webcams.  
11. `port:21 ftp` - Discover open FTP servers using Shodan.

### **Exposed APIs**:
12. `inurl:api` - Find public-facing API endpoints.  
13. `filetype:json api_key` - Search for exposed API keys in JSON files.

### **Error Messages**:
14. `intitle:"error" "sql syntax"` - Find SQL error messages that reveal database structure.  
15. `intitle:"error" "404"` - Locate broken links or error pages.

### **Sensitive Pages**:
16. `site:example.com "confidential"` - Search for pages marked as confidential.  
17. `site:example.com "not for public distribution"` - Locate restricted content.

### **Usernames and Passwords**:
18. `filetype:txt "username" "password"` - Find text files with potential credentials.  
19. `inurl:password filetype:log` - Discover log files containing passwords.

### **Source Code**:
20. `filetype:php site:example.com` - Locate PHP files on a specific site.

---

## **3. Dorking on Common Search Engines**

### **1. Google**
Google is the most popular and versatile search engine for dorking. It supports advanced operators like `site:`, `intitle:`, `inurl:`, `filetype:`, and `cache:`.

**Pros**:  
- Vast index covering most of the web.  
- Supports advanced and complex queries.  

**Cons**:  
- May block automated queries or frequent searches.

### **2. Bing**
Bing is a great alternative to Google and often yields different results because of its indexing algorithm.

**Unique Features**:  
- Supports similar operators like `site:` and `filetype:`.  
- Offers results that may not appear on Google due to different indexing policies.

### **3. DuckDuckGo**
DuckDuckGo prioritizes privacy and does not track user data. It provides slightly different results and respects user anonymity.

**Key Features**:  
- **Bang Commands**: Use `!g` to search Google or `!b` to search Bing directly.  
- Useful for OSINT when privacy is a concern.  

---

## **4. Why Use Multiple Search Engines?**

Using multiple search engines for the same task ensures:  
- **Comprehensive Results**: Each search engine uses a different indexing algorithm, providing varied results.  
- **Bypassing Restrictions**: Some content may be excluded from Google but appear on Bing or DuckDuckGo.  
- **Enhanced Privacy**: Using privacy-focused engines like DuckDuckGo prevents tracking and profiling.
  
---

## **Practical Exercises**

### **1. Google Dorking Challenge**
- Use Google to find publicly accessible login pages or directories.  
- Example: `site:example.com inurl:admin`.

### **2. Compare Results Across Search Engines**
- Perform the same query (e.g., `filetype:pdf site:example.com`) on Google, Bing, and DuckDuckGo.  
- Note differences in the results and identify the most comprehensive engine for your needs.

---

## **Resources for Day 5**

### **Guides and Cheat Sheets**
- [Google Dorking Cheat Sheet - Exploit-DB](https://www.exploit-db.com/google-hacking-database)   

### **Search Engine Links**
- [Google Advanced Search](https://www.google.com/advanced_search)  
- [Bing Search](https://www.bing.com)  
- [DuckDuckGo](https://duckduckgo.com/)
- [Bug Bounty Helper](https://dorks.faisalahmed.me/)
- [Mr.dorker](https://mr-dorker.onrender.com/login)  

### **YouTube Tutorials**
- [Google Dorking Basics](https://www.youtube.com/playlist?list=PL0tP8lerTbX1bDQ2K1LhRXk1mHQ1ePhVj)  

---

## **Created by:**

**Raman Mohurle & Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.

## **Upcoming!!**

**Specialized search engines with detailed information will be updated in the coming days. Stay tuned!**
