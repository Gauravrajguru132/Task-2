# Task-2-Analyze-a-Phishing-Email-Sample-Elevate-Labs-
Phishing, email spoofing, header analysis, social engineering, threat detection
## Downloadable Phishing Samples
GitHub – “Phishing Pot” Collection
A community-maintained archive of real phishing .eml samples collected via honeypots

`git clone https://github.com/rf-peixoto/phishing_pot.git`

`cd phishing_pot/email`

`nano sample-12.eml `

![image alt](https://github.com/Gauravrajguru132/Task-2/commit/1aaa0d8070904cefb3117a4e90f2821a6246aca4#diff-aa2099f261c1b791467217515e8d4761eb7ca4a732e6e4bb572e56512704f8bf)

## Use an online analyzer (open browser in Kali):

Go to: https://mxtoolbox.com/SuperTool.aspx

Paste header text and click "Analyze"

![image alt](https://github.com/Gauravrajguru132/Task-2/commit/1aaa0d8070904cefb3117a4e90f2821a6246aca4#diff-4c468b3b16999fd9578189576d5f770cb4a16ad9fca0e798a251f00a54a87c5d)
![image alt](https://github.com/Gauravrajguru132/Task-2/commit/1aaa0d8070904cefb3117a4e90f2821a6246aca4#diff-88a5d4f503b26504ed25f8cf38a0b97ddfd234c4f024896a96a3fa363de0660b)
![image alt](https://github.com/Gauravrajguru132/Task-2/commit/1aaa0d8070904cefb3117a4e90f2821a6246aca4#diff-da877ea96a7e8f7c9bced14ac791f424af4b0b4eab101ef636545c20e9eed116)
![image alt](https://github.com/Gauravrajguru132/Task-2/commit/1aaa0d8070904cefb3117a4e90f2821a6246aca4#diff-acf116f09554c5c3652b89f246234edb358ce68a27c0f4e4c0279e9429b50825)
## Email Overview

- **Subject**: `[Binаnсе] Immediate verification required for rodrigo-f-p@hotmail.com`
- **Claimed Sender**: `do-not-reply@ses.binance.com`
- **Actual Sending Domain**: `ilonasavola.com`
- **Return Path**: `wpcloud@ilonasavola.com`
- **Message ID**: `a6e2feecb5be84894fdbdba6447a7b10@ilonasavola-com.staging.hel2.wp-cloud.dev`
- **Date**: August 22, 2022

# 🛡 Phishing Email Sample Analysis 

This repository documents the analysis of a phishing email impersonating Binance. It highlights how threat actors use spoofing, misaligned headers, and social engineering to deceive recipients.

---

##  1. Sample Overview

A phishing email was analyzed that falsely claimed to be from Binance.  
- **Subject**: `[Binаnсе] Immediate verification required for rodrigo-f-p@hotmail.com`  
- The subject line raised suspicion due to its **urgent tone** and **unusual formatting** of the sender name, suggesting a potential scam.

---

##  2. Sender Spoofing Detected

The email **pretends** to be from:  
`do-not-reply@ses.binance.com`

However:
- The **actual sending domain** was `ilonasavola.com`
- The **Return-Path** was `wpcloud@ilonasavola.com`

This clearly indicates that the email **did not originate from Binance**, and is an example of **sender spoofing**.

---

##  3. Header Discrepancies

After header analysis using MXToolbox, multiple technical issues were found:

-  **SPF** failed: The sending IP was not authorized to send on behalf of Binance’s domain.
-  **DKIM** missing: The message was not cryptographically signed.
-  **DMARC** failed: The domain could not be verified by recipient servers.

 These authentication failures confirm the email is **not legitimately from Binance**.

---

##  4. Suspicious Links or Attachments

The full body of the email was not provided. However:
- The **urgency** in the subject line
- The **impersonation of Binance**
- The **spoofed sender address**

...all strongly suggest that the message likely contained a **malicious link** (e.g., a fake login page designed to steal user credentials).

---

##  5. Urgent & Threatening Language

The subject line used the phrase:
> **"Immediate verification required"**

This is a common **social engineering technique**, pressuring the recipient to act quickly without thinking. It plays on fear and urgency to increase the chances of a successful phishing attempt.

---

##  6. Visual Spoofing Using Unicode

The word **“Binаnсе”** in the subject is **not typed using standard English letters**:
- It uses **Cyrillic characters** that visually resemble Latin ones.

 This Unicode spoofing method:
- Helps attackers **bypass email filters**
- Tricks human readers by **mimicking familiar brand names**

---

##  7. Spelling and Grammar Issues

While obvious spelling or grammar issues weren't seen in the header alone, the **use of character substitution** (Unicode spoofing) is a known deception strategy in phishing:

- It avoids detection by traditional spam filters
- It mimics brand names in ways that are **difficult to visually distinguish**

---

##  8. Summary of Phishing Traits Identified

| Indicator                              | Status     |
|----------------------------------------|------------|
|  Spoofed sender address               | ✔️ Detected |
|  SPF/DKIM/DMARC authentication failed | ✔️ Detected |
|  Unrelated sending domain             | ✔️ Detected |
|  Urgent & pressuring language         | ✔️ Detected |
|  Unicode lookalike characters         | ✔️ Detected |
| Likely malicious links (body not shown) | Suspected   |

---

##  Conclusion

This email is a **confirmed phishing attempt** that uses both **technical deception** (spoofed headers, failed authentication, foreign sending domains) and **psychological manipulation** (urgency, visual brand impersonation) to trick recipients.

Users should:
- **Never click links** in such emails
- **Report** messages to their security teams or email providers
- **Verify** communication by going directly to official websites

---

