

1. Open up **PhishTool**, login, and drag the email into the analysis console.

2. **Check the File Artifacts - attachments** (Example: PDF, DOC, ETC...). We have been provided with the MD5 hash value. If we *click on the “VirusTotal” link to the right-hand side PhishTool* will generate a search query for the MD5 hash and take us to the report page so we can perform a quick reputation check and see whether the security community has marked this file as malicious or not.

- If this file hasn’t been reported as malicious, we can *open this inside a snapshotted VM*. In this case, we’re using a Kali VM. So we’ll drag the PDF into our VM, disconnect from the network in case there’s any nasty surprised inside that attempt to call out and download other files, and open the PDF. 

3. **Analyze the Web Artifacts - URLs that was included in the email.** If we click on the URL at the bottom of the analysis console we can perform two actions, a *web capture*, and a *WHOIS lookup*. 
- Let’s start with the *web capture* so see what’s on this URL. In the bottom section, we’re also able to view the headers from the URL request, and the HTTP request on the left-hand side.
- Doing a *WHOIS lookup* will give us information about the domain.

4. **Perform a reputation check on the URL with VirusTotal.** Since we checked the file MD5 hash in VirusTotal, we should also check the URL to see if it has been recognized as malicious. 
- We can copy the URL by clicking the clipboard icon, going to VirusTotal.com, and searching for it under the URL heading.  
- We can also double check the root domain by removing the URL ending.