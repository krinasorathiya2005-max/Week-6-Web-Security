Week 6 — Web Security & VAPT Basics
Overview
This project documents a practical Web Application Security and Vulnerability Assessment and Penetration Testing (VAPT) exercise performed in an authorized DVWA/local lab environment.
The project focuses on understanding common web application security vulnerabilities, controlled testing, HTTP request and response analysis, evidence collection, risk assessment, and mitigation.
Objectives
- Understand the fundamentals of Vulnerability Assessment and Penetration Testing (VAPT).
- Study selected OWASP Top 10 security concepts.
- Set up a safe local web application testing environment using DVWA.
- Practice SQL Injection testing in an authorized training environment.
- Understand and test Stored and Reflected Cross-Site Scripting (XSS).
- Capture and analyze HTTP requests and responses using Burp Suite.
- Perform an authorized automated web security scan using OWASP ZAP.
- Document findings, evidence, risk levels, impact, and mitigation.
Tools Used
- XAMPP
- DVWA (Damn Vulnerable Web Application)
- Burp Suite Community Edition
- OWASP ZAP
- Web browser
Assessment Methodology
1. Define and confirm the authorized local testing scope.
2. Set up the DVWA environment using XAMPP.
3. Review the application's pages, inputs, and normal behavior.
4. Perform controlled vulnerability testing.
5. Capture screenshots and relevant HTTP request/response evidence.
6. Analyze the observed behavior and potential security impact.
7. Review automated OWASP ZAP findings.
8. Assess findings based on evidence, likelihood, impact, and exploitability.
9. Document practical mitigation recommendations.
10. Retest after remediation where applicable.
Vulnerabilities & Security Topics Assessed
- SQL Injection
- Stored Cross-Site Scripting (XSS)
- Reflected Cross-Site Scripting (XSS)
- Broken Authentication concepts
- Security Misconfiguration
- HTTP Request and Response Analysis
- Automated Web Security Scanning
Key Findings
The practical assessment focuses on SQL Injection and Stored/Reflected XSS within the intentionally vulnerable DVWA laboratory environment.
The project also covers authentication weaknesses, security misconfiguration concepts, HTTP traffic analysis using Burp Suite, and potential security alerts identified through OWASP ZAP.
Automated scanner results are treated as findings requiring manual review rather than automatic proof of exploitability.
Remediation
- Use parameterized queries and prepared statements for database operations.
- Apply context-aware output encoding for untrusted content.
- Use safe templates and avoid unsafe DOM APIs.
- Apply appropriate input handling and sanitization where required.
- Use Content Security Policy as an additional defense for XSS.
- Use strong password hashing, MFA, secure session management, and rate limiting.
- Apply secure configuration baselines, timely patching, restricted permissions, and secure headers.
- Retest after remediation to confirm that the issue has been addressed.
Evidence Collection
The project includes evidence for:
- XAMPP with Apache and MySQL running
- DVWA login/setup and security configuration
- SQL Injection testing and results
- Stored XSS testing
- Reflected XSS testing
- Burp Suite proxy and HTTP request/response analysis
- OWASP ZAP alerts and exported scan report
Repository Structure
- README.md — Project overview, objectives, methodology, tools, and learning outcomes.
- Report/ — Detailed Week 6 VAPT project report.
- PPT/ — Project presentation.
- Screenshots/ — Evidence captured during the authorized lab testing.
- OWASP-Notes/ — Notes covering OWASP and web security concepts.
- ZAP-Report/ — OWASP ZAP scan report and related output.
Learning Outcomes
- Understanding of basic Web Application Security and VAPT methodology.
- Practical experience with DVWA as an authorized vulnerable training target.
- Understanding of SQL Injection and XSS concepts.
- Experience analyzing HTTP requests and responses using Burp Suite.
- Familiarity with automated web security scanning using OWASP ZAP.
- Experience collecting reproducible evidence and documenting findings.
- Understanding of risk assessment and security mitigation.
- Awareness of the importance of secure coding, input handling, access control, and regular security testing.
Scope and Disclaimer
This exercise is for educational and authorized cybersecurity training purposes and is restricted to the local DVWA/lab environment or other explicitly authorized targets.
Public or third-party systems must not be scanned or tested without explicit permission.
Author
Harsh Dankhra
