Scratch notes and questions that came up while reading through the knowledge base. Most if not all got answered.

# Questions for hiring manager
 - What is the current project scope for KnowBe4?
	 - Is it fully rolled out and automated or is there still a need for setup?
	 - Are we in a specific phase of setup if yes?
## Workflows
### Setup
#### Whitelisting
- How often do we work with the email team to whitelist new emails/accounts or do we have all of that automated at the moment? If not, is that a project I may undertake?
- Do we have PIM (Privileged Identity Management) roles in place for Exchange Admin and how granular does it go?
- Being on a security team, I feel I won't have these permissions and will need to interface with the email team. What kind of change management is involved if any?
- Because we're a global company and work with employees that utilize many different languages, what is the process for proofreading phishing tests before they go out or is that handled by knowbe4?
	- **Check
- How much of the process has been automated with PowerShell so far?
- Do we use Direct Message Injection (DMI) or do we whitelist simulated phishing emails?
	- Looks like It can only be used in public MS Azure instances, not MS GCC High or DoD instances.
		- Is this to say there's a security vulnerability with the secure KSAT console?
	- It works with phishing test emails, but training emails require additional whitelisting.
	- Microsoft recommends that we attempt to whitelist using MS's advanced delivery policies first before attempting DMI.
	- Looks like it's becoming deprecated.
##### Smart Hosting (M365 Skip Listing)
https://support.knowbe4.com/hc/en-us/articles/360000568187-Smart-Hosting-Guide
- Do we use Smart Hosting to bypass any spam filters for phishing tests?
	- I suppose we could whitelist the testing...but it seems like a massive security vulnerability if attackers knew we were using knowbe4...
		- Spoofed email/IP addresses & domain spoofing if we didn't have proper SPF/DKIM/DMARC policies enforced
		- Do we use Advanced Threat Protection with Microsoft Defender for Office 365 to mitigate threats if using skip listing? or do we sandbox them?
- Why oh why do they call their Phishing Security Tests... PSTs? That gives me PTSD from on-premise Microsoft Exchange 2010/13 servers.
#### Setting Up the PAB
The PAB allows your users to report suspicious emails to help keep your organization secure.

- Do we currently utilize the Graph API-capable Hybrid Phish Alert Button for analytics and what not?
	- **Do we feed it into Sentinel?**

#### SAML Single Sign-On (SSO)
[Set Up SAML Single Sign-on (SSO) for the Security Awareness Training Console](https://support.knowbe4.com/hc/en-us/articles/360041935913-Set-Up-SAML-Single-Sign-on-SSO-for-the-Security-Awareness-Training-Console)
- I don't like assuming, but in a mature environment, we'll be using Microsoft Entra ID for the IdP.
- Do users automatically get added to the KSAT console or does that take a form of change management and adding them to an Azure Group or Object within Entra?
- When ingesting new users, is everything automated for them to be added to the KSAT console?
	- **Is the phishing and training tailor-made per site or is it generic across the board for the moment?**
#### API's
- User Event API Use Cases
	- How often do we link in this kind of data for enriched training?
		- Data such as a user's birthday or out of office for social engineering?
		- Do we use physical access systems that we can pipe the security alerts from to the KnowBe4 KSAT console to assign tail gating training?
- Reporting API Overview
	- Do we have Platinum or Diamond licensing to utilize the API overview?
- Product API Overview
	- What integrations do we currently use?
		- Jira?
- KnowBe4 Graph API Overview
	- I'm assuming we're using the Graph API because it allows authentication on API calls to the KSAT console and PhishER platform.
	- Do we currently have a specific account(s) for API testing with KSAT & PhishER?
		- I feel that we could mitigate costs if we coded out reports and polled the Graph API.
	- **Do we have a connector in place with Sentinel to relate, parse, or allocate data from KSAT/PhishER?**
- Webhooks in Your KnowBe4 Console
	- Do we currently use any webhooks for custom or proprietary applications?
	- What type of authentication methods are in place? API Key only? HTTPS?
#### PasswordIQ
- Do we currently use PasswordIQ? 
- Do we have API reports pulling the data for these accounts and feeding them into Sentinel from the KSAT console or similar?

#### Second Chance
- Do we have Second Chance implemented?
- I feel like this would play havoc on EDR/XDR solutions....
