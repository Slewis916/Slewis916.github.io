---
layout: post
title:  Email Forensics
date:   2024-06-13 15:23:00 -0500
categories: blog 
description: Objective is to learn how properly analyze emails.
tags: studylogs 
---

## Understand Email Protocols

### SMTP(Simple Mail Transer Protocol)

SMTP is a basic protocol for sending email over the internet.

It is referred to as the "push" protocol because messages are sent directly from the sender's e-mail server to the recipient's e-mail server.

SMTP  does not encrpyt the contents of the mesage by default, which leaves the contents of the message vulnerable to interception or modification.
Additional measures such as TLS (Transport Layer Security) can minizse these weaknesses.

SMTP is a text-based protocol of commands and responses.

Some commmands used in the SMTP protocol are:

EHLO: Used by the SMTP client to authenticate itself during communication with serverand to obtain a list of commands supported by the server.

MAILFROM: Identifies sender's email address.

RCPT TO: