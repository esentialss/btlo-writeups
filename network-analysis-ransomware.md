# Network Analysis - Ransomware

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Medium

**Date:** 08.06.2026

**Category:** Security Operations

**Scenario:** ABC Industries worked day and night for a month to prepare a tender document for a prestigious project that would secure the company’s financial future. The company was hit by ransomware, believed to be conducted by a competitor, and the final version of the tender document was encrypted. Right now they are in need of an expert who can decrypt this critical document. All we have is the network traffic, the ransom note, and the encrypted ender document. Do your thing Defender!​

**Warning:** All challenges, websites, and artifacts used in this writeup may contain REAL malicious content. Exercise caution when interacting with any URLs, files, or indicators. Never enter sensitive information and always work in a safe environment.

## Investigation Process

**What is the operating system of the host from which the network traffic was captured? (Look at Capture File Properties, copy the details exactly)**

Statistics -> Capture File Properies and we have OS name.

<img width="660" height="97" alt="image" src="https://github.com/user-attachments/assets/d5890df1-396d-479a-9318-6894bb222b67" />

Answer - 32-bit Windows 7 Service Pack 1, build 7601

**What is the full URL from which the ransomware executable was downloaded?**

I used http filter and saw GET method so i checked this and got IP, Port and filename.

<img width="753" height="196" alt="image" src="https://github.com/user-attachments/assets/966c1b8a-364f-40e4-998a-f4db8022c200" />

Answer - http://10.0.2.15:8000/safecrypt.exe

**Name the ransomware executable file?**

safecrypt.exe is the executable file.

Answer - safecrypt.exe

**What is the MD5 hash of the ransomware?**
We need to export this object so select Request URI 

<img width="365" height="69" alt="image" src="https://github.com/user-attachments/assets/a98697a6-9cdc-44b9-972e-08ea6587a4aa" />

Next File -> Export Objects -> HTTP

<img width="737" height="79" alt="image" src="https://github.com/user-attachments/assets/3160f99c-4844-4098-8402-21486cb02848" />

Select and export, next step we do is checking the hash with md5sum in terminal.

<img width="958" height="32" alt="image" src="https://github.com/user-attachments/assets/3db1da7e-e906-48f4-b2f5-79affcc4036f" />

Answer - 4a1d88603b1007825a9c6b36d1e5de44

**What is the name of the ransomware?**

If we paste hash in VirusTotal we can have a lot of information.







