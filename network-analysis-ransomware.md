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

I used the HTTP filter and saw a GET request. I inspected it and found the IP address, port, and filename.

<img width="753" height="196" alt="image" src="https://github.com/user-attachments/assets/966c1b8a-364f-40e4-998a-f4db8022c200" />

Answer - http://10.0.2.15:8000/safecrypt.exe

**Name the ransomware executable file?**

safecrypt.exe is the executable file.

Answer - safecrypt.exe

**What is the MD5 hash of the ransomware?**
We need to export the object, so select the Request URI.

<img width="365" height="69" alt="image" src="https://github.com/user-attachments/assets/a98697a6-9cdc-44b9-972e-08ea6587a4aa" />

Next, go to File → Export Objects → HTTP.

<img width="737" height="79" alt="image" src="https://github.com/user-attachments/assets/3160f99c-4844-4098-8402-21486cb02848" />

Export the file, then calculate its MD5 hash using the md5sum command in the terminal.

<img width="958" height="32" alt="image" src="https://github.com/user-attachments/assets/3db1da7e-e906-48f4-b2f5-79affcc4036f" />

Answer - 4a1d88603b1007825a9c6b36d1e5de44

**What is the name of the ransomware?**

By submitting the hash to VirusTotal, we can obtain additional information about the malware.

<img width="1832" height="382" alt="image" src="https://github.com/user-attachments/assets/55dc9c83-6123-44b7-adca-e7fa7abfacf9" />

Answer - teslacrypt

**What is the encryption algorithm used by the ransomware, according to the ransom note?**

We can check it here

<img width="426" height="33" alt="image" src="https://github.com/user-attachments/assets/3468da6b-3d43-4668-873a-418b6b52437a" />

Answer - RSA-4096

**What is the domain beginning with ‘d’ that is related to ransomware traffic?**

By filtering DNS traffic, we can identify the related domain.

<img width="250" height="86" alt="image" src="https://github.com/user-attachments/assets/008a6ba2-b959-488e-a2f6-896f726d78fe" />

Answer - dunyamuzelerimuzesi.com

**Decrypt the Tender document and submit the flag**

I downloaded BloodDolly's TeslaDecoder and used it to decrypt the file.

Answer - BTLO-T3nd3r-Fl@g

# Lessons

- Statistics → Capture File Properties reveals operating system details of the captured host.
- HTTP GET requests can be used to identify downloaded malware and its source URL.
- File → Export Objects → HTTP allows extracted files to be recovered from network captures.
- MD5 hashes can be used to identify malware by searching services such as VirusTotal.

# Challenge Completed

<img width="795" height="611" alt="{A9CAFD32-3842-46D3-A4A6-D2DABE86B2F6}" src="https://github.com/user-attachments/assets/7b3402ab-437b-443b-969a-5d2b3dddd193" />
