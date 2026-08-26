# Task 2 — Web Application Security Assessment

## 📌 Overview

As part of my **Cybersecurity Internship at Alfido Tech**, I performed a practical **Web Application Vulnerability Assessment** in an isolated lab environment using **DVWA (Damn Vulnerable Web Application)**, **Kali Linux**, **Burp Suite**, and **Firefox**.

The objective was to understand how common web application vulnerabilities occur, identify vulnerable input points, analyze HTTP requests and responses, and document the security impact and recommended mitigations.

---

## 🎯 Objectives

* Set up and assess a deliberately vulnerable web application.
* Configure Burp Suite for HTTP traffic interception and analysis.
* Analyze application requests and responses.
* Identify SQL Injection vulnerabilities.
* Compare application behavior at different DVWA security levels.
* Test Reflected Cross-Site Scripting (XSS).
* Examine HTTP headers and information disclosure.
* Document findings with screenshots and HTTP evidence.
* Understand appropriate security controls and remediation techniques.

---

## 🛠️ Tools & Technologies

| Tool / Technology                | Purpose                                         |
| -------------------------------- | ----------------------------------------------- |
| **Kali Linux**                   | Security testing environment                    |
| **DVWA v1.0.7**                  | Deliberately vulnerable web application         |
| **Burp Suite Community Edition** | HTTP interception and request/response analysis |
| **Mozilla Firefox**              | Web application testing                         |
| **Apache**                       | Web server                                      |
| **PHP / MySQL**                  | Application backend                             |
| **Virtual Network**              | Isolated testing environment                    |

### Target

```text
http://192.168.56.102/dvwa/
```

---

## 🔍 Vulnerabilities / Security Issues Identified

### 1. SQL Injection

The DVWA SQL Injection module was tested by manipulating the `id` parameter.

A SQL Injection test successfully caused the application to return multiple database records at the **Low** security level.

**Status:** Confirmed
**Severity:** High

---

### 2. Reflected Cross-Site Scripting (XSS)

The Reflected XSS functionality was tested using the vulnerable `name` parameter.

The supplied input was reflected by the application and resulted in JavaScript execution in the browser.

**Status:** Confirmed
**Severity:** Medium

---

### 3. Information Disclosure

HTTP response analysis revealed technology and version information, including:

```text
Server: Apache/2.2.8 (Ubuntu)
X-Powered-By: PHP/5.2.4-2ubuntu5.10
```

This information may assist an attacker in identifying the underlying technology stack.

**Status:** Observed
**Severity:** Low

---

### 4. Database Error Disclosure

During SQL Injection testing, the application exposed a MySQL syntax error to the browser.

This demonstrates improper handling of database errors and provides information about the application's backend.

**Status:** Confirmed
**Severity:** Medium

---

## 🧪 Testing Performed

### SQL Injection

* Established normal application behavior.
* Tested the SQL Injection input at Low security.
* Captured the request using Burp Suite.
* Verified that multiple records were returned.
* Changed the DVWA security level to Medium.
* Compared application behavior.
* Observed database error behavior during testing.
* Examined the corresponding HTTP responses.

### Reflected XSS

* Located the vulnerable input parameter.
* Intercepted the HTTP request using Burp Suite.
* Tested reflected input handling.
* Verified JavaScript execution in the browser.
* Examined the reflected input within the HTTP response.

### HTTP Analysis

* Examined HTTP requests and responses.
* Reviewed cookies and request headers.
* Identified server and PHP version disclosure.
* Used Burp Suite HTTP History to maintain testing evidence.

---

## 📊 Preliminary Findings

| ID   | Finding                   | Severity | Status    |
| ---- | ------------------------- | -------- | --------- |
| F-01 | SQL Injection             | High     | Confirmed |
| F-02 | Reflected XSS             | Medium   | Confirmed |
| F-03 | Information Disclosure    | Low      | Observed  |
| F-04 | Database Error Disclosure | Medium   | Confirmed |

---

## 🛡️ Recommended Mitigations

### SQL Injection

* Use prepared statements and parameterized queries.
* Validate and sanitize user input.
* Avoid directly concatenating user input into SQL queries.
* Apply least-privilege database permissions.
* Prevent database errors from being displayed to users.

### Reflected XSS

* Properly encode user-controlled output.
* Validate input on the server side.
* Avoid inserting untrusted input directly into HTML.
* Implement an appropriate Content Security Policy.

### Information Disclosure

* Remove unnecessary server and software version information.
* Disable detailed errors in production environments.
* Return generic error messages to users.
* Keep detailed technical errors in protected server-side logs.

---

## 📸 Evidence

Screenshots documenting the assessment are stored in the:

```text
screenshots/
```

directory.

The evidence includes:

* DVWA login and configuration
* Burp Suite HTTP interception
* SQL Injection testing
* SQL Injection results
* Burp Suite SQL Injection request/response
* DVWA security-level changes
* Reflected XSS execution
* Burp Suite XSS analysis
* Database error disclosure
* HTTP header analysis

---

## ⚠️ Disclaimer

This assessment was performed against a **deliberately vulnerable DVWA application in an isolated lab environment** for cybersecurity learning and internship purposes.

No unauthorized external systems or public websites were targeted.

---

---

**Repository:** `Alfido-Tech-Cybersecurity-Internship`
**Task:** `Task-2-Web-Application-Security`

