
# Manual Artifact Analysis Process


1. **Upload files, attachments and the URL to https://www.virustotal.com/gui/home/upload.** Verify the reputation status of the artifacts.
- How long has it existed on the internet?
- What is the HTTP status code?

2. **Perform analysis on SHA256 string of attachment or file on https://www.talosintelligence.com/talos_file_reputation.**
- Identify the results and reputation of file. Is it malicious?

4. **Identify what the URL is displaying https://www.url2png.com/.**
- What is the HTML displaying?
- What information can we gather from looking at this?
- To get a better look we can right-click the image pane, go to Inspect Element, and copy the img id sample URL and paste this into a new browser tab. 

5. **Enter the URL into https://whois.domaintools.com/.**
- How long has it existed on the internet?
- What other information can we gather here?
- If the page has only existed for only a few days, It is safe to say that it is malicious. Otherwise, it may be a legitimate site which was compromised.

6. **Check the root domain of URL at https://www.url2png.com/.** 
- Is it a legitimate website? Is the page loading to a homepage?

7. **Enter the root domain into https://www.wannabrowser.net/ to identify HTTP response codes?**
- Evaluate the response codes

8. **Enter the full URL into https://www.wannabrowser.net/ to identify HTTP response codes?**
- Evaluate the response codes
- Is this an legitimate website?

9. **Enter the URL into the https://www.hybrid-analysis.com/ to confirm if malware is present.**
- Are there any malicious indicators or flags?
- What are the MITRE ATT&CK Framework TTPs that are being used?

10. **Search the https://urlhaus.abuse.ch/ database.** 
- Are there any malicious indicators or flags for this URL?





