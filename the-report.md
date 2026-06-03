# The Report

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Easy

**Date:** 03.06.2026

**Category:** Security Operations

**Scenario:** You are working in a newly established SOC where still there is lot of work to do to make it a fully functional one. As part of gathering intel you were assigned a task to study a threat report released in 2022 and suggest some useful outcomes for your SOC.

**Warning:** 
All challenges, websites, and artifacts used 
in this writeup may contain REAL malicious content. 
Exercise caution when interacting with any URLs, 
files, or indicators. Never enter sensitive 
information and always work in a safe environment.

## Investigation Process

**Question 1) Name the supply chain attack related to Java logging library in the end of 2021 (Format: AttackNickname)**

I opened the report used CTRL+F typing Java and found answer


<img width="417" height="161" alt="{78825875-2823-4645-B9E3-8091E0774000}" src="https://github.com/user-attachments/assets/3050fe82-a4b7-4866-a076-b1f5ad972d7e" />

Answer - Log4j

**Question 2) Mention the MITRE Technique ID which effected more than 50% of the customers (Format: TXXXX)**

I opened Techniques page and found out that ID of MITRE Technique which effect more than 50% is a T1059

<img width="596" height="82" alt="{73D18E9E-47AA-4863-8616-E24B42BB1F77}" src="https://github.com/user-attachments/assets/1be47fb0-35ac-4eb2-887e-aa58680cd85b" />

Answer - T1059

**Question 3) Submit the names of 2 vulnerabilities belonging to Exchange Servers (Format: VulnNickname, VulnNickname)**

In top of the vulnerabilities page (17), we can see 2 names.

<img width="399" height="62" alt="{D62D72EC-0FCC-457E-B508-8B24B7DB93B1}" src="https://github.com/user-attachments/assets/602df4c8-161c-4268-b82e-535df0462dd0" />

<img width="386" height="58" alt="{B60F94D2-2660-4719-95AC-D2E1CD566B58}" src="https://github.com/user-attachments/assets/6bfa35aa-ec0a-48b4-93dd-9229a312ec6d" />

Answer - ProxyLogon, ProxyShell

**Question 4) Submit the CVE of the zero day vulnerability of a driver which led to RCE and gain SYSTEM privileges (Format: CVE-XXXX-XXXXX)**

I used CTRL+F searching zero and found two vulnerability so I read the description of them and description of PrintNightmare was matching the question.

<img width="420" height="194" alt="{93D0B793-958E-4A13-9F8C-188D49F39EEF}" src="https://github.com/user-attachments/assets/ac1c6be0-525c-43d1-bd7b-cb1f3c086a49" />

Answer - CVE-2021-34527

**Question 5) Mention the 2 adversary groups that leverage SEO to gain initial access (Format: Group1, Group2)**

Again CTRL+F for fast searching, typed SEO and found these two groups.

<img width="427" height="77" alt="{2E148F59-4626-43CE-AF2E-B8BFDAC8C81A}" src="https://github.com/user-attachments/assets/035c5811-83da-4f3a-96c2-4eccc66b6b94" />

Answer - Gootkit, Yellow Cockatoo

**Question 6) In the detection rule, what should be mentioned as parent process if we are looking for execution of malicious js files [Hint: Not CMD] (Format: ParentProcessName.exe)**

CTRL+F typed javascript files and search for the answer.

<img width="410" height="100" alt="{3B1D85F3-8D09-4645-A195-58CB09546697}" src="https://github.com/user-attachments/assets/734906f5-4d2d-40a0-8dfc-c6a3566f9e3a" />

Answer - wscript.exe

**Question 7) Ransomware gangs started using affiliate model to gain initial access. Name the precursors used by affiliates of Conti ransomware group (Format: Affiliate1, Affiliate2, Afilliate3)**

CTRL+F typed affilate and again search for the answer.

<img width="431" height="271" alt="{52E9866F-471A-4986-9463-07367FCC6BBE}" src="https://github.com/user-attachments/assets/795c13ed-18b8-4a97-a897-bdb46d7c49f7" />

Answer - Qbot, Bazar, IcedID

**Question 8) The main target of coin miners was outdated software. Mention the 2 outdated software mentioned in the report (Format: Software1, Software2)**

CTRL+F typed coinminers and found the answer.

<img width="417" height="115" alt="{BB8F881A-E2A3-400B-9D26-15BBA7A3E3FD}" src="https://github.com/user-attachments/assets/f52319d2-cd5a-46d7-96fa-5a756cd3a0a3" />

Answer - JBoss, WebLogic

**Question 9) Name the ransomware group which threatened to conduct DDoS if they didn't pay ransom (Format: GroupName)**

CTRL+F typed DDoS and search for the answer.

<img width="412" height="90" alt="{FD07612C-5EE4-4790-81FE-6A98CFA45B8F}" src="https://github.com/user-attachments/assets/70adf62a-47d7-4cd9-9c68-f041e7cd209c" />

Answer - Fancy Lazarus

**Question 10) What is the security measure we need to enable for RDP connections in order to safeguard from ransomware attacks? (Format: XXX)**

CTRL+F typed RDP and found that connections without MFA are a common ransomware vectors.

<img width="417" height="138" alt="{BC3FEA08-56FF-4405-B8DD-874E8872FBAB}" src="https://github.com/user-attachments/assets/5efd63bd-6762-4fa6-8f74-e256fd2930f4" />

Answer - MFA

# Lessons
 
- Log4j is a Java logging library that 
  had a critical vulnerability which attackers exploited
- Ransomware groups use affiliate models to recruit 
  partners for attacks
- Enabling MFA on RDP connections can prevent 
  ransomware attacks

# Challenge Completed

<img width="789" height="604" alt="{E430F47F-E670-4697-AD33-8E56458B663A}" src="https://github.com/user-attachments/assets/3702b5ae-1109-4e87-8bff-49afccfb07f8" />
