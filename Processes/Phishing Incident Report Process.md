

# Phishing Incident Report Process
This process will underline the steps required to properly create a detailed report of a phishing attack or campaign with the following sections:

- **Email header details, artifacts collected, and a description of the body**
- **Users affected and actions taken to notify them**
- **Analysis process, tools used, and results**
- **Defensive measures taken**
- **Lesson learned**

## 1. Email Header, Artifacts, and Body Content
**Document the following:**

**Artifacts Retrieved**
- Sender: `sender@email.com`
- Reply-to: `reply-to@email.com`
- Date: `Day - Month - Year - Time [Monday 16th September 2019 17:33]`
- Sending Server IP: `xx.xx.xx.xx`
- Reverse DNS: `mail.maliciousserver.com`
- Recipients: `contact@email.com`
- Subject: `Subject Name of Email`
- URL: `http://maliciousdomain.com`
- Attachments: `.pdf, .exe, .bat, .ps, etc...`

Email Description: - `This email contains no malicious URLs or attachments and is attempting to get the recipient to respond, perhaps acting as a recon email or to engage in a social engineering tactics in the future. `

In your chosen note-taking platform, ensure to attach the email file directly to the case, preferably in .eml or .msg format if supported. Include a brief description of the email's content and purpose, along with a screenshot, to facilitate analysis without the need for additional downloads. Although the visual appearance of the email may not be crucial for defensive actions, it serves as valuable data for identifying patterns, targeted attacks, and generating metrics on malicious email trends.

## 2. Analysis of Malicious Artifacts (URLs and Attachments)
**Document the following:**

- URLs: `hxxp://maliciousdomain.com`
*Analysis Tool Used and Description:* `Document tool used, methods and findings from analysis.`

**Example:** 
![](/images/20240509213204.png)

- Attachment Name: `malicious-filename.exe`
- Attachment MD5 Hash: `0c4374d72e166f15acdfe44e9398d026`
- Attachment SHA256 Hash: `240387329dee4f03f98a89a2feff9bf30dcba61fcf614cdac24129da54442762`
*Analysis Tool Used and Description:* `Document tool used, methods and findings from analysis.`

**Example:** 
![](/images/20240509213427.png)
This section of your report demands meticulous attention as it involves evaluating the risk posed by malicious artifacts to the organization. Key inquiries such as determining the malicious nature of URLs or assessing the potential harm of attachments must be addressed, supported by thorough documentation on the analysis techniques and tools utilized. The depth of detail provided here will serve as the foundation for justifying any defensive actions proposed, ensuring that senior analysts can reach the same conclusions as you. 

## 3. Defensive Measures Taken
These are additional details of the actions taken to mitigate and remedy the issue which is added to the email description and report section. The following artifact blocking measures should be observed:

- Email artifact blocking (*subject line, sending address, sending server IP*)
- Web artifact blocking (*URL, domain, IP*)
- File artifact blocking (*file name, hash*)

These measures must be documented whether the analyst can conduct the actions themselves or escalated to a senior analyst.

![](/images/20240509213051.png)

## Note: Sanitize URLs and IP Addresses

The rules for doing this are simple:

- Surround the “**.**” within URLs and IP addresses with a “**[]**” to become “**[.]**”.
- Change the “**tt**” to “**xx**” within the **http** of URLs to become “**hxxp**”.

![](/images/20240509221738.png)

