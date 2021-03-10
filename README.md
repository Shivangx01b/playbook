## Playbook: Phishing


### Investigate


1. **Scope the attack** Usually you will be notified that a potential phishing attack is underway, either by a user, customer, or partner.
    * Determine **total number of impacted users**
    * Understand **user actions** in response to the phishing email (_e.g._, did they download the attachment, visit the spoofed site, or give out any personal or business information such as credentials)
    * Find the potentially related activity. Check:
        * social media
        * any possibly suspicious emails
        * emails with links to external and unknown URLs
        * non-returnable or non-deliverable emails
        * any kind of notification of suspicious activity
2. **Analyze the message** using a safe device (i.e., **do not** open messages on a device with access to sensitive data or credentials as the message may contain malware), determine: 
    * who received the message
    * who was targeted by the message (may be different than "successful" recipients)
    * email address of the sender
    * subject line
    * message body
    * attachments (**do not open attachments** except according to established procedures)
    * links, domains, and hostnames (**do not follow links** except according to established procedures)
    * email metadata including message headers (see below)
        * sender information from the 'from' field and the X-authenticated user header
        * all client and mail server IP addresses
    * note "quirks" or suspicious features
3. **Analyze links and attachments** 
    * use passive collection such as nslookup and whois to find IP addresses and registration information
    * find related domains using OSINT (_e.g._, [reverse whois](https://www.whoxy.com/reverse-whois/)) on email addresses and other registration data
    * submit links, attachments, and/or hashes to [VirusTotal](https://www.virustotal.com/gui/)
    * submit links, attachments, and/or hashes to a malware sandbox such as [Cuckoo](https://cuckoosandbox.org/), [Hybrid Analysis](https://www.hybrid-analysis.com/), [Joe Sandbox](https://www.joesecurity.org/), or [VMray](https://www.vmray.com/).
4. Categorize the type of attack. 
5. **Determine the severity.** Consider:
    * whether public or personal safety is at risk
    * whether personal data (or other sensitive data) is at risk
    * any evidence of who is behind the attack
    * number of affected assets
    * preliminary business impact
    * whether services are affected
    * whether you are able to control/record critical systems


### Remediate

* **Plan remediation events** where these steps are launched together (or in coordinated fashion), with appropriate teams ready to respond to any disruption.
* **Consider the timing and tradeoffs** of remediation actions: your response has consequences.

#### Contain


* Contain affected accounts
    * change login credentials
    * reduce access to critical services, systems, or data until investigation is complete
    * reenforce multi-factor authentication (MFA)
* Block activity based on discovered indicators of compromise, _e.g._:
    * block malicious domains using DNS, firewalls, or proxies
    * block messages with similar senders, message bodies, subjects, links, attachments, _etc._, using email gateway or service.
* Implement forensic hold or retain forensic copies of messages
* Purge related messages from other user inboxes, or otherwise make inaccessible
* Contain broader compromise in accordance with general IR plan
* Consider mobile device containment measures such as wiping via mobile device management (MDM).  Balance against investigative/forensic impact.
* Increase detection "alert level," with enhanced monitoring, particularly from related accounts, domains, or IP addresses.
* Consider outside security assistance to support investigation and remediation
* Confirm relevant software upgrades and anti-malware updates on assets.



### Communicate


1. Escalate incident and communicate with leadership per procedure
2. Document incident per procedure .
3. Communicate with internal and external legal counsel per procedure, including discussions of compliance, risk exposure, liability, law enforcement contact, _etc._
4. Communicate with users (internal)
    1. Communicate incident response updates per procedure
    1. Communicate impact of incident **and** incident response actions (e.g., containment: "why is the file share down?")
    1. Communicate requirements: "what should users do and not do?"  
5. Communicate with customers
    1. Focus particularly on those whose data was affected
    1. Generate required notifications based on applicable regulations (particularly those that may consider phishing a data breach or otherwise requires notifications) 
6. Contact insurance provider(s)
    1. Discuss what resources they can make available, what tools and vendors they support and will pay for, _etc._
    1. Comply with reporting and claims requirements to protect eligibility
7. Consider notifying and involving law enforcement.
8. Communicate with security and IT vendors 
   

### Recover

1. Launch business continuity/disaster recovery plan(s) if compromise involved business outages: _e.g._, consider migration to alternate operating locations, fail-over sites, backup systems.
2. Reinforce training programs regarding suspected phishing attacks. Key suspicious indicators may include: 
    * misspellings in the message or subject
    * phony-seeming sender names, including mismatches between display name and email address
    * personal email addresses for official business (e.g., gmail or yahoo emails from business colleagues)
    * subject lines marked "[EXTERNAL]" on emails that look internal
    * [malicious or suspicious links](https://www.pcworld.com/article/248963/how-to-tell-if-a-link-is-safe-without-clicking-on-it.html)
    * receiving an email or attachment they were not expecting but from someone they know (contact sender before opening it)
    * reporting suspicious activity to IT or security
3. Ensure that IT and security staff is up to date on recent phishing techniques.
4. Determine if any controls have failed when falling victim to an attack and rectify them. Here is a [good source](https://www.proofpoint.com/us/security-awareness/post/14-things-do-after-phishing-attack) to consider following a phishing attack.



