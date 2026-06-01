# Phishing Analysis

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Easy

**Date:** 01.06.2026

**Category:** Security Operations

**Scenario:** A user has received a phishing email and forwarded it to the SOC. Can you investigate the email and attachment to collect useful artifacts?

**Warning:** The website and phishing kit used in this challenge 
are REAL. Exercise caution when interacting with 
the malicious website and do not enter any sensitive 
information.

## Investigation Process

**Who is the primary recipient of this email?**

First we have to download Phishing Email file, next open in outlook for html view and in text editor for Head, Body, etc. view.

<img width="459" height="89" alt="image" src="https://github.com/user-attachments/assets/bfe98483-86b7-481d-9b62-2686d63ca981" />

I opened email in outlook and I saw the email was sent to kinnar1975@yahoo.co.uk so kinnar1975@yahoo.co.uk is the primary recipient.

**What is the subject of this email?**

I found the subject in the "Subject:" header field of the email.

Subject: Undeliverable: Website contact form submission

**What is the date and time the email was sent?**

In the "Sent:" header we can see date and time when email was sent.

Sent: 18 March 2021 04:14

**What is the Originating IP?**

First thing I noticed is that we can't see IP addresses in the outlook, so I head over to Phishing Email file in the text editor.

Next step I did is CTRL+F so I could find Originating IP faster, in the search bar I typed Originating and found the IP.

<img width="253" height="22" alt="{CC8C62D8-5BAC-41AA-9823-E33313EA96AE}" src="https://github.com/user-attachments/assets/1f00a0e2-0fc5-4030-86df-5ec5183529fd" />

The Originating IP is 103.9.171.10

**Perform reverse DNS on this IP address, what is the resolved host? (whois.domaintools.com)**

On whois.domaintools.com I entered the IP address, and I received detailed IP information but we are looking for Resolve Host.

In Quick Stats we can see that Resolve Host is c5s2-1e-syd.hosting-services.net.au 

<img width="745" height="201" alt="{D7CE484D-2BD8-4E37-80DF-4F991F973F90}" src="https://github.com/user-attachments/assets/6d76bd99-c5aa-49db-92a0-3abae05b8a9c" />

**What is the name of the attached file?**

In outlook on top of the email we can see that name of attached file is Website contact form submission

<img width="741" height="210" alt="{BD710B1D-C879-4B82-9366-FD7A3F717B66}" src="https://github.com/user-attachments/assets/609dae62-1758-4f75-963e-d8c9545e190a" />

**What is the URL found inside the attachment?**

I opened the attached file and found that URL is https://35000usdperwwekpodf.blogspot.sg?p=9swghttps://35000usdperwwekpodf.blogspot.co.il?o=0hnd

<img width="554" height="230" alt="{0C8FF45F-AC2E-40E6-A050-C5923AA8D6E2}" src="https://github.com/user-attachments/assets/2b97d623-8ce8-4fc6-988c-dec83fcca31c" />

**What service is this webpage hosted on?**

By analyzing the URL we can see that the hosting service is Blogspot

**Using URL2PNG, what is the heading text on this page? (Doesn't matter if the page has been taken down!)**

In URL2PNG site I pasted the url and found the heading text: Blog has been removed

# Challenge Completed

<img width="795" height="613" alt="{E026F7D4-E20F-40F0-A138-BB8804965882}" src="https://github.com/user-attachments/assets/fddf167b-854a-41f2-84db-3e368952d7fc" />
