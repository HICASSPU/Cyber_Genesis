
 # **Cyber Genesis - Day 4: Web Fundamentals** 🌐
 ---

Welcome to **Day 4 of the Cyber Genesis series!** 🚀  
Today, we explore the **Web Fundamentals**, the essential building blocks of the modern internet. Understanding web technologies is critical for both securing applications and identifying potential vulnerabilities.

---

## **What You’ll Learn**

### **1. HTML (HyperText Markup Language)**  
- The backbone of web pages, used to structure content.  
- **Key Elements**:  
  - `<html>`, `<head>`, `<body>`: The basic structure of a web page.  
  - `<div>`, `<span>`: Grouping and organizing content.  
  - `<a>`, `<img>`: Adding links and images.
    
**Example**:  

```markdown

<html>
  <head>
    <title>My First Web Page</title>
  </head>
  <body>
    <h1>Welcome to Cyber Genesis!</h1>
    <p>This is a simple web page using HTML.</p>
  </body>
</html>
```

---

### **2. CSS (Cascading Style Sheets)**  
- Adds style and layout to HTML pages.  
- **Key Concepts**:  
  - **Selectors**: Target HTML elements for styling (e.g., `div`, `.class`, `#id`).  
  - **Properties**: Control appearance (e.g., `color`, `margin`, `padding`).  
  - **Responsive Design**: Use media queries to create mobile-friendly designs.  

**Example**:  
```css
body {
  background-color: #f9f9f9;
  font-family: Arial, sans-serif;
}
h1 {
  color: #0056b3;
}
```

---

### **3. JavaScript (JS)**  
- A scripting language for interactivity and logic on web pages.  
- **Key Features**:  
  - Manipulating the DOM (Document Object Model).  
  - Handling user events (e.g., clicks, form submissions).  
  - Fetching data asynchronously using APIs (e.g., `fetch`).  

**Example**:  
```javascript
document.getElementById("myButton").addEventListener("click", function() {
  alert("Button Clicked!");
});
```

---

### **4. HTTP/HTTPS (Web Communication)**  
- **HTTP**: The protocol for transferring data on the web.  
- **HTTPS**: Secures HTTP communication with encryption (SSL/TLS).  
- **Key Concepts**:  
  - **Request Methods**: GET, POST, PUT, DELETE.  
  - **Status Codes**: 200 OK, 404 Not Found, 500 Internal Server Error.  

**Example**:  
Use browser developer tools to inspect HTTP requests and responses.

---

### **5. Cookies & Sessions**  
- **Cookies**: Small pieces of data stored on the client’s browser to maintain state.  
- **Sessions**: Server-side storage of user data for secure interactions.  
- **Example Use Case**: Storing user preferences or managing login sessions.

---

## **Practical Exercises**

### **1. Build a Simple Web Page**
- Create an HTML file with the basic structure.  
- Add a styled heading and paragraph using CSS.  
- Use JavaScript to add interactivity (e.g., a button that shows an alert).

### **2. Explore HTTP Requests**
- Open browser developer tools (F12) and inspect the **Network** tab.  
- Observe how resources (e.g., images, scripts) are requested and loaded.  
- Use tools like **Postman** or **cURL** to test HTTP methods (GET, POST).

### **3. Experiment with Cookies**
- Set and retrieve cookies in your browser console using JavaScript.  
```javascript
document.cookie = "user=CyberGenesis; expires=Fri, 31 Dec 2024 23:59:59 GMT";
console.log(document.cookie);
```

---

## **Resources for Day 4**

### **Interactive Labs**
- [DNS in Detail - TryHackMe](https://tryhackme.com/r/room/dnsindetail)  
- [HTTP in Detail - TryHackMe](https://tryhackme.com/r/room/httpindetail)  
- [How Websites Work - TryHackMe](https://tryhackme.com/r/room/howwebsiteswork)  
- [Putting It All Together - TryHackMe](https://tryhackme.com/r/room/puttingitalltogether)  

### **Guides and Documentation**
- [HTML Basics - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTML)  
- [CSS Fundamentals - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/CSS)  
- [JavaScript Guide - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)  
- [HTTP Basics - DigitalOcean](https://www.digitalocean.com/community/tutorials/an-introduction-to-http-and-rest)  
- [Web Basic Concepts - TutorialsPoint](https://www.tutorialspoint.com/web_developers_guide/web_basic_concepts.htm)  

### **Video Tutorials**
- [HTML, CSS & JavaScript for Beginners](https://www.youtube.com/playlist?list=PL0tP8lerTbX2b6uoTk8c17aSDueOymJYZ)  
- [Understanding HTTP](https://www.youtube.com/playlist?list=PL0tP8lerTbX2VuN9XZZdmHTfDwjeHji8p)

---

## **Created by:**

**Varad Mene**

---

## **Contributing**

Feel free to contribute by suggesting edits, adding more resources, or sharing your learning experiences.
