---
layout: post
title:  Email Header Analysis Using Thunderbird
date:   2024-07-04 09:45:00 -0500
categories: blog 
description: Analyzing an email header for potential phishing indicators and authentication anomalies.
tags: studylogs 
---

## Email Header Analysis Using Thunderbird 🌩️🐦

The email 'case2.eml' was opened in Thunderbird. The receiving email address is letsdefendlab@outlook.com. The email was sent from demo@letsdefend.io, but the 'reply-to' address is demo@l3tsd3f3nd.io, which could indicate a phishing attempt. Additionally, the subject line 'Request for Lab Testing Services' is potentially suspicious due to its call to action (Figure 1).

![Email](/assets/img/Ha/1.png)
_Figure 1 Overview of email_  

---


In the source file of case2.eml, the authentication results showed that the SPF result was 'SoftFail.' A SoftFail indicates that the sending activity is flagged as suspicious but still accepted, which often leads to the email being marked as spam. The smtp.mailfrom is designated as letsdefend.io, a valid domain. The DKIM (DomainKeys Identified Mail) status is 'none,' meaning the DKIM signature is absent. The DKIM signature is crucial for email authentication, as it allows the receiver to verify that the email originated from the specified domain and was authorized by the domain owner(Figure 2).

The DMARC check failed, but since the policy action was set to "none," the email was still delivered to the recipient. DMARC (Domain-based Message Authentication, Reporting, and Conformance) works in conjunction with SPF and DKIM to allow domain owners to specify how to handle emails that fail authentication checks. When a DMARC check fails, it typically means that the email did not pass either the SPF or DKIM checks. The "none" policy setting enables domain owners to monitor email traffic without affecting delivery, providing valuable insights for improving email authentication (Figure 2).




![Source file](/assets/img/Ha/2.png)
_Figure 2 Source file of email case2.eml_  

---



The domain 'emkei.cz' initiated server communication at 17:46:08 with the server AM2PEPF0001C70A.mail.protection.outlook.com via Frontend Transport. The IP address associated with 'emkei.cz' is 114.29.236.247. As shown in Figure 2, the 'Received-SPF' header specifies a 'SoftFail' occurred, indicating that "the domain of transitioning letsdefend.io discourages the use of 114.29.236.247 as a permitted sender." Further analysis of the domain 'emkei.cz' reports it as untrusted (Figure 3). Despite the 'SoftFail', the email was allowed to be transmitted.

![Screenshot Cisco Talso ](/assets/img/Ha/3.png)
_Figure 3 Domain reputation of emkei.cz via Cisco Talos Intelligence Search_  

---



## Conclusion 

In summary, the combination of suspicious sending and 'reply-to' addresses, the 'SoftFail' in SPF, absence of DKIM, and a failed DMARC check, alongside the use of an untrusted domain, all point to the likelihood of this email being part of a phishing attempt. This case underscores the importance of robust email authentication and monitoring mechanisms to protect against phishing and other email-based threats.