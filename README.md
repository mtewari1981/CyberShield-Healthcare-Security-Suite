# 🏥 CyberShield Healthcare Security Suite

> Open-source, HIPAA-aligned cybersecurity toolkit for healthcare organizations.  
> No sign-up. No installation required.

**Live Demo:** https://mtewari1981.github.io/CyberShield-Healthcare-Security-Suite/

---

## What Is This?

CyberShield is an open-source cybersecurity toolkit built specifically for healthcare organizations — community hospitals, outpatient clinics, medical billing firms, and independent practices that lack dedicated security staff or enterprise security budgets.

It provides two working tools and a HIPAA reference module, all accessible directly in the browser with no installation required.

---

## The Problem It Solves

Healthcare organizations are the #1 target for phishing, ransomware, and Business Email Compromise (BEC) attacks in the United States. According to HHS and CISA:

- Phishing is the leading cause of healthcare data breaches
- The average healthcare breach costs **$10.9 million** (IBM 2023)
- Small and mid-size healthcare organizations are disproportionately targeted because they lack the security tools that enterprise health systems have

Most security tools are expensive, complex, or require dedicated IT staff to operate. CyberShield is built for the organizations that have none of those resources.

---

## Components

### 📧 1. Healthcare Email Phishing Analyzer

Analyzes any email for healthcare-specific threat indicators. Paste the sender, subject, and body — get an instant risk score with HIPAA-mapped findings.

**What it detects:**

| Threat Type | Description |
|---|---|
| EHR Credential Phishing | Spoofed EPIC, Cerner, Meditech, Athenahealth, eClinicalWorks domains |
| Medicare / CMS Fraud | Impersonation of CMS, HHS, and federal healthcare agencies |
| PHI / ePHI References | Detection of Protected Health Information in email content |
| Ransomware Delivery | Invoice/attachment patterns used to deliver malware to clinical staff |
| Business Email Compromise | Wire transfer, payroll diversion, and executive impersonation fraud |
| Reply-To Mismatch | Sender/reply domain mismatch used to intercept PHI-containing replies |
| Urgency & Social Engineering | Pressure tactics used to bypass staff judgment |
| Malicious URLs | IP-based links, high-risk TLDs, and spoofed EHR/healthcare domains in body |

**Every finding is mapped to the applicable HIPAA Security Rule section.**

---

### 🔗 2. URL / Web Traffic Checker

Analyzes any URL or web link for signs of malicious intent — particularly useful for links received in emails, text messages, or documents.

**What it checks:**

| Check | Description |
|---|---|
| Protocol | HTTP vs HTTPS — unencrypted connections expose credentials and PHI |
| Raw IP Address | No legitimate EHR or healthcare site uses an IP address as the host |
| EHR Domain Spoofing | Detects domains impersonating EPIC, Cerner, MyChart, and others |
| Medicare / Gov Impersonation | Flags domains mimicking CMS.gov, HHS.gov, and federal agencies |
| High-Risk TLD | Flags .tk, .ml, .xyz, .pw, .ru and other domains abused in phishing |
| Suspicious Path | Detects credential-harvesting paths (login, verify, confirm, password) |
| Subdomain Depth | Excessive subdomains used to disguise malicious domains |

**Each finding includes the relevant HIPAA Security Rule reference.**

---

### 🏛 3. HIPAA Security Rule Framework Reference

A built-in reference module that maps the full spectrum of detected threats to the HIPAA Security Rule safeguards under 45 CFR §164:

- **Administrative Safeguards · §164.308** — Security management, awareness training, incident procedures, contingency planning
- **Technical Safeguards · §164.312** — Access control, audit controls, integrity, transmission security
- **Physical Safeguards · §164.310** — Workstation security, device and media controls

Also documents **OCR Breach Notification triggers** — the threat types that require mandatory reporting to the HHS Office for Civil Rights.

---

## How to Use

### Email Analyzer
1. Open the live tool: https://mtewari1981.github.io/CyberShield-Healthcare-Security-Suite/
2. Paste the sender email address, reply-to (if different), subject line, and email body
3. Click **Analyze for Healthcare Threats**
4. Review the risk score, findings, and HIPAA references
5. Use the built-in sample emails to see the tool in action

### URL Checker
1. Switch to the **URL / Web Traffic Checker** tab
2. Paste the URL you want to check
3. Select the context (found in email, browser, text, document)
4. Click **Analyze URL**
5. Review each security check and the HIPAA risk assessment

### Sample Scenarios Included
- ⚠️ EPIC EHR credential phishing email
- 🚨 Medicare billing fraud impersonation
- ☠️ Ransomware delivery via malicious invoice link
- 💼 CEO / CFO wire transfer BEC attack
- 🏥 PHI exfiltration request
- ✅ Legitimate internal IT communication

---

## Files in This Repository

| File | Description |
|---|---|
| `CyberShield_Healthcare_Suite.html` | Main tool — email analyzer, URL checker, HIPAA framework |
| `CyberShield_Email_Filter.html` | Original general-purpose email phishing filter (v1) |
| `index.html` | Project showcase / landing page |
| `manifest.json` | Chrome extension manifest (browser extension component) |
| `background.js` | Chrome extension background service worker |
| `popup.html` | Chrome extension popup UI |
| `blocked.html` | Chrome extension blocked page UI |
| `README.md` | This file |

---

## HIPAA Alignment

CyberShield is designed to support healthcare organizations in meeting their obligations under the HIPAA Security Rule (45 CFR Part 164). Every detected threat is mapped to the relevant safeguard:

| HIPAA Section | Safeguard | CyberShield Coverage |
|---|---|---|
| §164.308(a)(1) | Security Management Process | Threat detection and risk identification |
| §164.308(a)(5) | Security Awareness Training | Phishing and social engineering detection |
| §164.308(a)(6) | Security Incident Procedures | BEC and breach indicator detection |
| §164.308(a)(7) | Contingency Plan | Ransomware pattern detection |
| §164.312(a)(1) | Access Control | EHR credential phishing detection |
| §164.312(c)(1) | Integrity | PHI reference detection |
| §164.312(e)(1) | Transmission Security | Malicious URL and unencrypted link detection |
| §164.310(c) | Workstation Security | Malware delivery pattern detection |

> **Note:** CyberShield is a detection and awareness tool. It does not replace a comprehensive HIPAA compliance program but supports the security awareness and incident detection requirements of the Security Rule.

---

## Who This Is For

- Small and mid-size hospitals without a dedicated SOC
- Community health centers and federally qualified health centers (FQHCs)
- Independent medical practices and outpatient clinics
- Medical billing and revenue cycle management organizations
- Healthcare IT staff who need a quick, accessible triage tool
- Security awareness trainers in healthcare settings

---

## Technical Notes

- **No backend. No data collection.** All analysis runs entirely in the browser using JavaScript. No email content or URLs are transmitted to any server.
- **No login or account required.**
- **Pattern-based detection.** The tool uses curated pattern libraries for healthcare-specific threat detection. It does not connect to live external threat intelligence feeds.
- **Open source.** All code is available in this repository for review, audit, and contribution.

---

## Roadmap

- [ ] VirusTotal API integration for real-time URL reputation checking
- [ ] Chrome Web Store publication of the browser extension component
- [ ] Expanded EHR and healthcare vendor domain pattern library
- [ ] Downloadable PDF report of scan findings for compliance documentation
- [ ] NIST CSF control mapping alongside HIPAA references

---

## Contributing

Contributions are welcome — particularly from healthcare IT professionals, security researchers, and clinicians who can help expand the detection patterns and validate the HIPAA framework mappings.

1. Fork the repository
2. Create a feature branch
3. Submit a pull request with a clear description of the change

---

## Author

**Monika Tewari**  
Cybersecurity researcher and developer  
GitHub: [@mtewari1981](https://github.com/mtewari1981)  
Project: [CyberShield Healthcare Security Suite](https://mtewari1981.github.io/CyberShield-Healthcare-Security-Suite/)

---

## License

This project is released as open-source software for public benefit. 

---

*CyberShield is an independent open-source project. It is not affiliated with EPIC Systems, Cerner, HHS, CMS, or any other healthcare organization or government agency mentioned in this documentation.*
