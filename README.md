🔐 Week 6 — Web Security & VAPT
Cybersecurity Internship | Web Application Security Testing
A practical, authorized lab project covering Web Security, Vulnerability Assessment & Penetration Testing (VAPT), SQL Injection, XSS, Burp Suite analysis, and OWASP ZAP scanning.

🎯 About This Project
This repository contains the practical work completed for Week 6 of the cybersecurity internship.
The project focuses on understanding how common web application vulnerabilities can be identified, validated, documented, assessed, and mitigated in a controlled learning environment.
The primary training target used in this project is DVWA (Damn Vulnerable Web Application), a deliberately vulnerable application designed for security education.
What this project demonstrates
- 🌐 Web application security fundamentals
- 🔎 Vulnerability assessment methodology
- 💉 SQL Injection testing
- ⚡ Stored & Reflected XSS testing
- 🕵️ HTTP request/response analysis with Burp Suite
- 🤖 Automated security scanning with OWASP ZAP
- 📊 Vulnerability risk assessment
- 🛡️ Mitigation and secure development practices
- 📸 Evidence collection and security documentation
🧭 Project Workflow
        ┌─────────────────────┐
        │   Define Scope      │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Reconnaissance      │
        │ & Input Analysis    │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Controlled Testing   │
        │ SQLi / XSS / HTTP   │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Evidence Collection  │
        │ Screenshots / HTTP   │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Risk Assessment     │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Mitigation          │
        └──────────┬──────────┘
                   ↓
        ┌─────────────────────┐
        │ Documentation &     │
        │ Retesting           │
        └─────────────────────┘
🧪 Lab Environment
Component	Purpose
XAMPP	Local Apache, PHP and MySQL environment
DVWA	Deliberately vulnerable web application used as the authorized training target
Burp Suite Community	HTTP proxy, request interception and request/response analysis
OWASP ZAP	Automated web application security scanning
Web Browser	Application interaction and observation


🔐 Security Scope
All practical testing in this project is intended for an authorized local learning environment.
Testing principles
- ✅ Test only systems you own or have explicit permission to assess.
- ✅ Use controlled test data.
- ✅ Keep screenshots free from real credentials or sensitive information.
- ❌ Do not scan or exploit public websites without written authorization.
- ❌ Do not use this project against unauthorized targets.
🧩 Modules Covered
01 — VAPT Fundamentals
The project begins with the difference between:
Vulnerability Assessment
- Identifies possible weaknesses.
- Often involves scanning and analysis.
- Produces a prioritized list of potential vulnerabilities.
Penetration Testing
- Validates whether selected weaknesses can actually be exploited within an authorized scope.
- Uses controlled manual and automated testing.
- Produces evidence-based findings, impact analysis and recommendations.
02 — OWASP Security Concepts
The project covers the following learning areas:
💉 SQL Injection
Understanding how unsafe handling of user input can influence database query logic.
Key prevention concepts:
- Parameterized queries
- Prepared statements
- Input validation
- Least-privilege database access
- Safe error handling
⚡ Cross-Site Scripting (XSS)
Two XSS scenarios are covered:
Stored XSS
User-controlled input is stored by the application and later rendered to users.

Reflected XSS
User input is immediately reflected in the server response without appropriate output encoding.

Key prevention concepts:
- Context-aware output encoding
- Safe input handling
- Appropriate sanitization
- Content Security Policy
- Secure cookie configuration
- Avoiding unsafe DOM APIs
🔑 Broken Authentication
The project covers weaknesses related to:
- Login mechanisms
- Session management
- Password handling
- Account recovery
- Weak authentication controls
Prevention concepts:
- Strong password hashing
- MFA
- Secure session management
- Rate limiting
- Session expiration and invalidation
⚙️ Security Misconfiguration
Examples discussed include:
- Default credentials
- Unnecessary services
- Verbose error messages
- Exposed directories
- Outdated components
Prevention concepts:
- Secure baseline configuration
- Patching
- Removing unused features/services
- Access restrictions
- Secure headers
- Regular configuration reviews
🧪 Practical Testing
💉 SQL Injection Testing
Testing is performed inside the local DVWA environment.
Method
1. Open the SQL Injection module.
2. Understand normal application behavior.
3. Submit controlled test input.
4. Compare the response with normal behavior.
5. Capture relevant evidence.
6. Analyze the observed behavior and impact.
7. Document mitigation.
Evidence
SQL-01 → SQL Injection test input
SQL-02 → SQL Injection output/result
⚡ XSS Testing
Stored XSS
The test examines whether controlled input is stored and later rendered unsafely.
Reflected XSS
The test examines whether controlled input is reflected immediately in the application response.
Evidence
XSS-01 → Stored XSS input and resulting output
XSS-02 → Reflected XSS input and resulting output
🕵️ Burp Suite Analysis
Burp Suite Community Edition is used to understand what happens between the browser and the application.
Analysis includes
Browser
   ↓
HTTP Request
   ↓
Burp Suite
   ↓
DVWA
   ↓
HTTP Response
   ↓
Burp Suite
   ↓
Browser
Evidence collected
- HTTP method
- Request path
- Headers
- Parameters
- Test input
- Response status
- Response body
- Application behavior
Evidence IDs
ID	Evidence
B-01	Burp proxy/listener setup
B-02	Captured normal DVWA request
B-03	Request containing authorized test input
B-04	Corresponding HTTP response
B-05	Repeater result, if used


🤖 OWASP ZAP Automated Scan
OWASP ZAP is used to identify potential web security issues through automated crawling and scanning.
Process
1. Open OWASP ZAP.
2. Configure the browser or use the ZAP-provided browser.
3. Access the local DVWA target.
4. Define the appropriate scope/context where required.
5. Run a suitable baseline or automated scan.
6. Review generated alerts.
7. Analyze risk classifications.
8. Export the report.
9. Store the report in ZAP-Report/.
Evidence
Z-01 → OWASP ZAP alerts/results panel
Z-02 → Exported ZAP report / report summary
⚠️ Automated scanner results must be manually reviewed. A scanner alert is not automatically proof that a vulnerability is exploitable.

📊 Risk Assessment
Findings are evaluated using:
- Likelihood
- Impact
- Exploitability
- Affected component
- Supporting evidence
- Confirmation within the lab environment
Risk Levels
Level	Meaning
🔴 Critical	Severe impact requiring urgent remediation
🟠 High	Significant impact or practical exploitation risk
🟡 Medium	Meaningful risk requiring planned remediation
🟢 Low	Limited impact or difficult exploitation
🔵 Informational	Observation or hardening recommendation


Severity should be assigned from actual evidence and lab context—not simply because an automated tool displayed an alert.

🛡️ Mitigation Summary
Vulnerability	Main Mitigation
SQL Injection	Prepared statements, parameterized queries and least-privilege DB access
Stored XSS	Output encoding, safe templates and appropriate sanitization
Reflected XSS	Context-aware encoding, validation and safe rendering
Broken Authentication	Strong password hashing, MFA, secure sessions and rate limiting
Security Misconfiguration	Secure defaults, patching, restricted permissions and secure headers


📁 Repository Structure
Week-6-Web-Security-VAPT/
│
├── README.md
│
├── Report/
│   └── Week_6_Web_Security_VAPT_Project_Report.pdf
│
├── PPT/
│   └── Week_6_Web_Security_VAPT_Presentation.pptx
│
├── Screenshots/
│   ├── 01-XAMPP/
│   ├── 02-DVWA-Setup/
│   ├── 03-SQL-Injection/
│   ├── 04-Stored-XSS/
│   ├── 05-Reflected-XSS/
│   ├── 06-Burp-Suite/
│   └── 07-OWASP-ZAP/
│
├── OWASP-Notes/
│   ├── OWASP-Top-10.md
│   ├── SQL-Injection.md
│   ├── XSS.md
│   ├── Broken-Authentication.md
│   └── Security-Misconfiguration.md
│
└── ZAP-Report/
    └── ZAP-Scan-Report.html
📸 Evidence Map
Evidence	Description
S-01	XAMPP with Apache & MySQL running
S-02	DVWA login/home page
S-03	DVWA database/setup page
S-04	DVWA security level
SQL-01	SQL Injection test input
SQL-02	SQL Injection result
XSS-01	Stored XSS input/result
XSS-02	Reflected XSS input/result
B-01	Burp proxy/listener setup
B-02	Normal HTTP request
B-03	Authorized test request
B-04	HTTP response
B-05	Repeater result, if used
Z-01	ZAP alerts/results
Z-02	ZAP exported report


📚 References
- OWASP Top 10
- OWASP Web Security Testing Guide
- PortSwigger Web Security Academy
- OWASP ZAP Documentation
- DVWA Documentation
📌 Key Learning Outcome
This project goes beyond simply running security tools.
The main learning workflow is:
Identify → Test → Capture Evidence → Analyze → Assess Risk → Recommend Mitigation → Retest

The practical work demonstrates how web security findings can be converted into structured, evidence-based security documentation.
⚠️ Disclaimer
This repository is intended strictly for authorized cybersecurity education, research, and lab practice.
The techniques demonstrated here must not be used against systems, applications, networks, or accounts without explicit authorization.
👨‍💻 Author
Krina Sorathiya
Cybersecurity | VAPT | Web Application Security
⭐ If this project helps you understand the fundamentals of web security testing, consider giving the repository a star.
