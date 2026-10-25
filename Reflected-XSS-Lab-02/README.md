# Reflected XSS into HTML context with nothing encoded

**Platform:** PortSwigger Web Security Academy
**Lab:** Lab #2 - Reflected XSS
**Category:** Cross-Site Scripting (XSS)
**Status:** Solved ✅

### Vulnerability
Search function me user input encode nahi ho raha tha, jiski wajah se attacker ka payload execute ho gaya.

### Payload Used
<script>alert(1)</script>

### Mitigation
1. HTML Output Encoding
2. Content Security Policy (CSP)
3. Input Validation
### Proof of Concept

![Lab Proof](Screenshot%202026-10-15%20114150.png)

> Lab successfully solved - alert(1) executed!
   

### Learning
Output encoding ka importance aur reflection points kaise find karte hain.

---
Author: Mr Mehdi - Aspiring Bug Bounty Hunter 
