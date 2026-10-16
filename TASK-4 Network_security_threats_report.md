# Common Network Security Threats: DoS/DDoS, MITM, IP Spoofing and DNS Poisoning

**Author:** Aisha Aziz
**Type:** Security Research Report
**Scope:** How each attack works, real-world impact and specific mitigation strategies

\---

## Table of Contents

1. [Introduction](#1-introduction)
2. [DoS and DDoS Attacks](#2-dos-and-ddos-attacks)
3. [Man-in-the-Middle (MITM) Attacks](#3-man-in-the-middle-mitm-attacks)
4. [IP Spoofing](#4-ip-spoofing)
5. [DNS Poisoning / Spoofing](#5-dns-poisoning--spoofing)
6. [Comparison Table](#6-comparison-table)
7. [Conclusion: Key Takeaways for a Network Administrator](#7-conclusion-key-takeaways-for-a-network-administrator)
8. [References](#8-references)

\---

## 1\. Introduction

Modern organizations depend on networks for almost everything: email, cloud services, payments, remote work and customer-facing applications. That dependence makes the network a prime target, because an attacker who can disrupt, intercept or redirect traffic can cause outages, steal credentials and data, or impersonate trusted services without ever touching an endpoint directly. Many of the protocols that underpin the internet, such as IP, DNS and ARP, were designed decades ago for a smaller and more trusting environment and do not authenticate the data they carry by default. Attackers exploit exactly this gap, using tools that are cheap, widely available and often automated. This report examines four common network threats (DoS/DDoS, Man-in-the-Middle, IP spoofing and DNS poisoning), explains how each works, reviews a documented real-world incident, and gives specific mitigation strategies that a network administrator can apply.



## 2\. DoS and DDoS Attacks

A Denial-of-Service (DoS) attack is a cyberattack where a single system floods a target server, website, or network with excessive requests, making it crash or become unavailable to real users

### 2.1 How it works

A **Denial-of-Service (DoS)** attack tries to make a system, service or network unavailable to legitimate users by exhausting its resources (bandwidth, CPU, memory or connection tables). In a **Distributed DoS (DDoS)** attack, the traffic comes from many sources at once, usually a **botnet** of compromised computers, servers and IoT devices, which makes it far harder to block.

Common categories:

|Category|Target|Examples|
|-|-|-|
|**Volumetric**|Bandwidth|UDP floods, DNS/NTP/Memcached amplification and reflection|
|**Protocol**|Connection-handling resources of servers, firewalls and load balancers|SYN flood, Ping of Death, fragmented-packet attacks|
|**Application layer**|Web server or application logic|HTTP GET/POST floods, Slow loris|
||||

### 

### 2.2 Real-world example:

##### &#x20;Boston Children’s Hospital (2014)

* &#x20;**DDoS Attack Strike #1 - Low-Rate Attacks**
* &#x20;Starting in early April 2014, the attackers made good on their threats, targeting the hospital's  external website with a DDoS attack.
* **DDoS Attack #2 - Attacks Ramp Up**
* Over the course of a week, the attacks increased to the point that they slowed legitimate inbound and outbound traffic. This second string of attacks—DDoS attacks, scans, and intrusion attempts—included TCP fragmented floods, out-of-state floods, and DNS reflection floods (including UDP fragment floods). DDoS attack mitigation efforts were able to stop DDoS attacks from reaching the targeted servers.
* **DDoS Attack Strike #3 - Attacks Peak**
* The third strike peaked at nearly four times that of the second strike, reaching 28 Gbps. This time, the attackers made multiple attempts to penetrate the hospital's network through direct DDoS attacks on exposed ports and services. The attackers also used "spear phishing" emails to try to lure recipients into clicking embedded links or opening attachments, thereby granting access to part of the network behind the hospital's firewall.



###### **Lessons Learned**

* The DDoS attacks against Boston Children's Hospital are significant not because of their technical sophistication but because they demonstrate that any organization, including healthcare entities, can be a target for cyber-attacks.





##### 2.3 Impacts of this attack

* Inability to route prescriptions electronically to pharmacies
* Email downtime for departments where email supports critical processes
* Inability to access remotely hosted electronic health records
* Service outages and loss of revenue
* Reputation and customer-trust damage
* Cost of emergency mitigation and incident response
* Use as a **smokescreen** while attackers carry out intrusion or data theft elsewhere
* Collateral damage to third parties that depend on the target (as in the Dyn incident)





### 2.4 Three specific mitigation strategies

* The Boston Children's Hospital team invoked Radware's Emergency Response Team to perform DDoS attack mitigation, and used Radware's scrubbing center to handle the massive rate of DDoS attacks. Because Boston Children's Hospital shares an ISP with other hospitals, seven other health care institutions also faced potential impacts to their network and operations.





* As soon as it became aware of the initial threat, Boston Children's Hospital activated its multidisciplinary incident response team. The team had to quickly assess what services would be compromised or lost if the hospital were to lose Internet connectivity. (The hospital had not conducted such an assessment prior to the DDoS attacks.)



* Healthcare entities, like all organizations, must ensure continual vigilance regarding information security. Organizations want to know how to prevent DDoS attacks, but foolproof anti-DDoS protection isn't possible. Instead, organizations need to devote resources to developing a strategic DDoS mitigation plan, and that plan must be communicated well and updated constantly as threats and risks evolve.





## 3\. Man-in-the-Middle (MITM) Attacks

A man-in-the-middle attack is when someone secretly slips into the middle of a conversation between two parties, say you and your bank’s website. Each side thinks it is talking straight to the other, but every message now passes through the attacker first. That position lets them read what is being sent and change it before it reaches the other end. 

### 3.1 How it works

In a **Man-in-the-Middle** attack (called *Adversary-in-the-Middle* in MITRE ATT\&CK, technique T1557), the attacker secretly positions themselves between two communicating parties so they can **eavesdrop on, alter or inject** traffic while both sides believe they are talking directly to each other.

Common techniques:

* **ARP spoofing/poisoning:** sending forged ARP replies so devices on a LAN send their traffic to the attacker's machine.
* **Rogue Wi-Fi access points / "evil twin":** a fake hotspot with a legitimate-looking name.
* **DHCP spoofing:** a rogue DHCP server hands out a malicious gateway or DNS server.
* **SSL stripping / fraudulent certificates:** downgrading HTTPS to HTTP or presenting a forged certificate.
* **DNS spoofing and session hijacking** as supporting techniques.



### 3.2 Real-world example:

##### Equifax Data Breach Context (2017) 

The 2017 Equifax data breach was a massive cyberattack that exposed the sensitive personal data of approximately 147 million consumers (primarily in the U.S., alongside individuals in the UK and Canada) due to severe security and patching failures.



###### **What Happened**

• **The** **Vulnerability:** Attackers exploited an unpatched vulnerability (CVE-2017-5638) in Apache Struts, a web application framework used by Equifax's online dispute portal.

• **Timeline**: The intrusion began around March 10, 2017. Equifax discovered the breach on July 29, 2017, but waited over five weeks to publicly disclose it on September 7, 2017.

• **System Failures**: Equifax failed to apply a critical security patch released months earlier.

&#x20;An expired SSL inspection certificate (expired for 10 months) blinded network monitoring tools from detecting malicious traffic for 76 to 78 days. Poor internal network segmentation allowed hackers to move freely across databases once inside.

### 

### 3.3 Impacts

• **Exposed Data**: Compromised records included full names, Social Security Numbers (SSNs), dates of birth, home addresses, driver's license numbers, and hundreds of thousands of credit card numbers.

• **Organizational Fallout**: The CEO, CIO, and CSO resigned. Executive stock sales prior to public disclosure drew insider trading scrutiny.

• **Financial \& Legal Penalties**: Equifax agreed to a global settlement of up to $700 million with the FTC, CFPB, and state attorneys general, plus hundreds of millions more in remediation and security upgrades.



### 3.4 Three specific mitigation strategies

* **Credit Freezes**: Placing a credit freeze with major credit bureaus blocks lenders from opening new accounts in your name.

• **Credit Monitoring**: Affected consumers were offered credit monitoring and identity theft protection services.

• **Corporate Remediation**: Equifax overhauled its infrastructure by implementing multi-factor authentication (MFA), automated patch management, stricter network segmentation, and data encryption.

• **Checking Eligibility**: Consumers can review settlement details or check remediation options via official resources like the Security.org Equifax Guide.

## 

## 4\. IP Spoofing

IP spoofing is a cyberattack technique where a sender alters the source Internet Protocol (IP) address in packet headers to hide their identity, impersonate another computer system, or both

### 4.1 How it works

**IP spoofing** is the creation of IP packets with a **forged source address**. Because IP does not verify the sender, an attacker can make packets appear to come from a trusted host or from a victim. It is used to:

* Hide the attacker's identity.
* **Reflect and amplify** traffic onto a victim (DDoS).
* Impersonate a trusted host to bypass IP-based access controls or firewall rules.
* Hijack or inject into TCP sessions by predicting sequence numbers (blind spoofing).

Spoofing is mainly a **technique** that enables other attacks, rather than an end goal by itself.

### 4.2 Real-world examples

###### **GitHub memcached attack (2018):** 

**What Happened**

On February 28, 2018, GitHub, the world’s largest code-sharing platform, was hit by the largest distributed denial-of-service (DDoS) attack ever recorded at that time, peaking at 1.35 terabits per second (Tbps). This attack leveraged a technique known as memcached amplification and set a new benchmark for how massive DDoS attacks could become.

Attackers sent small requests to thousands of exposed memcached servers with the **source IP forged to GitHub's address**. The servers replied with responses up to tens of thousands of times larger, producing the 1.35 Tbps flood described in Section 2. Spoofing was the essential ingredient.



Memcached is a caching system meant to accelerate applications, but in this case, it was reachable over UDP (port 11211) with no authentication.



Attackers sent small spoofed requests to vulnerable memcached servers.

Servers responded with huge amplified replies (up to 50,000x bigger).

Replies were directed at GitHub → overwhelming its systems.

2.Scale of the Attack



Traffic peaked at 1.35 Tbps and 126.9 million packets per second (Mpps).

This dwarfed previous large DDoS attacks, such as the Mirai IoT botnet (2016, \~620 Gbps).

Press enter or click to view image in full size



### 4.3 Impact 

* **Service Outage**: GitHub went offline for around 8 minutes, which may seem short, but GitHub is a global platform used by millions of developers and companies.



* **Workflow Disruptions**: Developers worldwide experienced issues with code pushes, CI/CD pipelines, and repository pulls, especially those with automated systems relying on GitHub’s uptime.



* Trust Concerns: Even with rapid recovery, the attack reminded businesses that even the biggest platforms were not immune to cyber disruptions.



### 4.4 Three specific mitigation strategies



• **Real-Time Detection**: The attack began at 17:21 UTC and was identified within minutes.

• **BGP Route Withdrawal:** At 17:26 UTC, GitHub (AS 36459) withdrew its BGP routes from primary upstream providers (including Telia, Level 3, and NTT).

• **Traffic Rerouting to Scrubbing Centers**: Traffic was redirected to Akamai Prolexic (AS 32787). Scrubbing centers filtered out spoofed malicious UDP traffic while allowing legitimate requests to pass through.

• **Rapid Recovery**: Full traffic flow and service stability were restored in under 10 to 15 minutes, with lingering traffic routed through Prolexic for several post-attack hours.



## 5\. DNS Poisoning / Spoofing

### 5.1 How it works

The **Domain Name System (DNS)** translates names such as `example.com` into IP addresses. In **DNS cache poisoning (DNS spoofing)**, an attacker inserts **false records** into a DNS resolver's cache, so users who query that resolver are sent to an attacker-controlled IP address, typically a phishing or malware site, even though they typed the correct URL.

Related methods include compromising a DNS server or registrar account, and hijacking DNS traffic through routing manipulation.



**Basic steps of classic cache poisoning**:

1. The attacker triggers the resolver to look up a name it does not have cached.
2. The attacker floods it with forged responses, guessing the transaction ID (and, historically, relying on a predictable source port).
3. If a forged response arrives before the genuine one and matches, the resolver **caches the fake answer** until the record's TTL expires.
4. Every user of that resolver is redirected.



### 5.2 Real-world examples

###### **The Kaminsky vulnerability (2008):** 

&#x20;Security researcher Dan Kaminsky showed a far more efficient way to poison DNS caches (CVE-2008-1447), allowing attackers to take over entire domains within seconds. A coordinated, industry-wide patch was released in July 2008, introducing source port randomisation.

* **MyEtherWallet DNS/BGP hijack (April 2018):** Attackers hijacked BGP routes for Amazon's Route 53 DNS address space and ran rogue DNS servers that answered queries for `myetherwallet.com` with the address of a phishing site. Users who ignored the certificate warning entered their credentials, and roughly **USD 150,000** worth of cryptocurrency was reportedly stolen.
* **DNS infrastructure hijacking campaign (2018–2019):** CISA issued Alert AA19-024A warning that attackers were modifying DNS records of government and commercial organizations to redirect and intercept traffic.



### 5.3 Impacts



* Redirection to phishing or malware sites with a legitimate-looking URL
* Credential and financial theft
* Interception of email and web traffic (can combine with MITM)
* Wide reach: one poisoned resolver affects all its users
* Hard to notice, because the address bar still shows the correct name



### 5.4 Three specific mitigation strategies



1. **Deploy DNSSEC.** DNSSEC digitally signs DNS records so resolvers can verify their authenticity. Sign your zones and enable DNSSEC validation on your recursive resolvers (NIST SP 800-81-2 provides deployment guidance).
2. **Harden and patch DNS servers.** Use source port and transaction ID randomisation, restrict recursion to internal clients only, limit zone transfers, keep DNS software patched, and use encrypted DNS (DoT/DoH) between clients and resolvers.
3. **Protect DNS administration and monitor changes.** Enable registrar lock and MFA on registrar and DNS-provider accounts, use strong credentials, and monitor DNS records and resolver logs for unexpected changes. Combine with TLS and certificate warnings to limit the damage if redirection happens.





## 6\. Comparison Table

|Threat|Attack vector|Who is at risk|Difficulty to execute|Ease of mitigation|
|-|-|-|-|-|
|**DoS / DDoS**|Flooding bandwidth, protocols or applications, often via botnets and reflection|Public-facing websites, online services, DNS and ISP providers, e-commerce, gaming|**Low** (DDoS-for-hire services are cheap), though very large attacks need big botnets|**Moderate**: needs paid scrubbing/CDN capacity and upstream cooperation|
|**MITM**|Interception on the LAN or Wi-Fi (ARP/DHCP spoofing, rogue AP), forged certificates, SSL stripping|Users on public or shared Wi-Fi, remote workers, banking and e-commerce users|**Medium**: needs a position on the network path or a rogue certificate|**Moderate to easy**: TLS/HSTS, VPN and switch hardening are effective but need consistent configuration|
|**IP spoofing**|Forged source IP in packets, sequence-number guessing, reflection|Servers relying on IP-based trust, DDoS victims, networks lacking ingress filtering|**Low to medium**: simple to send packets, hard to complete two-way sessions|**Moderate**: needs ingress/egress filtering by many networks, including your ISP|
|**DNS poisoning**|Forged responses to resolvers, compromised DNS servers or registrars, route hijacking|Any user of an affected resolver, domain owners, banks and crypto services|**Medium to high** on patched, modern resolvers|**Moderate**: DNSSEC and hardening work but DNSSEC adoption and key management add effort|





## 7\. Conclusion: Key Takeaways for a Network Administrator

1. **Assume the network is hostile and never trust addresses or names alone.** Spoofing, MITM and DNS poisoning all exploit implicit trust. Use encryption and cryptographic authentication (TLS, IPsec, DNSSEC, 802.1X) rather than IP addresses or unauthenticated lookups.
2. **Layer your defences and harden the basics.** Filter spoofed traffic at the edge, secure switches against ARP/DHCP attacks, lock down DNS servers and registrar accounts, and patch systems promptly. No single control stops all four threats.
3. **Plan for attacks before they happen.** Arrange DDoS protection and ISP support in advance, monitor traffic, DNS records and certificates for anomalies, and keep a tested incident response plan so recovery is measured in minutes, not days.

\---

## 8\. References



1. https://www.google.com/search?q=The+GitHub+DDoS+Attack+%282018%29+matigation+strategies\&sca\_esv=
2. CERT/CC. *Vulnerability Note VU#800113: Multiple DNS implementations vulnerable to cache poisoning* (2008). https://www.kb.cert.org/vuls/id/800113
3. Kaminsky, D. *Black Ops 2008: It's the End of the Cache As We Know It*. Black Hat USA 2008.
4. https://medium.com/@mganeshram2005/%EF%B8%8F-case-study-github-ddos-attack-2018-3e9c9cd4be80
5. https://www.imperva.com/learn/application-security/man-in-the-middle-attack-mitm/
6. https://www.cloudflare.com/learning/ddos/famous-ddos-attacks/
7. https://www.quillaudits.com/blog/web3-security/dns-attack

