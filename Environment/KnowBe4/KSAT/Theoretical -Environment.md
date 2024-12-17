Bear with me as this is a PoC (Proof of Concept) showcase. I would more than love to get my hands on the platform to test and fine tune it towards what our team and the organization needs.
## Customer Environment: 
- M365 Workstations, Email, Licensing, etc.
- Azure & AWS services
- MS Entra ID for IdP
- Different KSAT portals for different global regions to adhere to GDPR
## KnowBe4 KSAT/PhishER/PasswordIQ/PAB
- Phishing & Training Email Whitelisting
	-  Advanced Delivery Policies through Microsoft Defender for Office 365
		- DKIM signatures turned on in KSAT console
		- Domains and Sender IPs added to Phishing Simulation in M365
			- Spoof intelligence policy?
- SSO
	- M365 MyApps Tiles Enterprise Application
- User Provisioning
	- SCIM (System for Cross-domain Identity Management)
	- Considerations: 
		- How is the current setup configured?
			- Does every user at corporate receive a license?
			- Is there additional considerations like Salesforce integrations at play?
			- How are the Entra ID user groups configured to mitigate overprovisioning if not?
				- Alias e-mails are not supported.
				- Creating separate SCIM tokens that correlate to specific Entra ID groups would work.
- APIs
	- KSAT console is polled by Sentinel to view if users are completing their security training. If not, their account is locked out to bare minimum permissions via a SOAR playbook. They can only reach the KSAT console to complete training for the most part. When completed their permissions are reinstated.
		- It's a neat way to ensure cybersecurity insurance compliance depending on which provider we're with. 
	- User Event API
		- Data such as user's birthday or out of office can be used
		- Physical access systems can be triggered as well	-  
- PAB
	- Integrated within MS Outlook for the web/workstation/mobile
- KSAT Campaigns
	- custom templates for spearphish prone individuals & offices
	- Built-in Templates for the majority
- PhishER
	- Users are allowed to report phishing emails via the PAB
	- PhishML
	- PhishFlip
		- Defang events are highlighted and dealt with
	- PhishRIP
		- Phishing emails are Quarantined

# Articles
## Whitelisting
[Bypass  Clutter and Spam Filtering](https://support.knowbe4.com/hc/en-us/articles/212723707-Whitelist-by-Email-Headers-in-Microsoft-365-Microsoft-Exchange-2016-and-Microsoft-Exchange-2019)
[Advanced Delivery Policies in Microsoft Defender for Office 365](https://support.knowbe4.com/hc/en-us/articles/4404511190803-Advanced-Delivery-Policies-in-Microsoft-Defender-for-Office-365) - If Microsoft Defender is used and the need to read email headers 
- [video instructions](https://support.knowbe4.com/hc/en-us/articles/4413978898707)
- [Microsoft's article for advanced delivery policies](https://learn.microsoft.com/en-us/defender-office-365/advanced-delivery-policy-configure?view=o365-worldwide)
[Direct Message Injection (DMI) Configuration Guide](https://support.knowbe4.com/hc/en-us/articles/360054494394-Direct-Message-Injection-DMI-Configuration-Guide)

## Hybrid Phish Alert Button (PAB)
[Hybrid Phish Alert Button (PAB) Product Manual](https://support.knowbe4.com/hc/en-us/articles/1500003848221-Hybrid-Phish-Alert-Button-PAB-Product-Manual)
[Graph API-capable Hybrid Phish Alert Button (Graph PAB) Product Manual](https://support.knowbe4.com/hc/en-us/articles/14701808484627-Graph-API-capable-Hybrid-Phish-Alert-Button-Graph-PAB-Product-Manual)
## SAML Single Sign-On (SSO)
[Set Up SAML Single Sign-on (SSO) for the Security Awareness Training Console](https://support.knowbe4.com/hc/en-us/articles/360041935913-Set-Up-SAML-Single-Sign-on-SSO-for-the-Security-Awareness-Training-Console)
[SAML Single Sign-On (SSO) Options](https://support.knowbe4.com/hc/en-us/sections/360000156768-SAML-SSO)
### User Provisioning
[Active Directory Integration (ADI) Configuration Guide](https://support.knowbe4.com/hc/en-us/articles/228373888-Active-Directory-Integration-ADI-Configuration-Guide)
[System for Cross-domain Identity Management (SCIM) Configuration Guide](https://support.knowbe4.com/hc/en-us/articles/360052380374-SCIM-Configuration-Guide)
## API's
[User Event API Overview](https://support.knowbe4.com/hc/en-us/articles/360024863474-User-Event-API-Overview)
[Reporting API Overview](https://support.knowbe4.com/hc/en-us/articles/115016090908-Reporting-API-Overview)
[Product API Overview](https://support.knowbe4.com/hc/en-us/articles/10495383627155-Product-API-Overview)
[KnowBe4 Graph API Overview](https://support.knowbe4.com/hc/en-us/articles/4404258222099-KnowBe4-Graph-API-Overview)
[Webhooks in Your KnowBe4 Console](https://support.knowbe4.com/hc/en-us/articles/10103021848723-Webhooks-in-Your-KnowBe4-Console)
[KnowBe4 API Documentation](https://developer.knowbe4.com/graphql/phisher/page/Introduction)
## PasswordIQ
[PasswordIQ Product Manual](https://support.knowbe4.com/hc/en-us/articles/4406004172435-PasswordIQ-Product-Manual)
