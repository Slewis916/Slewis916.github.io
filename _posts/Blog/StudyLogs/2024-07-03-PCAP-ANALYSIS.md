---
layout: post
title:  Analyzing a PCAP file with Wireshark
date:   2024-06-13 15:23:00 -0500
categories: blog 
description: PCAP file analysis with Wireshark
tags: studylogs 
---
## Analyzing a PCAP file with Wireshark  🌊🦈

The pcap file 'case1.pcap' was opened in Wireshark. I filtered through the network traffic log using the 'smtp' filter to examine the email traffic associated with the smtp protocol.

![Alert](/assets/img/pc1/1.png)
_Figure 1 Applying the smtp filter on a pcap file in wireshark_  

---

The SMTP session begins with the server indicating it is ready to proceed with communication by responding with response code 220. The SMTP command 'EHLO' identifies itself to the server and provides a list of commands supported by the sevrer.
Response code 250 is the server identifying itself (figure 2).

![Alert](/assets/img/pc1/5.png)
_Figure 2 SMTP traffic from start to finish_  

---

Further inspection of the network traffic log indicates the email address that sent the email is : test@letsdefend.io.

![Alert](/assets/img/pc1/2.png)
_Figure 3 Sender's email address_  
---

The destination email address that receieved the email is: admin@ubuntuvm.
![Alert](/assets/img/pc1/3.png)
_Figure 4 Email address of the recipient_  

---

The source IP address that sends the 'EHLO' message in SMTP traffic is: 172.16.8.136 (figure 5).
![Alert](/assets/img/pc1/4.png)
_Figure 5 Overview of the filtered network traffic log_  



