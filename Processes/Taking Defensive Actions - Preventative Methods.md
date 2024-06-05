
# Taking Defensive Actions - Preventative Methods


## 1. Marking External Emails
- A common way to inform users that an email is external and coming from an outside source from the environment or network is to label it as such. We can set specific rules with platforms such as Microsoft Exchange and Office 365 that allows the subject line to be altered - External Email.

![](images/20240506192421.png)

The same method can be applied to automatically add warning messages to the start of the body content instead of (or as well as) appending the subject line, and styling can be applied such as making the text red so it stands out more, and means the employee is more likely to read it and proceed with caution.

## 2. Email Security Technology
- **Sender Policy Framework (SPF)** - This is essentially a DNS record type specifically created to help prevent an email address form being forged by establishing a policy on the domain. Having a record establish on your domain prevents a malicious actor from spoofing it. This is established by the SPF TXT record by specifying the following: *Declaration of the record type, the IP addresses and the external domains allowed to send the emails, and an enforcement rule.*
Basic syntax of the record is: `v=spf <IP> <enforcement rule>`
Example: `v=spf1 a: include:mailgun.org protection.outlook.com -all`

Our record declares that it's an SPF record and it's sent from `mailgun.org` and `protection.outlook.com`. The `-all` specifies that the email will show a hard fail if the domain is spoofed.

- **Domain Keys Identified Mail (DKIM)** - This is a method of email authentication where an *encrypted hash of the email is created and a private key is distributed from the sender's domain*. This will be stored in the header of the email. If that hash that was sent to the recipient doesn't match the newly generated hash created by the receiving server, this will indicate that the email is possibly fraudulent and it's integrity is not insured.
Basic syntax of the record is: `V=DKIM <key type> <public key>`

- **Domain-based Message Authentication, Reporting and Conformance (DMARC)** - An email authentication, policy and protocol largely based off the concepts of SPF and DKIM. This type of record dictates what would happen if both SPD and DMARC failed checks. There are three basic options that an email server can take: none, quarantine, and reject.

Basic syntax of the record is: `v=DMARC1 <action> <report address>`
Example: mywebsite.com would have the following DMARC record...
`v=DMARC1; p=reject; rua=contact@mywebsite.com`

## 3. Spam Filter
- **Content Filter** - A content filter is the classic depiction of a spam filter and uses information in the email header and body to try to determine whether the email is legitimate or spam.
- **Rule-Based Filter** - A rule-based filter allows for emails to be filtered based on predetermined criteria.  A good example of this is Mail Flow rules in Microsoft Exchange where you could say:

_If the subject or body contains “FREE OFFER” and the Sender is located Outside of the Organization, raise the likelihood of the message being spam_


- **Bayesian Filter** -  Bayesian filters have become one of the most intelligent types of spam filters that can be used.  This is because it can often utilize concepts such as machine learning, to learn the users’ spam preferences.  For example, when the user marks an email as spam, it can analyze the characteristics of that message and use that information to block similar messages from going to the inbox.  One slight downside to this kind of filter, however, is that it can often require a large amount of spam to efficiently utilize the machine learning capabilities.

## 4. Attachment Filtering
- Email gateways and email security tools will often allow for different actions to be taken once a certain attachment has been identified, such as scanning it for malicious indicators, blocking the email from being delivered, quarantining the email, stripping the attachment, alerting the email gateway administrator, sending an email to specific recipients about the activity (such as the security team), or generating logs which can be ingested by a SIEM platform and used to generate an alert for security analysts to investigate. The most obvious file types that are used for malicious activity are:

- **.exe** (Executable)
- **.vbs** (Visual Basic Script)
- **.js** (JavaScript)
- **.iso** (Optical Disk Image)
- **.bat** (Windows Batch File)
- **.ps/.ps1** (PowerShell Scripts)
- **.htm/.html** (Web Pages / Hypertext Markup Language)

## 5. Attachment Sandboxing
- Emails that include file attachments are extracted and analyzed, and files are detonated (run) in a virtual environment, where everything is monitored to actually see what happens when a file is executed. If any malicious indicators are observed, such as trying to download additional files from a malicious domain or trying to create or alter existing processes, the attachment is classed as malicious, and the email will not be delivered.

## 6. Security Awareness Training
**Educating users on the following:**
- Coming from an unknown source and sending address.
- Improper grammar and spelling mistakes.
- Poor styling.
- Trying to get the recipient to click on a button or complete an action.
- Suspicious URLs and attachments.

**Simulated Phishing Attacks**
- It is common for security-conscious organizations to launch simulated phishing attacks against their own employees in order to determine how effective their current security awareness training is. There are a number of security services that offer phishing attacks as a service, and allow you to customize the email that will be sent to mailboxes under the organization’s domain. If the user clicks on a “malicious” link, they will be redirected to a safe website (typically owned by the company conducting the simulated attack) and will inform them that they have just fallen for a phishing email.

