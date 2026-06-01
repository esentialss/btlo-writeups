# Phishing Analysis

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Easy

**Date:** 01.06.2026

**Category:** Security Operations

**Scenario:** A user has received a phishing email and forwarded it to the SOC. Can you investigate the email and attachment to collect useful artifacts?

## Investigation Process

**Who is the primary recipient of this email?**

First we have to download Phishing Email file, next open in outlook for html view and in text editor for Head, Body, etc. view.

<img width="459" height="89" alt="image" src="https://github.com/user-attachments/assets/bfe98483-86b7-481d-9b62-2686d63ca981" />

I opened email in outlook and i saw the email was sent to kinnar1975@yahoo.co.uk so kinnar1975@yahoo.co.uk is the primary recipient.

**What is the subject of this email?**

I found the subject in the "Subject:" header field of the email.

Subject: Undeliverable: Website contact form submission

**What is the date and time the email was sent?**

In the "Sent:" header we can see date and time when email was sent.

Sent: 18 March 2021 04:14

**What is the Originating IP?**

First thing i noticed is that we can't see IP adresses in the outlook, so i head over to Phishing Email file in the text editor.

Next step i did is CTRL+F so i could find Originating IP faster, in the search bar i typed Originating and found the ip.

<img width="253" height="22" alt="{CC8C62D8-5BAC-41AA-9823-E33313EA96AE}" src="https://github.com/user-attachments/assets/1f00a0e2-0fc5-4030-86df-5ec5183529fd" />

The Originating IP is 103.9.171.10

**Perform reverse DNS on this IP address, what is the resolved host? (whois.domaintools.com)**

On whois.domaintools.com i put the IP adress, and i got a lot of IP Information but we are looking for Resolve Host.

In Quick Stats we can see that Resolve Host is c5s2-1e-syd.hosting-services.net.au 

<img width="745" height="201" alt="{D7CE484D-2BD8-4E37-80DF-4F991F973F90}" src="https://github.com/user-attachments/assets/6d76bd99-c5aa-49db-92a0-3abae05b8a9c" />
