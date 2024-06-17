---
layout: post
title:  Cyber Threat Intelligence
date:   2024-06-13 15:23:00 -0500
categories: blog 
description: Determining the attack surface
tags: studylogs blog
---
## Extended Threat Intelligence

### Concept:
Creates an attack surface belonging to the organization in order to produce intelligence specific to the organization.

This personalized attack surface allows the organization to gain visibility. Visibility can be a forgotten endpoint or a forgotten subdomain.

The main takeaway is the organization now know their inventories and know which assets to defend against.

## Determining the Attack Surface

When creating the attack surface every facet is taken into account.

- For instance, subdomains,
- domains,
- websites,
- login pages,
- CMS applications,
- technologies used on websites,
- IP addresses,
- IP blocks,
- DNS records,
- C-level employee mails,
- network applications,
- operating systems,
- bin numbers,
- SSL certificates
- and swift codes

## Domains

Given only the primary domain of the organization, the goal is to create the entire entity structure over this domain.

Sample scenario:

An asset inventory of Abanca, a bank located in Spain, will be created.

Main domain: Abanca.com

Related domains: 

1. Find domains that provide redirects to the main domain
2. Use host.io, it provides all the domains hosted on the same IP, domains hosting the relevant domain within the website, other domains hosted by the domain within the website
3. Decide which domains belong to the organizationn and which don’t by checking the whois outputs of the domains or by looking at their content
4. To view all of the domains via the API, become a member, or
5. Find similar information in whois records of the primary domain we are working on by performing a Reverse whois lookup (Reverse by Org Name, reverse by Registrant Mail, etc.)
6. Use the reverse whois tool at [viewdns.info](http://viewdns.info) or the [whoxy.com](http://whoxy.com) tool
7. Check DNS records of relevant domain  and reach other domains using the same DNS records with the “dig” command on the command line

### Subdomains

Tools available to find subdomains:

- SecurityTrails
    - Can be used on the command line via hacktrails or API or queries can be made from the visual interface
- Aquatone
    - collects data and produces output by querying form multiple sources
    - Entering the necessary API keys in the configuration files for the resources that require API keys will increase the number of subdomains it will find.
    - Uses a scan module to check the activity of the subdomains it finds
    - Uses a takeover module to check whether there is a takeover vulnerability on the subdomains it finds

    
- Sublist3r
    - Runs on the command line and finds and outputs from multiple sources
    
    

- Assetfinder
    - Queries subdomains and obtains data from many sources
    

When searching for subdomains, get as much data from as many sources as possible.

## Websites

To find websites, requests must be sent to the domains and subdomains we find.

Active websites are obtained by examining the domains and subdomains that respond to HTTP/HTTPS requests.


When all the domains are listed and scanne dby the “httpx” tppl, it will list all the domains that responf to http/https requests.

An alternative to “httpx” tools is to use “httprobe” tool, a tool that possesses similar functions.

## Login Pages

Detecting websites with login pages can be done manually, however it is a time-consuming process.

To make the detection process easier, simple scripts can be written in “Python”

By sending requests and using the BeautifulSoup libraries in python, we can detect login pages for the websites we have.

For this process:

1. We need to check the background code of the login page and look for indicators that will give us a clue about whether there is a login page or not
2. We can ask the following question to determine whether the page is a login page or not:
    - Is the word "Login" or its corresponding phrase in any language possible on the page?
    - Are form tags used on the page?
    - Are there expressions such as “Username” or “Password” in the placeholder section of the input fields on the page?
    - Are there “Login” or similar expressions in the title or header of the page?
3. If the script we wrote parses the content in the response to answer to answer these questions, we can detect most of the login pages in a short time.

## Technologies Used of Websites

Detecting technologies used on websites will be important for vulnerability intelligence.

Technologies used on websites can be detected using manual methods and multiple tools.

Wappalyzer tool can be used to detect technologies used on pages. 

Alternatives to “Wappalyzer” are “Whatruns”, “BuiltWith” and “Whatcms”

To examine technologies used on websites manually, one could examine the source code of the page and make a technology detection by viewing the file paths of the theme belonging to thr content management system and libraries given in the code, specifically in the script tags.

A second approach would be to examine the header of the responses returned from the page from the developer console. 

Information about the technologies used on the page can be displayed within the header of the returned responses.

## IP Addresses

In order to detect IP addresses of domains and subdomains, the A records of the domains are collected or IP addresses are detected by sending a request and resolving it.

To detect all the active IP addresses contained in the IP blocks used within an organization, requests are sent to all the IP addresses in the block and the active ones are selected.

## IP Blocks

IPs with the highest risk are contained within the IP blocks owned by the organization.

IP blocks can be detected by looking for patterns in the IP addresses obtained from the domains and checking the whois information of consecutive IP addresses to understand whether they belong to the organization or not.

A second approach is to search for keywords of an organization by using the org parameter on Shodan.

The org parameter is a search parameter used for the organization part of the IP addresses.

Alternatives to Shodan are Binaryedge and Zoomeye.

Online tools such as [bgp.he.net](http://bgp.he.net) can be used to detect blocks.

## DNS Records

It’s important to monitor DNS records to detect unknown DNS record changes.

To detect DNS records, use Google’s dig tool or use websites like dnslytics.com

DNS records can also be accessed with the dig command on the command line.

## C- Level Employee Mails

Senior executive emails compromises can result in disaster.  Data transmitted within the mail traffic on a daily basis is crucial for the organization. It is essential to monitor corporate email traffic as well as personal emails.

Several tools frequently used to detect these emails include:

- SalesQL
- RocketReach
- Apollo
- ContactOut

These tools work as chrome extensions.

It is recommended to use a fake email address and fake LinkedIn account when using the tools.

Go to the person’s LinkedIn profile and click on the extension and the extension will list the e-mail addresses they can detect.

### Network Applications and Operating Systems

Discovered services can be collected by querying the IP addresses via Shodan with passive scanning or they can be detected via active scanning.

Network applications and operating system detections can be made according to the responses to the requests sent to the open ports of previously removed IP addresses on the asset list.

## Bin Numbers and Swift Codes

Most import assets to be monitored for matters such as the detection of stolen credit cards on the intelligence side, which are of particular interest to fraud teams in banks.

There public databases designed for the detection of bin number and swift codes such as:

- bincheck.io
    - Filter through bin numbers using the country and bank names
- freebinchecker.com
- bintable.com

Sites to detect Swift codes:

- wise.com
- bank.codes
- theswiftcodes.com

Obtain swift codes by making bank-based inquiries on these sites.

## SSL Certificates

Most important factors for secure communication.

To determine if there is an SSL certificate on the domains that have been detected and add it to the asset list, utilize tools such as “Censys” and “crt.sh”