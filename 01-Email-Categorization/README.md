# Phishing Email Categorization

## Executive Summary
This investigation focused on the initial triage of four suspicious emails. The main goal is to identify the type of phishing activity associated with each message before conducting any in-depth technical analysis.
Accurate categorization is an essential first step in the phishing investigation process, as different attack types require different investigative techniques and response actions.

## Skills Demonstrated
- Email triage
- Phishing classification
- Threat identification
- Initial incident assessment
- Security analysis
- Critical thinking

## Tools Used
- Mozilla Thunderbird

## Investigation Methodology
Each email was manually reviewed to identify visible indicators of phishing without performing detailed forensic analysis. I focused on:

- Sender information
- Email content
- Embedded links
- Attachments
- Social engineering techniques
- Intended attacker objective

Each email was categorized into one of the following phishing types:

- Reconnaissance
- Credential Harvester
- Spam
- Malicious Attachment

# Investigation Results

## Email 1

### Classification

**Reconnaissance**

### Analysis

The email appeared to be designed to collect information about the recipient rather than immediately deliver malware or steal credentials. Reconnaissance emails are commonly used to verify active accounts or gather intelligence before launching a targeted attack.
📷 **Screenshot**`images/01-email-overview.png`

## Email 2

### Classification

**Credential Harvester**

### Analysis

The email attempted to lure the recipient into providing authentication credentials through a fraudulent login page impersonating a trusted service.
📷 **Screenshot**`images/02-email-overview.png`

## Email 3

### Classification

**Spam**

### Analysis

The message contained characteristics commonly associated with unsolicited bulk email. While not every spam message is malicious, spam is frequently used as a delivery method for phishing campaigns and other threats.
📷 **Screenshot**`images/03-email-overview.png`

## Email 4

### Classification

**Malicious Attachment**

### Analysis

The email contained an attachment intended to convince the recipient to open a potentially malicious file. Attachment-based phishing remains a common method for delivering malware and establishing initial access.
📷 **Screenshot**`images/04-email-overview.png`

# Classification Summary

| Email | Category | Primary Threat |
|-------|----------|----------------|
| Email 1 | Reconnaissance | Information Gathering |
| Email 2 | Credential Harvester | Credential Theft |
| Email 3 | Spam | Unsolicited Messaging |
| Email 4 | Malicious Attachment | Malware Delivery |

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1566 | Phishing |
| T1566.001 | Spearphishing Attachment |
| T1566.002 | Spearphishing Link |
| T1589 | Gather Victim Identity Information |
| T1204 | User Execution |

# Detection Opportunities
Throughout this investigation, I identified several opportunities where security controls could detect or prevent similar phishing attempts before they reach users:

- **Look-alike Domain Detection:** Monitor for domains that closely resemble legitimate organizations to identify potential brand impersonation and typosquatting attacks.

- **Credential Harvesting Detection:** Create alerts for emails containing hyperlinks that redirect users to external login pages, especially when they impersonate trusted services such as Microsoft, Google, or financial institutions.

- **Attachment Sandboxing:** Automatically analyze email attachments in a sandbox environment before delivery to identify malicious files and reduce the risk of malware execution.

- **Sender Authentication Validation:** Verify SPF, DKIM, and DMARC records to identify spoofed or unauthorized email senders.

- **URL Reputation Monitoring:** Inspect embedded URLs against threat intelligence feeds and newly registered domain databases to detect suspicious or malicious websites.

- **User Awareness:** Encourage users to report suspicious emails as early as possible. User reports often provide valuable indicators that can help the SOC identify and contain phishing campaigns before they spread.

# Lessons Learned
This investigation reinforced that effective phishing analysis begins with careful observation. Rather than immediately relying on automated tools, I learned the importance of examining an email's content, sender information, links, attachments, and overall intent to understand what the attacker is trying to accomplish.

One of the biggest takeaways from this exercise was recognizing that not every phishing email has the same objective. Some are designed to steal credentials, others deliver malware through attachments, while some simply gather information about potential victims. Correctly identifying the attack type allows an analyst to prioritize the investigation and choose the appropriate response.

This exercise also strengthened my confidence in manually identifying phishing indicators and thinking through an investigation like a SOC analyst. Developing this analytical approach is just as important as learning the technical tools, as it helps build the critical thinking needed to investigate real-world phishing incidents.
