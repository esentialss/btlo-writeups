# Network Analysis – Web Shell

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Easy

**Date:** 04.06.2026

**Category:** Security Operations

**Scenario:** The SOC received an alert in their SIEM for ‘Local to Local Port Scanning’ where an internal private IP began scanning another internal system.

**Warning:** All challenges, websites, and artifacts used in this writeup may contain REAL malicious content. Exercise caution when interacting with any URLs, files, or indicators. Never enter sensitive information and always work in a safe environment.

## Investigation Process

**What is the IP responsible for conducting the port scan activity?**

Open the file, and in wireshark open Statistics menu click Conversations and choose TCP, we can see that 10.251.96.4 is has the most connections.

<img width="489" height="310" alt="image" src="https://github.com/user-attachments/assets/5576067e-0eec-4158-949b-524f5ba65d3a" />

Answer - 10.251.96.4

**What is the port range scanned by the suspicious host?**

Sort Port B from lowest to highest and we can see the lowest and highest port that was scanned.

<img width="344" height="77" alt="image" src="https://github.com/user-attachments/assets/b8567010-7692-45bd-b292-d2237b1062ec" />

<img width="349" height="73" alt="image" src="https://github.com/user-attachments/assets/aea7e293-5c3d-453a-9bea-b1f3e4aa0912" />

Answer - 1-1024

**What is the type of port scan conducted?**

Type tcp.flags.syn == 1 in filters and we can see a lot of SYN without responses.

<img width="1112" height="339" alt="image" src="https://github.com/user-attachments/assets/e445c169-0070-4b00-a4b4-d95c112039b7" />

Answer - TCP SYN

**Two more tools were used to perform reconnaissance against open ports, what were they?**

Type http in filter, and sort Info we can see POST, GET, etc. If we click the POST Packet we can see User-Agent is sqlmap 1.4.7

<img width="946" height="466" alt="image" src="https://github.com/user-attachments/assets/cce60f8b-aa5a-4885-be8a-c89bdd5f468f" />

And if we click the GET Packet we see User-Agent is gobuster 3.0.1

<img width="860" height="351" alt="image" src="https://github.com/user-attachments/assets/a5ebc612-40a6-4144-9e53-0822c827654a" />

Answer - sqlmap 1.4.7, gobuster 3.0.1

**What is the name of the php file through which the attacker uploaded a web shell?**

Filter http.request.method==POST and we can see upload.php packet with editprofile.php referer.

<img width="918" height="300" alt="image" src="https://github.com/user-attachments/assets/ebafc8c4-1a24-4833-b0b1-e5cd702d3305" />

Answer - editprofile.php

**What is the name of the web shell that the attacker uploaded?**

If we analize more the packet we can see name of the uploaded web shell.

<img width="912" height="332" alt="image" src="https://github.com/user-attachments/assets/4d00a2aa-3220-4307-89ec-4dce8d45d996" />

Answer - dbfunctions.php

**What is the parameter used in the web shell for executing commands?**

If we follow TCP stream we can see more information inluding parameter.

<img width="723" height="223" alt="image" src="https://github.com/user-attachments/assets/abed4f0f-6bcb-4539-a045-29aae8075866" />

Answer - cmd

**What is the first command executed by the attacker?**

If we use filter ip.src==10.251.96.4 searching for cmd we can find that the first command was id also looking into the timestamp

<img width="1220" height="280" alt="image" src="https://github.com/user-attachments/assets/f2ceda75-2786-4d33-9f74-df28e4fefa22" />

Answer - id

**What is the type of shell connection the attacker obtains through command execution?**

I found packet with python in the name so i followed the TCP Stream and got some informations.

<img width="1236" height="189" alt="image" src="https://github.com/user-attachments/assets/4cfa5073-7249-4b4b-b1c0-148907ae664c" />

Answer - Reverse

**What is the port he uses for the shell connection?**

We can see port here

<img width="264" height="34" alt="image" src="https://github.com/user-attachments/assets/7c602efe-5559-43bf-9484-cc3440052308" />

Answer - 4422

# Lessons

# Challenge Completed

<img width="793" height="612" alt="{C6DDE576-7F2D-41EF-8C42-3443E825FB6D}" src="https://github.com/user-attachments/assets/da0dd4fb-a939-408b-a1d9-1db350e53728" />
