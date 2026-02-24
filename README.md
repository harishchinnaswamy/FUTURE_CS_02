# FUTURE_CS_02
# Phishing Email Detection & Awareness System  
---

## Project Objective

This project simulates real-world Security Operations Center (SOC) email threat analysis. The objective was to investigate suspected phishing emails by performing header analysis, domain authentication validation, and risk classification based on technical and behavioral indicators.

The project focuses on detecting:

- Email spoofing  
- Domain impersonation  
- Authentication failures  
- Credential harvesting attempts  
- Social engineering tactics  

---

##  Scope of Analysis

Three phishing scenarios were analyzed:

1. Microsoft Account Suspension (Credential Harvesting)
2. Bank OTP Verification (MFA Bypass Attempt)
3. Payroll Update Notification (Corporate Impersonation)

Each email was examined using a structured SOC triage workflow

---

## Tools Used

### 1. MXToolbox – Header Analyzer
Used to:
- Analyze raw email headers  
- Verify SPF authentication results  
- Verify DKIM signature validation  
- Evaluate DMARC policy enforcement  
- Identify originating IP addresses  
- Inspect DNS and MX records  

### 2. Email Client Header Extraction (Gmail / Outlook)
Used to extract full RFC-compliant raw headers for detailed forensic inspection.

---

##  Technical Analysis Approach

The analysis followed a structured SOC investigation process:

### Step 1: Header Extraction
Full raw headers were obtained from the email client.

### Step 2: Authentication Verification
SPF, DKIM, and DMARC results were reviewed to determine:
- Whether the sending IP was authorized
- Whether message integrity was validated
- Whether domain policy enforcement failed

### Step 3: Infrastructure Review
Inspected:
- Return-Path
- Reply-To domain
- Originating IP address
- Mail server inconsistencies

### Step 4: Domain Impersonation Check
Identified:
- Lookalike domains (character substitution, added keywords)
- Non-official domain extensions
- Mismatch between display name and actual domain

### Step 5: Social Engineering Analysis
Examined email content for:
- Urgency or fear-based language
- Financial manipulation tactics
- Authority impersonation
- Credential harvesting links

### Step 6: Risk Classification
Each email was categorized based on authentication failures, spoofing indicators, and attack intent.

---

## Risk Methodology

Risk levels were determined using combined technical and behavioral indicators.

### 🔴 High-Risk Phishing
Classified as High-Risk when:
- SPF = Fail  
- DKIM = Fail or None  
- DMARC = Fail (p=reject or quarantine)  
- Unauthorized sending IP detected  
- Domain impersonation observed  
- Credential harvesting link present  
- Urgency or coercion tactics used  

All analyzed samples met these conditions.

---

### 🟠 Medium Risk (Suspicious)
Would apply if:
- Partial authentication failure  
- Minor domain inconsistencies  
- No confirmed credential harvesting  

---

### 🟢 Low Risk (Legitimate)
Would apply if:
- SPF, DKIM, and DMARC passed  
- Authorized sending IP  
- Domain alignment verified  
- No manipulation indicators  

---

## Key Findings

Across all analyzed samples:

- Multiple authentication failures were identified
- Domain spoofing techniques were used
- Sending infrastructure was unauthorized
- Social engineering tactics targeted user trust and urgency
- Credential harvesting intent was confirmed

All samples were classified as **High-Risk Phishing**.

---

## SOC Relevance

This project demonstrates practical understanding of:

- Email authentication protocols (SPF, DKIM, DMARC)
- Email spoofing detection
- Threat triage workflow
- Risk-based classification
- Human-factor exploitation in phishing campaigns

---

---

##  Author

Harish C  
Cyber Security Intern  
Future Interns
