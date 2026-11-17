# SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

**Platform:** PortSwigger Web Security Academy
**Category:** SQL Injection (SQLi)
**Severity:** High

---

## 📝 Description
This lab contains a SQL injection vulnerability in the product category filter. When a user selects a category, the application executes a SQL query which contains the user input in the WHERE clause. This allows an attacker to manipulate the query.

## 🚀 Steps to Reproduce
1. Navigated to the lab and clicked on a product category (e.g., Gifts).
2. Intercepted the request in **Burp Suite Professional**.
3. Modified the `category` parameter by appending the payload: `' OR 1=1--`
4. Forwarded the request. The application returned all products, including unreleased ones.

## 💥 Impact
An attacker can bypass application logic to retrieve sensitive data, including hidden products, user details, or other confidential information from the database.

## 📸 Proof of Concept (PoC)
![SQLi Hidden Data](sqli-hidden.png)

## 🛡️ Remediation (Fix)
1. **Parameterized Queries:** Use prepared statements to ensure user input is treated as data, not code.
2. **Input Validation:** Implement strict server-side validation for all input fields.
