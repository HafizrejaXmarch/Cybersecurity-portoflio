# 🛡️ Cyber Security Portfolio — Hafiz Reja Pratama

Welcome to my Cybersecurity Portfolio. I am an aspiring **Junior SOC Analyst (L1)** and **Cybersecurity Enthusiast** with hands-on experience in **Defensive Security** (Log Analysis, Digital Forensics, SIEM Monitoring) and **Offensive Security** (VAPT & Web Exploitation).

---

## 🔵 Project 1: Defensive Security — Digital Forensics & Wazuh SIEM Investigation (PRIMARY)
- **Role:** Junior SOC Analyst / Incident Responder[cite: 2]
- **Environment:** Ubuntu Linux (`srv974671`), Wazuh SIEM, Apache2, MySQL[cite: 2]
- **Objective:** Investigating multi-vector attacks, analyzing raw log artifacts, identifying detection gaps, and mapping adversary techniques to the MITRE ATT&CK framework[cite: 2].
- **Key Findings & Investigation Summary:**
  - **SQL Injection (Database Layer - CRITICAL):** Identified unauthorized data enumeration (`SELECT COUNT(*) FROM mysql.user`) in MySQL General Query logs[cite: 2].
  - **SSH Brute Force Analysis (MEDIUM):** Analyzed 160+ authentication failure events via Wazuh SIEM & `auth.log`, mapping attack patterns to MITRE ATT&CK (T1110.001)[cite: 2].
  - **RCE & LFI Exploitation Attempts (MEDIUM):** Investigated Netgear CGI RCE attempts (Mozi botnet payload) and LFI traversal, confirming True Negative/Failed attempts via HTTP status codes and payload size analysis[cite: 2].
  - **SIEM Control Plane Assessment (LOW):** Evaluated Wazuh API logs (`api.log`) to identify session token expiration and temporary monitoring blind spots[cite: 2].
- **🛡️ Remediation & Actionable Mitigation:**
  - **Immediate:** Apply Prepared Statements for database queries[cite: 2], disable `PermitRootLogin` and `PasswordAuthentication` in `sshd_config`[cite: 2], and permanently block malicious IoC IPs via firewall (`iptables`/`UFW`)[cite: 2].
  - **Long-term:** Implement Least Privilege on database credentials[cite: 2], deploy key-based SSH authentication with `fail2ban`[cite: 2], tune WAF (ModSecurity) rulesets[cite: 2], and adjust Wazuh API token lifetimes[cite: 2].

📄 [Lihat Laporan Forensik & SIEM PDF Selengkapnya](./docs/Defensive_Wazuh_SIEM_Forensics_Report.pdf)

---

## 🔴 Project 2: Offensive Security — Vulnerability Assessment & PenTest
- **Role:** Penetration Tester / Red Teamer[cite: 4]
- **Target Platform:** BimbyCart v1.0 (E-Commerce Simulation)[cite: 4]
- **Objective:** Identifying business logic flaws and security misconfigurations to recommend actionable mitigation strategies[cite: 4].
- **Tools Used:** Burp Suite Community Edition, Nmap, Gobuster, Firefox DevTools[cite: 4]
- **Key Findings (OWASP Top 10):**
  - **Parameter Tampering (HIGH - CVSS 8.1):** Manipulated client-side price parameters to checkout items for unauthorized amounts[cite: 4].
  - **Insecure Session Management (MEDIUM):** Identified missing `HttpOnly` and `Secure` cookie flags on session IDs (`PHPSESSID`)[cite: 4].
  - **Security Misconfigurations (MEDIUM/LOW):** Public server banner exposure (`Server: Apache`)[cite: 4], missing `X-Frame-Options` (Clickjacking risk)[cite: 4], and missing `Content-Security-Policy` (CSP)[cite: 4].
- **🛠️ Remediation & Patching Guidance:**
  - **Server-Side Price Enforcement:** Completely sever client-side price parameters and handle item pricing calculations strictly on the backend via database lookup[cite: 4].
  - **Cookie Hardening:** Set `secure` and `httponly` flags via `session_set_cookie_params()` or global `php.ini` (`session.cookie_httponly = On`)[cite: 4].
  - **Server Hardening:** Suppress server banners (`ServerTokens ProductOnly`, `ServerSignature Off`)[cite: 4] and inject missing security response headers (`X-Frame-Options: SAMEORIGIN`, `Content-Security-Policy`)[cite: 4].

📄 [Lihat Laporan PenTest PDF Selengkapnya](./docs/Offensive_Penetration_Testing_Report.pdf)

---

## 🛠️ Technical Skill Set & Tools
- **SIEM & Monitoring:** Wazuh SIEM[cite: 2]
- **Forensics & Log Analysis:** `auth.log`, Apache Access/Error Logs, MySQL Query Logs, Wireshark[cite: 2]
- **Offensive & Assessment Tools:** Burp Suite, Nmap, Gobuster, SQLmap, Metasploit[cite: 2, 4]
- **Operating Systems & Scripting:** Linux (Ubuntu, Kali Linux), Bash Scripting[cite: 2, 4]
- **Frameworks & Standards:** OWASP Top 10, MITRE ATT&CK, CVSS v3.1[cite: 2, 4]

---

## 📬 Contact & Professional Links
- **LinkedIn:** [Hafiz Reja Pratama](https://www.linkedin.com/in/hafiz-reja-pratama-9b1373271/)
- **GitHub:** [HafizrejaXmarch](https://github.com/HafizrejaXmarch)

