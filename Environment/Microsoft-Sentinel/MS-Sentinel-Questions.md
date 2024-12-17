# Questions for Interview
- Do we have CSP (Cloud Service Provider) capabilities within our tenant or outside of it?
- Does contenthub have a Rapid7 connector or do we have to code our own through REST API for MS Sentinel?
- How often do we get called in to integrate a custom application into our sentinel subscription?
- How granular is our Manage Groups (workspaces?), Subscriptions, and resource groups within our MS Azure tenant? I ask because of the nature of alert fatigue etc.
	- Do we only handle corporate or are we the security team for the entirety of every outlier office?
		- How are the groups and subscriptions chopped up and is that why you're asking about terraform?
		- **create a terraform script to deploy managed groups, subscriptions, and resource groups. Create as granular as possible
- What level of change management is going on for the changes we need to implement? 
	- Ticket based?
	- Change Advisory Board?
	- or a mix of the two?
- Are we able to install plugins from content hub or is that a request?
## Data Connectors
- Do we have the requirements for each data connector bootstrapped into each instance standup or is being applied with something like Jenkins, Ansible, etc.?
- How was the migration to the AMA agent? I heard it was a little gnarly for some organizations
	- It's pretty easy for VMs in the cloud, but do we have non-headless sites still or are we all in the cloud? On-premise VMs need the Azure Arc agent to install the AMA agent for data connectors.
		- Is that when we're sent in?
- How often are we able to create custom data collection rules or does that take change management approval?
	- **Site the need for specific system events that pop off
	- Example: "Security!*[System[(EventID=4625) or (EventID=4624)]]"
	- Find a better example or event that I can reiterate
- Custom data connectors cost the organization less money.
	- **How much does data connectors cost?
- Do we have a hybrid approach depending on data connector and log type?
	- take a screenshot of "Microsoft Sentinel Deep Dive Sept. 2023 update" youtube video at 43:22 for the storage options
	- Are the security engineers responsible for the cost metrics or do we leave that to the architects?
- How often do we need to restore archive data to the analytics or basic pools?
- Do we hold onto data in analytics and then move it into data archive within 90 days or sooner?
- Doe any of our Business Admins create custom queries for tables or is that on us to show data?

## Analytics  Rule Wizard
- How fast can i get my hands on the custom analytics rules. I want to see what we have enabled within each tenant to make sure I'm not reinventing the wheel and can learn as much about our security posture.
- Contenthub workbooks will more than likely have most of the rules needed.
- Do we handle rule creation or is that another role?


## Sentinel Repositories
- Do we currently use Github with sentinel repositories?
	- Analytics rules,
	- Automation rules
	- Parsers, saved searches and functions
	- hunting and livestream queries
	- Workbooks
- Terraform AzureRM Provider
- Looks like we can connect a github repository or azure devops repository, load various types of scripts (powershell, jsons, terraforms, etc. depending on the configuration changes needed. check the screenshot) and configure the repos to push when we want them to, then have the configurations be pushed to various workspaces and azure tenants.
	- **I realllly want to bring this up in the interview**
	- Worries about granular access management?
	- Analytics shows when the pushes happen 
## Workspaces
## Automation (SOAR?)
- Do we have an API license for MDTI (Microsoft Detection Threat Intelligence)?
	- Understand the question better
- Microsoft Sentinel Triage Assistant (STAT) Tool for automations creation within MS Sentinel. Not officially a Microsoft tool, but created by Microsoft engineers.
	- Automating the research and investigation of an incident
- Do we utilize Azured OpenAI Service anywhere within our tenants?
