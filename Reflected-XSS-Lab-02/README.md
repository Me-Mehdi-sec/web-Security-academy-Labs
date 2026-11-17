# Reflected XSS into HTML context with nothing encoded

**Platform:** PortSwigger Web Security Academy
**Category:** Cross-Site Scripting (XSS)
**Severity:** Medium

---

## 📝 Description
This lab contains a reflected cross-site scripting vulnerability in the search functionality. The application takes user input and reflects it directly into the HTML response without proper sanitization or encoding.

## 🚀 Steps to Reproduce
1. Navigated to the lab and tested the search function.
2. Intercepted the HTTP request in **Burp Suite Professional**.
3. Observed that the search term was reflected directly in the HTML body.
4. Injected the following payload into the search bar: 
   `<script>alert(1)</script>`
5. The browser executed the script and displayed an alert box.

## 💥 Impact
If this were a real application, an attacker could craft a malicious URL containing a JavaScript payload. If a victim clicks this link, the script executes in their browser, allowing the attacker to steal session cookies (Session Hijacking) or perform actions on behalf of the user.

## 📸 Proof of Concept (PoC)
![XSS Alert Popup](Screenshot%202026-10-15%20114150.png)

## 🛡️ Remediation (Fix)
1. **HTML Output Encoding:** The application should encode user input before reflecting it on the page (e.g., `<` becomes `&lt;`).
2. **Content Security Policy (CSP):** Implement a strict CSP to prevent inline scripts from executing.
3. **Input Validation:** Validate and sanitize all user-supplied data on the server side.
Author: Mr Mehdi - Aspiring Bug Bounty Hunter 
