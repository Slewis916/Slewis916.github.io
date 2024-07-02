---
layout: post
title:  Email Forensics
date:   2024-06-13 15:23:00 -0500
categories: blog 
description: Objective is to learn how properly analyze emails.
tags: studylogs 
---

## Understand Email Protocols

### SMTP (Simple Mail Transer Protocol)

SMTP is a basic protocol for sending email over the internet.

It is referred to as the "push" protocol because messages are sent directly from the sender's e-mail server to the recipient's e-mail server.

SMTP  does not encrpyt the contents of the mesage by default, which leaves the contents of the message vulnerable to interception or modification.
Additional measures such as TLS (Transport Layer Security) can minizse these weaknesses.

SMTP is a text-based protocol of commands and responses.

Some commmands used in the SMTP protocol are:

EHLO: Used by the SMTP client to authenticate itself during communication with serverand to obtain a list of commands supported by the server.

MAILFROM: Identifies sender's email address.

RCPT TO: identifies recipient's email address.

DATA: Specifies start of the header, body of email, and containes the text data to be sent after this command.

QUIT: End's the SMTP client's communication with the server ans closes the conection.


### SMTP Port 25 vs. Port 587

#### Port 25
The default and oldest port of SMTP. It's used for communication between email servers. 
Server-to-server communication


Security: Blocked or restricted by many Internet Server Providers (ISPs). Emails sent through port 25 are susceptible to spam and fraud. Port should be used to provide a secure way for users to connect to their own e-mail server.

#### Port 587
Provides a secure way for users to connect to their own e-mail server and send an email.


Security: Preferred port for sending email because it requires the use of encryption (SSL or TLS) to initiate messages, which provides an extra layer of security for user authentication and data integrity.


### IMAP and POP3
IMAP (Internet Message Access Protocol) and POP3 (Post Office Protocol version 3) 

#### IMAP
Manages emails on the server and allows users to access emails across mutliple devices.
Changes are synchronized across all devices.

Security: Requires persistent server connection and is usually encrypted with SSL/TLS. It is recommended that strong authentication and encryption methods are used due to the risk of credetials being transmitted in clear text.

#### IMAP Ports
Port 143: starndard unencrypted port.
Port is ususally encrypted with (STARTTLS)

What is STARTTLS?
A protocol command used to initiate encryption in communication protocols that start as plaintext.
Primary used in email and messaging protocols such as SMTP, IMAP, and POP3.

1. Protocol Upgrade:
During an existing communication session, STARTTLS upgrades a plaintext connection to an encrypted one using Transport Layer Security (TLS) or its predecessor, Secure Socket Layer (SSL).

2. Command-Based: 
In protocols like SMTP, IMAP, and POP3 is a command that the client sends to the server to request and encrypted connection.

3. Encryption Activation:
After the server acknowledges the STARTTLS command, communication channel is encrypted using TLS, providing confidentiality and intergrity for the data exchange.
   