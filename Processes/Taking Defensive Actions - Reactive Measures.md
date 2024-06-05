
# Taking Defensive Actions - Reactive Measures

## 1. Blocking Email Artifacts
- **Email Sender (mailbox@domain)** - Block this email on the email gateway to stop incoming and outgoing emails.
- **Sender Domain (@domain)** - This is typically only done when the *sending domain is purely malicious or is using a large number of mailboxes to send malicious emails*. However, we must also consider the domain we are blocking as well. When receiving emails form common domains like @outlook or @gmail, it obvious not feasible to block these entire domains as it can potential block legitimate emails.
- **Sending Server IP** - This is a very serious block which is not conducted unless necessary. Although similar to a domain block in some respect, a domain may use multiple sending servers. *Only block IPs that have been confirmed malicious or have been compromised.*
- **Subject Line** -  While multiple sending addresses can be delivering the same phishing email, if they all share the same subject line we can easily catch them all, instead of blocking multiple senders, by dropping any emails with the subject line in question.

## 2. Blocking Web Artifacts
Blocking malicious web sites is critical when keeping an environment safe, specifically when you're dealing with web artifacts and malicious URLs. One of the most consistent ways to that environment safe is to implement a web proxy at the perimeter that can monitor network connections -- allowing and disallowing connectivity.

###### Web Proxy

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cc680558d07aba1834ee1640db2e413cb9eec8bbbc7e7f89de3783579046f78182091e6242804d12af0fff4ddfde.png)

There are two types of blocks we can make at the perimeter on the web proxy -- *URL and Domain block.*

-  **URL Blocks** - These type of blocks are extremely specific to the entire URL that has been provided. Instead of blocking the entire URL, it'll probably be more efficient to block a portion of the URL. Sometimes URL are dynamically generated for a specific recipient. So when deciding on a URL block, work out if the full URL is static and would work for all recipients, or if there is an obviously malicious directory where the URL block can end.
- **Domain Blocks** - This will essentially block the access to the entire domain. If necessary -- after an investigation that this domain was deemed unsafe -- take the precautions to block it. However, we must also take in consideration if that domain is possibly connected to needed services. These decisions will be made during the investigation of the artifacts.
- **DNS Blackholing** - An additional step and precaution to ensure that the environment is safe is to create an fake DNS entry as a protective measure. Blackholing is the process of creating a fake entry so that if an employee accidentally clicks on a link they will be taken to another site. This measure can be made in tandem with a URL or Domain Block as well.
- **IP Blocking** -  When there are multiple malicious sites being hosted on the same IP, if there is no legitimate resource that the business would need access to running on that IP, we can block that server to prevent access to any of the sites on it. This is an extreme measure, and is typically not conducted when regarding phishing, and is often used to block IPs that are scanning or attacking the organization.
## 3. Blocking File Artifacts
- **Hash Blocking** - We can block the MD5, SHA1, or SHA256 hash within the *organization’s endpoint detection and response (EDR) tool*. This means whenever the hash becomes present on a protected endpoint, the software will recognize and delete it immediately before it is able to run. However, we must keep in mind that commodity software which is frequently sold online can edit itself and add additional trash data to it's code, changing the hash altogether.
- **Blocking File Names** -  Possibly one the first things to do when mitigating this artifact is to block it by filename to stop the bleeding per se. However, this probably is not the most effective method long term unless the file name is extremely unique. We must consider the ramifications if the filename is common which will render other legitimate files to being blocked as well.

## 4. Things to consider
- Was the domain created for malicious purposes?
- If the domain is legitimate how long has it been compromised?
- Does the employees need to access the compromised website for business purposes? If so, do we need to block only a portion of the URL or the whole domain?