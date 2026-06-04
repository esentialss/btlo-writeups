# Phishing Analysis 2

**Platform:** <a href="https://blueteamlabs.online/">Blue Team Labs Online</a>

**Difficulty:** Easy

**Date:** 02.06.2026

**Category:** Security Operations

**Scenario:** Put your phishing analysis skils to the test by triaging and collecting information about a recent phishing campaign.

**Warning:** All challenges, websites, and artifacts used in this writeup may contain REAL malicious content. Exercise caution when interacting with any URLs, files, or indicators. Never enter sensitive information and always work in a safe environment.

## Investigation Process

**What is the sending email address?**

<img width="281" height="70" alt="{5FEFB8D0-788A-428F-B4F4-22F218942FC5}" src="https://github.com/user-attachments/assets/b8fe3e9e-29d6-42fc-a934-df575039c8f2" />

We can see that email was sent from amazon@zyevantoby.cn address.

**What is the recipient email address?**

If we click the name field where is recipient username we can notice email address of the recipient.

<img width="256" height="77" alt="{60767C8A-479D-445A-A2D6-6E903984EDBB}" src="https://github.com/user-attachments/assets/f3d78ac4-c4d4-4bb6-80c7-7584785ceb4c" />

The recipient email address is saintington73@outlook.com

**What is the subject line of the email?**

On left-top of the email we can see the subject.

<img width="230" height="31" alt="{E9A49AFC-1666-49F1-9716-0FD3561B6437}" src="https://github.com/user-attachments/assets/b8c1c4e0-2df6-4566-8b2a-c9ca8f2e217c" />

The subject line of the email is Your Account has been locked

**What company is the attacker trying to imitate?**

That was the first thing I noticed.

<img width="193" height="76" alt="{49CC8E60-2116-4707-8E68-C960E4A6FDE8}" src="https://github.com/user-attachments/assets/1cd74ce8-acc9-46ee-94bd-e0d6d8109e32" />

Name of the company which attacker is trying to imitate is Amazon

**What is the date and time the email was sent? (As copied from a text editor)**

If we open a Phishing Email in text editor we can see more detailed information.

First thing I did after opening text editor I used CTRL+F and typed "Date" so I could find the date faster.

<img width="489" height="128" alt="{DAF468B2-ED65-43FA-9929-2B27FB148E34}" src="https://github.com/user-attachments/assets/697fdb53-f8b2-47d0-a958-4b893e04aed9" />

And we have date and time when the email was sent. Wed, 14 Jul 2021 01:40:32 +0900

**What is the URL of the main call-to-action button?**

I pointed on the cta button and right clicked so I could copy the URL.

The URL: https://emea01.safelinks.protection.outlook.com/?url=https%3A%2F%2Famaozn.zzyuchengzhika.cn%2F%3Fmailtoken%3Dsaintington73%40outlook.com&data=04%7C01%7C%7C70072381ba6e49d1d12d08d94632811e%7C84df9e7fe9f640afb435aaaaaaaaaaaa%7C1%7C0%7C637618004988892053%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=oPvTW08ASiViZTLfMECsvwDvguT6ODYKPQZNK3203m0%3D&reserved=0

<img width="585" height="122" alt="{5FD3D1F1-0AB4-4422-ABCB-3FB24137900F}" src="https://github.com/user-attachments/assets/0975468e-db99-4845-8ba3-4411973fb12e" />

**Look at the URL using URL2PNG. What is the first sentence (heading) displayed on this site? (regardless of whether you think the site is malicious or not)**

I pasted the URL in URL2PNG site and saw only Bad Request because I pasted full URL with https://emea01.safelinks.protection.outlook.com/?url= in the beginning and I should paste without it.

<img width="77" height="25" alt="{CB52EF13-F9C3-4121-992D-E3A602B3805F}" src="https://github.com/user-attachments/assets/62e41dd3-b3ab-4ddf-9da0-18cb4b4ebfda" />

So I pasted and this also didn't work, so I debugged the URL on this site https://www.urldecoder.org/ and tried again but again it didn't work.

Next I tried to see the page on web.archive.org I pasted the full URL and it worked.

<img width="1886" height="523" alt="{6C664000-68D8-4D42-8F81-DB28FBA2A548}" src="https://github.com/user-attachments/assets/fb369cee-df68-4b8a-84a3-43df7ea7bc3c" />

The answer is This web page could not be loaded.

**When looking at the main body content in a text editor, what encoding scheme is being used?**

I opened the text editor, again I used CTRL+F, for faster searching, in the search bar I typed encoding and found that the encoding scheme is base64.

<img width="354" height="82" alt="{35A12AAD-239C-4D83-B9CA-9B578BE1D9B6}" src="https://github.com/user-attachments/assets/89d9c539-02b5-4af7-8374-8235ff20f928" />

**What is the URL used to retrieve the company's logo in the email?**

In outlook I right clicked in the company logo and copied the photo URL https://images.squarespace-cdn.com/content/52e2b6d3e4b06446e8bf13ed/1500584238342-OX2L298XVSKF8AO6I3SV/amazon-logo?format=750w&content-type=image%2Fpng

<img width="407" height="244" alt="{3315BE64-D204-4FBE-90BF-355FE6903469}" src="https://github.com/user-attachments/assets/d52decf4-eb20-4eb7-a123-13d7690c792f" />

**For some unknown reason one of the URLs contains a Facebook profile URL. What is the username (not necessarily the display name) of this account, based on the URL?**

First URL I checked was the sent URL and thought that the zzyuchengzhika text in the URL is the answer but not, so next URL I checked was in the Amazon Support Team text and when I hovered over it I could see the URL

<img width="144" height="22" alt="{85D8302A-B7C0-4849-B99E-EBFB6D558AED}" src="https://github.com/user-attachments/assets/511a58e2-ca6f-47d3-ba7f-291e03afeb23" />

I found the Facebook URL containing username amir.boyka.7, however the accepted answer was the display name: Famir.boyka.7

# Lessons

- If you can't see a preview of the site in URL2PNG, 
  you can use Web Archive (web.archive.org)
- Carefully checking URLs can reveal information 
  that the attacker didn't intend to reveal
- Microsoft SafeLinks is a function in Outlook 
  that wraps URLs, if the URL is malicious it 
  blocks and warns the user, if it's safe it 
  redirects the user to the original site
- When analyzing phishing emails from Outlook, 
  the real URL is hidden inside SafeLinks and 
  must be extracted before analysis

# Challenge Completed

<img width="798" height="614" alt="{B999D701-E876-4724-B50F-4913A98A80EC}" src="https://github.com/user-attachments/assets/874eb30d-008c-4f5d-b101-64d765b64414" />

