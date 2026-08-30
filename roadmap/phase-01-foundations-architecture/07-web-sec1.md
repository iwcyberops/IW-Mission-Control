<!-- 🚩 FLAG: This is Month 7 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 7: Advanced Web Security I – Server-Side Vulnerability Analysis

> **🎯 Primary Outcome:** Develop manual web vulnerability discovery skills, bypass input filters, and construct robust server-side exploits.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Advanced SQL Injection:** Boolean-based blind extraction, time-based blind timing channels, out-of-band (OAST) exfiltration, second-order SQLi, bypassing WAF keyword filters.
*   **Broken Object Level Authorization (BOLA/IDOR):** Multi-tenant authorization bypasses, UUID predictability, authorization matrix mapping, state-changing verb manipulation.
*   **Server-Side Request Forgery (SSRF):** Bypassing blacklists via DNS rebinding, exploiting cloud metadata APIs (AWS IMDSv1 vs IMDSv2, GCP, Azure), protocol smuggling via `gopher://`.
*   **XML External Entity (XXE):** Billion Laughs DOS, local file retrieval via system entities, blind out-of-band exfiltration using parameter entities.
*   **Server-Side Template Injection (SSTI):** Template engine identification (Jinja2, Twig, Freemarker, Velocity), sandbox escape payloads, achieving Remote Code Execution (RCE).

---

### 🛠️ 2. Tools & Operational Environment

`Burp Suite Professional / Community` | `ffuf` | `sqlmap` | `Turbo Intruder` | `Interactsh` | `Docker`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Complete advanced PortSwigger Web Security Academy labs covering SQLi, SSRF, XXE, and SSTI.
*   **Hour 05 (C Track):** Write basic C parsers; validate input sanitization routines against buffer overflows.
*   **Hour 06 (ASM Track):** Analyze compiled web backend C modules (e.g., NGINX modules) in Ghidra.
*   **Hour 07 (Hardware Track):** Study physical network interfaces (NICs), MAC filtering, and hardware-level packet processing.
*   **Hours 08–10 (Lab):** Build custom Python automated exploit scripts extracting data through blind SQLi and SSRF channels.
*   **Hour 11 (Reading):** Read OWASP Web Security Testing Guide (WSTG) sections on Input Validation and Authorization.
*   **Hour 12 (Documentation):** Document vulnerability impact, CVSS 3.1 scoring, and exact remediation code for every web lab solved.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Custom Automated Blind SQLi Engine:** Write an asynchronous Python script that extracts database tables via binary search timing attacks.
2.  **Deliberately Vulnerable Polyglot Web App:** Build a vulnerable Python Flask application demonstrating SSTI, SSRF, and complex IDOR.
3.  **PortSwigger Certified Practitioner Lab Clear:** Clear all Server-Side vulnerability labs on PortSwigger Web Security Academy.

---

### 📚 5. Primary Learning Sources

*   💻 *PortSwigger Web Security Academy*
*   📖 *OWASP Web Security Testing Guide (WSTG)*
*   📖 *The Web Application Hacker’s Handbook* (Stuttard & Pinto)

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Time-based SQL injection is unreliable due to network jitter.
>
> **🔍 Root Cause:** Static sleep delays (e.g., `pg_sleep(2)`) become indistinguishable from network latency variations.
> 
> **✅ Fix:** Implement dynamic baseline latency calculation in Python; take average response times and use statistical confidence intervals.
