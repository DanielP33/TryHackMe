In this room, we cover:

    Security Operations Center (SOC)
    Threat Intelligence
    Digital Forensics and Incident Response (DFIR)
    Malware Analysis


  What is SOC ?

  A Security Operations Center (SOC) is a team of cyber security professionals that monitors the network and its systems to detect malicious cyber security events.
  (Blue Team)

  Some of the main areas of interest for a SOC are:

  
    Vulnerabilities: Whenever a system vulnerability (weakness) is discovered, it is essential to fix it by installing a proper update or patch.
    When a fix is not available, the necessary measures should be taken to prevent an attacker from exploiting it. Although remediating vulnerabilities
    is of vital interest to a SOC, it is not necessarily assigned to them.
    
    Policy violations: We can think of a security policy as a set of rules required for the protection of the network and systems. For example,
    it might be a policy violation if users start uploading confidential company data to an online storage service.
    
    Unauthorized activity: Consider the case where a user’s login name and password are stolen, and the attacker uses them to log into the network.
    A SOC needs to detect such an event and block it as soon as possible before further damage is done.
    
    Network intrusions: No matter how good your security is, there is always a chance for an intrusion. An intrusion can occur when a user clicks
    on a malicious link or when an attacker exploits a public server. Either way, when an intrusion occurs, we must detect it as soon as possible
    to prevent further damage.

Digital Forensics

    File System: Analyzing a digital forensics image (low-level copy) of a system’s storage reveals much information, such as installed programs,
    created files, partially overwritten files, and deleted files.
    
    System memory: If the attacker is running their malicious program in memory without saving it to the disk, taking a forensic image
    (low-level copy) of the system memory is the best way to analyze its contents and learn about the attack.
    
    System logs: Each client and server computer maintains different log files about what is happening. Log files provide plenty of information about
    what happened on a system. Some traces will be left even if the attacker tries to clear their traces.
    
    Network logs: Logs of the network packets that have traversed a network would help answer more questions about whether an attack is occurring and what it entails.

Incident Response

The four major phases of the incident response process are:

    Preparation: This requires a team trained and ready to handle incidents. Ideally, various measures are put in place to prevent incidents from happening in the first place.
    Detection and Analysis: The team has the necessary resources to detect any incident; moreover, it is essential to further analyze any detected incident to learn about its severity.
    Containment, Eradication, and Recovery: Once an incident is detected, it is crucial to stop it from affecting other systems, eliminate it, and recover the affected systems. For instance, when we notice that a system is infected with a computer virus, we would like to stop (contain) the virus from spreading to other systems, clean (eradicate) the virus, and ensure proper system recovery.
    Post-Incident Activity: After successful recovery, a report is produced, and the learned lesson is shared to prevent similar future incidents.
Malware Analysis

Viruses: Infect executable files and spread when these files are executed.

Worms: Replicate themselves across networks without any user intervention, often consuming bandwidth.

Trojans: Deceptively appear as legitimate software but perform malicious actions like stealing data or providing unauthorized access.

Spyware: Monitor and collect sensitive information from the user's device without their knowledge.

Adware: Display unwanted advertisements on the user's device, often bundled with legitimate software.

Ransomware: Encrypt files on a victim's device and demand payment (usually in cryptocurrency) for decryption.

Rootkits: Gain unauthorized access to the root or administrative level of a computer system, often used to hide other malware.

Keyloggers: Record keystrokes entered by the user, often used to capture sensitive information like passwords.

Botnets: Networks of infected devices (often called bots or zombies) controlled remotely to perform coordinated tasks, such as launching DDoS attacks.

Cryptojacking: Use a victim's computer to mine cryptocurrency without their consent or knowledge, consuming resources.

![imagem](https://github.com/DanielP33/THM/assets/145346859/6f835b2f-a20b-41bd-9f44-f40f1a5c8842)

On the third task thet get us in a simulated environment where we see a SIEM.

SIEM (Security Information and Event Management) collects and analyzes log data from various IT systems to detect and respond to security threats, providing alerts and incident management capabilities.

Examples of SIEM Solutions:
Splunk
Wazuh

In these logs we can see a successful attempt in login for the user John Doe and a successfull SSH authentication from an unknown ip address.

![imagem](https://github.com/DanielP33/THM/assets/145346859/86131fa1-5aef-4073-899c-2df95b74e1de)


we then scan the ip and it's a malicious ip according to the database.

![imagem](https://github.com/DanielP33/THM/assets/145346859/aea335fa-273e-4735-a697-1c058439d7b3)


then we chose which person has the most appropriate role in the company to respond to the incident
![imagem](https://github.com/DanielP33/THM/assets/145346859/7391c4e7-994e-499c-9d54-fbc94bc9a689)

We then block the ip on the firewall and we get the flag:
"THM{THREAT-BLOCKED} "

