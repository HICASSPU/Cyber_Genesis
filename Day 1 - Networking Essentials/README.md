# **Cyber Genesis - Day 1: Networking Essentials** 🌐

Welcome to **Day 1 of the Cyber Genesis series**! 🚀  
Today, we’re diving deep into the essential concepts of **Networking**, which form the backbone of cybersecurity. Whether you’re looking to understand how data travels through networks or how to secure them, this is where your journey begins!

---

## **Key Networking Concepts to Know**

### **1. Networking Protocols**
A networking protocol is a set of rules that define how data is transmitted and received across a network. Protocols ensure seamless communication between devices and software from different manufacturers. Every layer of the network depends on protocols to establish reliable and secure communication.

#### **Important Protocols**
- **TCP/IP (Transmission Control Protocol/Internet Protocol)**  
  The core protocol suite for internet communication.  
  - **TCP** ensures data is delivered reliably and in order.  
  - **IP** handles addressing and routing packets.  
  **Why it's important**: It’s the backbone of modern communication, making devices interact efficiently over networks.  
  **Example**: When you send an email, TCP/IP ensures the email is broken into packets, sent to the recipient, and reassembled correctly.

- **UDP (User Datagram Protocol)**  
  A faster alternative to TCP but doesn’t guarantee delivery.  
  **Example use cases**: Used in real-time applications like VoIP and live streaming.  
  **Why it's important**: Crucial for scenarios where speed matters more than reliability.  
  **Example**: During a live video stream, UDP ensures the video plays continuously, even if some data packets are dropped.

- **HTTP/HTTPS (Hypertext Transfer Protocol/Secure)**  
  - **HTTP**: Protocol for data exchange on the web.  
  - **HTTPS**: Secured version of HTTP, using SSL/TLS to encrypt communication.  
  **Why it's important**: Every website uses HTTP/HTTPS; HTTPS protects sensitive data from attackers.  
  **Example**: When you log in to a bank website, HTTPS ensures your password and account details are encrypted.

- **FTP (File Transfer Protocol)**  
  Transfers files between computers over a network.  
  **Why it's important**: Widely used for uploading/downloading files to/from servers.  
  **Example**: FTP is often used by web developers to upload website files to a hosting server.

- **SMTP (Simple Mail Transfer Protocol)**  
  Sends emails between servers.  
  **Why it's important**: Essential for email communication.  
  **Example**: When you send an email from Gmail to Yahoo, SMTP ensures it’s routed between servers.

- **POP3 and IMAP**  
  Used for retrieving emails:  
  - **POP3**: Downloads emails, removing them from the server.  
  - **IMAP**: Keeps emails on the server, syncing them across devices.  
  **Why it's important**: IMAP is better for multiple devices, while POP3 works well for offline access.  
  **Example**: IMAP allows you to check the same emails on your phone and laptop.

- **DNS (Domain Name System)**  
  Translates domain names (e.g., `www.example.com`) into IP addresses.  
  **Why it's important**: Allows users to access websites using simple names instead of complex IPs.  
  **Example**: When you type `www.google.com`, DNS translates it to the IP `142.250.190.78` so your browser can connect.

---

### **2. HTTP Basics: Understanding Web Communication**
HTTP is a stateless protocol used for web communication. It enables browsers and servers to exchange data.

#### **How HTTP Works**
1. **Request**: The browser sends an HTTP request to a server for a resource (e.g., a webpage).
2. **Response**: The server sends back the resource with a status code indicating success or failure.

#### **Common HTTP Methods**
- **GET**: Retrieve data (e.g., loading a webpage).  
- **POST**: Send data to the server (e.g., form submissions).  
- **PUT**: Update existing resources.  
- **DELETE**: Remove resources.  
- **PATCH**: Partially update resources.

#### **HTTP Status Codes**
The HTTP response from the server contains a status code, which tells the client whether the request was successful or if there was an issue. Common HTTP status codes include:
- **200 OK**: The request was successful, and the server returned the requested resource.
- **404 Not Found**: The requested resource could not be found on the server.
- **500 Internal Server Error**: The server encountered an error and could not process the request.

#### **Grouping HTTP Status Codes for Simple Understanding**
- **Informational responses** (`100` – `199`)  
- **Successful responses** (`200` – `299`)  
- **Redirection messages** (`300` – `399`)  
- **Client error responses** (`400` – `499`)  
- **Server error responses** (`500` – `599`)

#### **HTTPS (HTTP Secure)**
Uses SSL/TLS encryption to protect data during transmission.  
**Why HTTPS Matters**:  
- Secures data (e.g., passwords, payments).  
- Verifies website authenticity.  
- Builds user trust (e.g., padlock in the browser bar).

---

### **3. Subnetting & Implementation Logic**
**Subnetting** divides a network into smaller, manageable sub-networks (subnets). This improves performance, security, and resource allocation.

- **Subnet Mask**: Identifies the network and host parts of an IP address.  
- **CIDR Notation**: Compact way to denote subnets (e.g., `192.168.1.0/24`).

**Example**:  
For `192.168.1.0/24`, creating 4 subnets involves borrowing 2 bits from the host portion:  
- Subnet 1: `192.168.1.0/26`  
- Subnet 2: `192.168.1.64/26`  
- Subnet 3: `192.168.1.128/26`  
- Subnet 4: `192.168.1.192/26`

#### **Advantages of Subnetting**
1. **Faster Networks**: Reduces unnecessary traffic, improving speed.  
2. **More Secure**: Separates different network areas, limiting access for attackers.  
3. **Efficient IP Use**: Avoids wasting IP addresses.  
4. **Easier Management**: Smaller networks are simpler to handle.  
5. **Scalability**: Easy to add new subnets as needed.

---

### **4. Autonomous System Number (ASN)**
An **ASN** is a unique number assigned to an Autonomous System (AS), which is a group of IP networks managed by one organization.  
- **Public ASN**: Used on the global internet.  
- **Private ASN**: Used internally within networks.

---

### **5. RFC (Request for Comments)**
RFCs define internet standards and protocols, published by the IETF.  
- **[RFC 791](https://www.rfc-editor.org/rfc/rfc791)**: Defines the Internet Protocol (IP), which handles addressing and routing data.  
- **[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616)**: Defines HTTP/1.1, the foundation of modern web communication.  
- **[RFC 2547](https://www.rfc-editor.org/rfc/rfc2547)**: Defines BGP (Border Gateway Protocol), which handles routing between autonomous systems.

---

## **Practical Implementation & Exercises**

### **HTTP Request and Response**
- Use browser tools (e.g., Chrome Developer Tools) to inspect HTTP requests/responses.  
- Test HTTP methods (e.g., GET, POST) using **Postman** or **cURL**.

### **DNS Lookup**
- Use `nslookup` or `dig` to resolve domain names to IPs.  
  **Example**: `nslookup www.google.com`.

### **Subnetting Practice**
- Divide the network `10.0.0.0/24` into smaller subnets and assign IPs.

---

## **Why Networking Matters in Cybersecurity**

Networking knowledge is critical for cybersecurity. Understanding how data travels, identifying vulnerabilities, and securing communications are key to building strong defenses.

---

## **Today’s Learning Resources**
📚 **Networking Protocols**  
- [IETF RFC Process](https://www.ietf.org/standards/)  
- [Subnetting Practice Tool](https://www.subnettingpractice.com/)  
- [Networking Tutorial - DigitalOcean](https://www.digitalocean.com/community/tutorials)  
- [Common Network Port Numbers](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)  
- **YouTube**:  
  - [Networking Tutorials Playlist 1](https://www.youtube.com/playlist?list=PL0tP8lerTbX1aNiUwl7fHlX0yS5uBgtl7)  
  - [Networking Tutorials Playlist 2](https://www.youtube.com/playlist?list=PL0tP8lerTbX1eRZGxtgTkIkoytM8KvvVG)

---

## *Created by:*

*Raman Mohurle & Varad Mene & Harsh Navgale*

---

## *Contributing*

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
