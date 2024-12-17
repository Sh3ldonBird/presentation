PAB, PhishER, PhishFlip, PhishRIP notes and questions that came up while researching the platform and knowledgebase. Most of it is straight forward.
# PAB
- PAB (Phish Alert Button) is a requirement as users need to report
- Do we currently support shared mailboxes and if we do, what's the Outlook .exe installation method for PAB look like on our end? Intune?
- Do we have multiple instances of the PAB button for different use cases and/or users?
# PhishER
- PhishER is a Security Orchestration, Automation, and Response (SOAR) platform that manages emails that users report
- Do we use integration for CrowsStrike Falcon Sandbox?
# PhishFlip
- Are there any Automatic PhishFlip campaigns in play currently?
- Do we ever highlight reported emails past a certain threshold of failed reporting?- 
# PhishRIP
- What are your thoughts on PhishRIP?
	- How accurate is it and do we have it set up to quarantine? Are we rolling the dice on permanent deletion?
# Articles

[PAB (Phish Alert Burron) Guide](https://support.knowbe4.com/hc/en-us/articles/208969608-Phish-Alert-Button-PAB-Product-Manual)
- PAB communicates with KnowBe4's API over TLS 1.2
	- Information sent to KnowBe4 servers
		- License Key
		- PAB version
		- Operating system (OS)
		- Operating system architecture
		    - This includes 32-bit or 64 bit.
		- Microsoft Outlook version
		- Windows configured language
		    - This is the language code. For example, EN for English, DE for German, and so on.
		- Operating System ID
		    - This is a random GUID generated for each individual workstation.
		- User's email address
		    - We do not store your users' email addresses unless it is already in our system.\
[Microsoft Ribbon Phish Alert Button Product Manual](https://support.knowbe4.com/hc/en-us/articles/26106205842707-Microsoft-Ribbon-Phish-Alert-Button-Product-Manual)
- For M365 non-hybrid mail servers
[Integrate Microsoft Defender for Office 365 with the Phish Alert Button (PAB)](https://support.knowbe4.com/hc/en-us/articles/17538935276051-Integrate-Microsoft-Defender-for-Office-365-with-the-Phish-Alert-Button-PAB)
[Multiple Phish Alert Button Instances (Multi-PAB): Microsoft 365 or Exchange](https://support.knowbe4.com/hc/en-us/articles/115013625907-Multiple-Phish-Alert-Button-Instances-Multi-PAB-Microsoft-365-or-Exchange)
[Set Up Multiple Phish Alert Button Instances (PAB)](https://support.knowbe4.com/hc/en-us/articles/115012103388-Set-Up-Multiple-Phish-Alert-Button-Instances-PAB)


[PhishER Product Manual](https://support.knowbe4.com/hc/en-us/articles/360010802673-PhishER-Product-Manual)



[PhishFlip Guide](https://support.knowbe4.com/hc/en-us/articles/1500005846941-PhishFlip-Guide)

[PhishRIP Guide](https://support.knowbe4.com/hc/en-us/articles/360045742834-PhishRIP-Guide)
