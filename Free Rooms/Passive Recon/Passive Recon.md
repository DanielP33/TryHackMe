[Free Rooms](https://github.com/winterrdog/tryhackme-free-rooms)


[Passive Recon](https://tryhackme.com/r/room/passiverecon)
## Task 1 : Introduction
What is WHOIS?

WHOIS is a protocol used to query databases that store information about the registration of domain names on the internet. When you perform a WHOIS lookup, you retrieve details about a domain name, such as:

    The registrant's name (who owns the domain)
    Contact information (email, phone number)
    Domain registration and expiration dates
    Name servers used by the domain

What is DIG?

DIG (Domain Information Groper) is a command-line tool used for querying Domain Name System (DNS) servers. It’s a powerful tool used to:

    Retrieve DNS records for a domain (like A, MX, TXT, CNAME records)
    Troubleshoot DNS problems
    Test DNS configurations

What is NSLOOKUP?

NSLOOKUP (Name Server Lookup) is another command-line tool used for querying DNS servers to obtain domain name or IP address mapping information. It’s used to:

    Look up the IP address associated with a domain name (or vice versa)
    Obtain specific DNS records (like A, MX, NS records)
    Perform reverse DNS lookups
## Task 2 : Passive Versus Active Recon

Reconnaissance (recon) can be defined as a preliminary survey to gather information about a target. It is the first step in The Unified Kill Chain to gain an initial foothold on a system. We divide reconnaissance into:

    Passive Reconnaissance
    Active Reconnaissance

In passive reconnaissance, you rely on publicly available knowledge. It is the knowledge that you can access from publicly available resources without directly engaging with the target. Think of it like you are looking at target territory from afar without stepping foot on that territory.

Passive reconnaissance activities include many activities, for instance:

    Looking up DNS records of a domain from a public DNS server.
    Checking job ads related to the target website.
    Reading news articles about the target company.

Active reconnaissance, on the other hand, cannot be achieved so discreetly. It requires direct engagement with the target. Think of it like you check the locks on the doors and windows, among other potential entry points.

Examples of active reconnaissance activities include:

    Connecting to one of the company servers such as HTTP, FTP, and SMTP.
    Calling the company in an attempt to get information (social engineering).
    Entering company premises pretending to be a repairman.

"You visit the Facebook page of the target company, hoping to get some of their employee names. What kind of reconnaissance activity is this? (A for active, P for passive)"
**ANSWER:** ``P``

"You ping the IP address of the company webserver to check if ICMP traffic is blocked. What kind of reconnaissance activity is this? (A for active, P for passive)"
**ANSWER:** ``A``

"You happen to meet the IT administrator of the target company at a party. You try to use social engineering to get more information about their systems and network infrastructure. What kind of reconnaissance activity is this? (A for active, P for passive)"
**ANSWER:** ``A``
## Task 3 : Whois

"When was TryHackMe.com registered?"
**ANSWER:**
``20180705``

(This one was stupid tbh..)

"What is the registrar of TryHackMe.com?"
**ANSWER:** ``Namecheap.com``

"Which company is TryHackMe.com using for name servers?"

**ANSWER:** ``Cloudflare.com``

## Task 4 : nslookup and dig

![image](https://github.com/user-attachments/assets/f4ad79eb-aec2-4ed0-b5d5-e4423021ba22)

``nslookup -type=A tryhackme.com 1.1.1.1``


"Check the TXT records of thmlabs.com. What is the flag there?"
``nslookup -type=txt thmlabs.com``

**ANSWER:** ``THM{a5b83929888ed36acb0272971e438d78}``

## Task 5 : Dns Dumpster

DNS lookup tools, such as nslookup and dig, cannot find subdomains on their own. 

One can use an online service that offers detailed answers to DNS queries, such as DNSDumpster. If we search DNSDumpster for tryhackme.com, we will discover the subdomain blog.tryhackme.com, which a typical DNS query cannot provide. In addition, DNSDumpster will return the collected DNS information in easy-to-read tables and a graph. DNSDumpster will also provide any collected information about listening servers.

"Lookup tryhackme.com on DNSDumpster. What is one interesting subdomain that you would discover in addition to www and blog?"
**ANSWER:** ``Remote``

## Task 6 : Shodan.io

When you are tasked to run a penetration test against specific targets, as part of the passive reconnaissance phase, a service like Shodan.io can be helpful to learn various pieces of information about the client’s network, without actively connecting to it. Furthermore, on the defensive side, you can use different services from Shodan.io to learn about connected and exposed devices belonging to your organization.

Shodan.io tries to connect to every device reachable online to build a search engine of connected “things” in contrast with a search engine for web pages. Once it gets a response, it collects all the information related to the service and saves it in the database to make it searchable. 

"According to Shodan.io, what is the 2nd country in the world in terms of the number of publicly accessible Apache servers?"

**ANSWER:** Germany

Based on Shodan.io, what is the 3rd most common port used for Apache?

**ANSWER:** 8080

Based on Shodan.io, what is the 3rd most common port used for nginx?

**ANSWER:** 

