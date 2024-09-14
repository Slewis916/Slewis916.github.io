---
layout: post
title:  Malicious VBA
date:   2024-06-29 15:04:00 -0500
categories: blog 
description: Investigating a suspicious document attached to an email invoice.
tags: homelabs blog
---


![Alert](/assets/img/ch/1.png)




## Background:
One of the employees has received a suspicious document attached in the invoice email. They sent you the file to investigate. You managed to extract some strings from the VBA Macro document. Can you refer to CyberChef and decode the suspicious strings?


## Analysis
To begin the analysis, the suspicous document 'invoice.vb' was opened in the Linux terminal. The bash command 'strings' was used to extract readable text from the file.

![Alert](/assets/img/ch/2.png)
_Figure 2 Output in the Linux terminal from the 'strings' bash command_  

---

The first string which is underlined in red, in figure 3, was input into Cyberchef using the 'from Charcode' recipe. The output of the string is tinyurl.com/g2z2gh6f. The document initiates the download of a payload after execution which is hosted on tinyurl.com/g2z2gh6f (figure 4).


![Alert](/assets/img/ch/1st.png)
_Figure 3 First string output from the bash command 'strings'._  

---

![Alert](/assets/img/ch/3.png)
_Figure 4 Decoded string from the suspicious file using CyberChef_  

---

The filename of the payload was discovered by decoding next string from document in CyberChef. The output was 'dropped.exe'.

![Alert](/assets/img/ch/5.png)
_Figure 5 Decoded string from the suspicious file using CyberChef_  

---

The suspicious document is using method 'MSXML2.ServerXMLHTTP' to establish an HTTP connection between files on the malicious web server (figure 6).

![Alert](/assets/img/ch/6.png)
_Figure 6 Decoded string from the suspicious file using CyberChef_  

---

The malicious web server is using the user-agent, Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.0), (figure 7).

![Alert](/assets/img/ch/7.png)
_Figure 7 Decoded string from the suspicious file using CyberChef_  

---

The attacker uses the object 'ADODB.Stream' to read and write text and binary files (figure 8).

![Alert](/assets/img/ch/8.png)
_Figure 8 Decoded string from the suspicious file using CyberChef_  

---

The attacker uses the object 'winmgmts:\\.\root\cimv2:Win32_Process' for WMI execution (figure 9). This allows the attacker to gather system information, execute commands or scripts on remote systems and automate routine task or deploy software.


![Alert](/assets/img/ch/9.png)
_Figure 9 Decoded string from the suspicious file using CyberChef_  

---


Technologies and Tools used:
Linux terminal, Bash, CyberChef

This challenge is hosted via Letsdefend.io: 
https://app.letsdefend.io/challenge/Malicious-VBA