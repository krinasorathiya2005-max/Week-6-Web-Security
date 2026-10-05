🛡️ WEEK-6 INTERNSHIP
Web Application Security — My Practical Learning Lab
A personal knowledge repository documenting what I learned, tested, observed, and understood during Week 6 of my Cybersecurity Internship.

⚡ WHY THIS REPOSITORY EXISTS
This is not just a collection of screenshots or a report.
I created this repository as my personal technical reference for understanding how a web application behaves from a security perspective — from identifying an input point to analyzing HTTP traffic, validating a weakness, collecting evidence, understanding the impact, and thinking about remediation.
My Week 6 learning path
        WEB APPLICATION
               │
               ▼
        ┌─────────────┐
        │ Understand  │
        │ the Target  │
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │ Find Input  │
        │ & Behavior  │
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │   Test      │
        │  Carefully  │
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │ Analyze HTTP│
        │ Request/Resp│
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │   Capture   │
        │   Evidence  │
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │ Understand  │
        │    Risk     │
        └──────┬──────┘
               ▼
        ┌─────────────┐
        │  Mitigate   │
        │  & Retest   │
        └─────────────┘
🔍 What I Explored
Area	What I learned
🌐 Web Security	How common web application weaknesses occur
💉 SQL Injection	How unsafe input handling can affect database query logic
⚡ Stored XSS	How stored user input can become unsafe browser content
🔁 Reflected XSS	How input can be reflected through an application response
🕵️ Burp Suite	How to inspect and understand HTTP requests and responses
🤖 OWASP ZAP	How automated web security scanning works
📊 Risk Assessment	How findings can be evaluated using impact, likelihood and evidence
🛡️ Mitigation	How vulnerabilities can be prevented or reduced


🧪 My Lab
The practical work was designed around an authorized local training environment.
┌───────────────────────────────────────────────────────┐
│                    LOCAL LAB                          │
│                                                       │
│   Browser ──────► DVWA ◄────── XAMPP                 │
│       │             │                                 │
│       │             ├──── Burp Suite                 │
│       │             │       ↓                         │
│       │             │   HTTP Analysis                 │
│       │             │                                 │
│       └─────────────┴──── OWASP ZAP                   │
│                           ↓                           │
│                     Scan & Alerts                     │
└───────────────────────────────────────────────────────┘
Tools
- XAMPP — local Apache, PHP and MySQL environment
- DVWA — deliberately vulnerable web application for training
- Burp Suite Community Edition — HTTP traffic inspection and analysis
- OWASP ZAP — automated web application security scanning
- Web Browser — application interaction
💉 01 — SQL Injection
The question I wanted to understand
What happens when an application trusts user input too much?

In the DVWA lab, I studied SQL Injection by comparing normal application behavior with controlled test input and observing the resulting response.
What I focused on
Normal Input
     ↓
Application Processing
     ↓
Database Interaction
     ↓
Normal Response

          VS

Controlled Test Input
     ↓
Application Processing
     ↓
Changed Query Behaviour
     ↓
Observed Response
Security takeaway
The main defensive lesson is to keep query structure separate from user-supplied values using parameterized queries or prepared statements.
Evidence
- SQL-01 → Test input
- SQL-02 → Observed SQL Injection result
⚡ 02 — Cross-Site Scripting
Stored XSS
I studied the case where user-controlled content is stored by an application and later rendered to users.
Reflected XSS
I studied the case where user-controlled input is immediately reflected in the application's response.
What I learned
User Input
    ↓
Application
    ↓
Is it safely handled?
    │
 ┌──┴───┐
 NO     YES
 │       │
 ▼       ▼
Unsafe  Safe
Output  Output
Defensive concepts
- Context-aware output encoding
- Safe input handling
- Appropriate sanitization
- Content Security Policy
- Safe templating
- Secure cookie settings
Evidence
- XSS-01 → Stored XSS
- XSS-02 → Reflected XSS
🕵️ 03 — Burp Suite
Burp Suite helped me understand something more important than simply "intercepting a request":
A browser action is ultimately represented through HTTP requests and responses.

What I practiced
Browser
   │
   ▼
HTTP Request
   │
   ▼
Burp Suite
   │
   ▼
DVWA
   │
   ▼
HTTP Response
   │
   ▼
Burp Suite
   │
   ▼
Browser
I analyzed
- HTTP method
- Request path
- Headers
- Parameters
- Test input
- Response status
- Response body
- Application behavior
Evidence
B-01 → Proxy/listener setup
B-02 → Normal request
B-03 → Authorized test request
B-04 → Corresponding response
B-05 → Repeater result, if used
🤖 04 — OWASP ZAP
I used OWASP ZAP to understand how automated web application security scanning can identify potential security issues.
Learning flow
Target
  ↓
Crawl / Scan
  ↓
Alerts
  ↓
Review
  ↓
Validate
  ↓
Document
One important lesson:
A scanner alert is a lead — not automatically proof of a confirmed vulnerability.

Alerts need to be reviewed in the context of the target and available evidence.
Evidence
- Z-01 → ZAP alerts/results
- Z-02 → Exported ZAP report
📊 05 — From Finding to Risk
Finding a vulnerability is only one part of security testing.
I also learned to think about:
Finding
   ↓
What is affected?
   ↓
Can the behavior be reproduced?
   ↓
What could happen?
   ↓
How realistic is exploitation?
   ↓
What evidence supports it?
   ↓
How should it be fixed?
Risk levels studied
Level	Meaning
🔴 Critical	Severe impact requiring urgent remediation
🟠 High	Significant impact / practical exploitation risk
🟡 Medium	Meaningful risk requiring planned remediation
🟢 Low	Limited impact or difficult exploitation
🔵 Informational	Observation or hardening recommendation


🛡️ 06 — What Would Fix It?
Area	Defensive Approach
SQL Injection	Prepared statements / parameterized queries
Stored XSS	Output encoding / safe rendering
Reflected XSS	Context-aware encoding / validation
Authentication	Strong hashing / MFA / secure sessions
Misconfiguration	Secure defaults / patching / restricted access


📸 Evidence Collection
The repository keeps practical evidence organized instead of mixing everything together.
Screenshots/
│
├── 01-XAMPP/
├── 02-DVWA-Setup/
├── 03-SQL-Injection/
├── 04-Stored-XSS/
├── 05-Reflected-XSS/
├── 06-Burp-Suite/
└── 07-OWASP-ZAP/
Evidence map
S-01 → XAMPP services
S-02 → DVWA login/home
S-03 → DVWA setup/database
S-04 → DVWA security level
SQL-01 / SQL-02 → SQL Injection
XSS-01 / XSS-02 → XSS testing
B-01 → B-05 → Burp Suite
Z-01 / Z-02 → OWASP ZAP
📁 Repository Map
Week-6-Internship/
│
├── 📄 README.md
│
├── 📑 Report/
│   └── Week_6_Web_Security_VAPT_Project_Report.pdf
│
├── 🎤 PPT/
│   └── Week_6_Web_Security_VAPT_Presentation.pptx
│
├── 📸 Screenshots/
│   ├── 01-XAMPP/
│   ├── 02-DVWA-Setup/
│   ├── 03-SQL-Injection/
│   ├── 04-Stored-XSS/
│   ├── 05-Reflected-XSS/
│   ├── 06-Burp-Suite/
│   └── 07-OWASP-ZAP/
│
├── 📚 OWASP-Notes/
│
└── 🤖 ZAP-Report/
🧠 Personal Knowledge Notes
This repository is also my revision space.
Instead of remembering tools as commands only, I want to remember the reasoning:
Don't just ask:
"Which tool finds the vulnerability?"

Ask:
"Why does the vulnerability exist?"

"What evidence proves the behavior?"

"What is the actual impact?"

"How would a developer fix it?"

"How would I verify the fix?"

🎯 Week 6 Takeaway
The biggest lesson from this week was:
VAPT is not just about finding vulnerabilities. It is about understanding the application, validating behavior, collecting evidence, assessing risk, and communicating a realistic fix.

⚠️ Authorized Use Only
All practical security testing documented here is intended for an authorized cybersecurity learning environment.
Never test public websites, applications, networks, or accounts without explicit permission.
👨‍💻 Internship Learning Log
Week: 06
Domain: Cybersecurity / VAPT
Focus: Web Application Security
Environment: Authorized Local Lab
🔐 Learn → Test → Understand → Document → Improve
This repository is maintained as my personal technical knowledge base and internship learning record.
