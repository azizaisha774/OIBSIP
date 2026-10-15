# Social Engineering Attacks: Phishing, Pretexting and Baiting

**Author:** Aisha Aziz
**Type:** Security Research Report
**Scope:** Attack types, real-world case studies, prevention and organizational recommendation.



## Table of Contents

1. [Introduction](#1-introduction)
2. [Phishing](#2-phishing)
3. [Pretexting](#3-pretexting)
4. [Baiting](#4-baiting)
5. [Quid Pro Quo (Bonus)](#5-quid-pro-quo-bonus)
6. [Comparison Table](#6-comparison-table)
7. [Organizational Recommendations](#7-organisational-recommendations)
8. [Conclusion](#8-conclusion)
9. [References](#9-references)



## 1\. Introduction

### 1.1 What is social engineering?



Social engineering is the use of **psychological manipulation** to trick people into revealing confidential information, granting access, or performing actions that compromise security. Instead of breaking through a firewall or exploiting a software bug, the attacker targets the *human* in the system such as trust, fear, curiosity, or urgency. CISA describes these attacks as relying on human interaction and on persuading people to break normal security practices.



### 1.2 Why is it so effective?



&#x20;• **Bypasses Technical Defenses**: Firewalls, antivirus software, and multi-factor authentication (MFA) protect code and networks, but they cannot stop a user who willingly hands over their credentials or approves a fake prompt.



• **Exploits Human Emotions:** Attackers manipulate natural instincts—such as fear of legal trouble or job loss, urgency to fix a broken system, trust in authority figures or brands, and curiosity or greed.



• **Easier than Hack Engineering**: Compromising a human brain through persuasion or deception is often much cheaper and simpler for an attacker than spending weeks searching for zero-day code exploits in hardened software.



• **Amplified by Artificial Intelligence (AI)**: Modern threat actors use AI for voice cloning, deepfake video, and highly personalized spear-phishing messages that mimic real colleagues or executives with extreme precision.



• **High Success and Impact**: Industry reports (such as the Verizon DBIR) show that human-targeted social engineering accounts for roughly 60% of data breaches, making it a primary entry point for major cyberattacks and ransomware.

### 

### 1.3 Key statistics



|Statistic|Source|
|-|-|
|68% of breaches in the 2024 dataset involved a non-malicious human element (error or being tricked by social engineering)|Verizon DBIR 2024|
|Median time for a user to click a malicious link in a phishing email was about 21 seconds, with about 28 more seconds to enter data|Verizon DBIR 2024|
|Phishing/spoofing was the most reported cybercrime type in 2023 with 298,878 complaints|FBI IC3 Report 2023|
|Business Email Compromise (BEC) caused about USD 2.9 billion in reported losses in 2023|FBI IC3 Report 2023|

## 

## 2\. Phishing

### 2.1 Definition

Phishing is a type of cybercrime and social engineering scam where attackers impersonate trusted, legitimate entities—such as banks, government agencies, or tech companies—to trick people into revealing sensitive data like passwords, credit card numbers, and login credentials, or to install malware



### 2.2 Types of phishing

|Type|Channel|Description|
|-|-|-|
|**Mass phishing**|Email|Generic message sent to thousands of people, e.g. a fake "Your account is suspended" notice.|
|**Spear phishing**|Email|Targeted at a specific person or small group, using researched details (name, job role, colleagues, projects) to look authentic.|
|**Whaling**|Email|Spear phishing aimed at senior executives (the "big fish"), such as a fake request to the CFO or a fake legal notice to the CEO.|
|**Vishing** |Phone call|Attacker calls while posing as a bank, IT helpdesk or government agency and pressures the victim into sharing data or approving actions.|
|**Smishing** |Text message|Short text with a malicious link, e.g. a fake delivery or bank alert.|
|**Business Email Compromise (BEC)**|Email|Impersonating an executive or vendor to request payments or change bank details.|

### 

### 2.3 How phishing works

1. **Reconnaissance:** the attacker gathers information (company website, LinkedIn, leaked data) to choose targets and craft a believable message.
2. **Crafting the lure:** a message is built with a trusted sender identity, a logo, and an emotional trigger such as urgency or fear.
3. **Delivery:** the message is sent by email, SMS, phone or messaging apps.
4. **Hook:** the victim clicks a link to a fake login page, opens a malicious attachment, or replies with information.
5. **Exploitation:** credentials are harvested or malware is installed.
6. **Action on objectives:** the attacker moves through the network, steals data, commits fraud or deploys ransomware.

&#x20;



### 2.4 Case study: 

&#x20;

Elara Caring, a home-based care provideR based in Dallas, Texas.

&#x20;

**WHAT HAPPENED:**

Elara Caring was the victim of a phishing attack . On December 9, 2020, a phishing email was sent to employees which enabled a hacker to gain access to several employee accounts. Although Elara Caring detected the unauthorized access the same day, it wasn't able to contain the situation until December 16. Protected health information ( PHI ) may have been leaked during this data breach. As many as 100,400 patients had sensitive data exposed, including information like:

Name

Date of birth

Address

Phone number

Financial or bank account information

Social Security number

Insurance information

Driver’s license number

&#x20;

Elara Caring claims that there's no evidence that PHI was accessed or misused. Its investigation also concluded that malware wasn't released into its network.

&#x20;

**RESPONSE TO ATTACK**

Elara Caring sent notification letters of the data breach to all affected patients and is offering to pay for a two-year membership of Experian services to monitor for potential fraud.  Elara Caring also made many internal changes. 



**CHANGES THEY MADE**:

Conducting an enterprise-wide password change

Implementing multi-factor authentication

Training employees on cybersecurity and how to spot scams 

&#x20;

### 2.6 Four prevention recommendations

&#x20;

1. **Enable multi-factor authentication (MFA):**
 preferably phishing-resistant (FIDO2 security keys or passkeys) so stolen passwords alone are   not enough.
2. **Deploy email security controls:**
Email security controls like spam/phishing filtering, SPF, DKIM and DMARC, attachment sandboxing and link rewriting.
3. **Train and test users regularly:**
  Train with phishing simulations, and teach a simple habit: *stop, inspect the sender and link, and verify through a separate channel.*
4. **Make Use of Endpoint Monitoring and Protection:**
Cloud services and personally-owned devices introduce an increasing number of new endpoints beyond     the traditional perimeter. Threat actors can exploit these insecure endpoints to breach into the connected network. Endpoint monitoring and protection extend visibility beyond the traditional perimeter to detect and respond to endpoint threats and quickly remediate compromised devices.



## 3\. Pretexting

### 3.1 Definition



Pretexting is a social engineering technique in which the attacker creates a **fabricated scenario (the pretext)** and often a false identity to gain the victim's trust and obtain information or access. Unlike many phishing attacks, pretexting depends on a convincing *story* and often on a real conversation.

A hacker impersonates someone the victim knows or trusts—such as a coworker, delivery person, or government organization—to access information or sensitive systems. In many cases, pretexting may involve interacting with people either in person or via a fraudulent email address as they launch the first phase of a future attempt to infiltrate a network or steal data using email. 



In a pretexting attack, the attacker convincingly presents a story using legitimate-looking message formats and images (such as government logos), tone, and wording. Note that a pretexting attack can be done online, in person, or over the phone. The goal is to put the attacker in a better position to launch a successful future attack. 



### 3.2 How an attacker builds a false scenario

1. **Choose the goal:** for example, obtaining an employee's login, a customer's account details, or physical access to a building.
2. **Research:** collect names, job titles, reporting lines, internal jargon and vendors from LinkedIn, company websites, social media and data leaks (OSINT).
3. **Pick a believable persona:** IT support, auditor, new employee, vendor, bank representative, police officer or HR.
4. **Build credibility:** quote real names and ticket numbers, use correct terminology and spoof the caller ID or sender address.
5. **Create pressure:** deadlines, "your account will be locked", or invoking a senior manager.
6. **Make a small, reasonable-sounding request:** often starting with harmless questions and escalating step by step.
7. **Exit cleanly:** thank the victim so that nothing seems wrong.



### 3.3 Case study: 

**WHAT HAPPENED:**

On July 15, 2020, between 20:00 and 22:00 UTC, 130 high-profile Twitter accounts were compromised by outside parties to promote a bitcoin scam. Hackers used social engineering against Twitter employees to gain access to administrative tools, allowing them to post the tweets directly. The scam tweets asked individuals to send bitcoin currency to a specific cryptocurrency wallet, with the promise that money sent would be doubled and returned – within minutes, one account received over 320 deposits with a value of over US$110,000 before the scam messages were removed by Twitter.



CrowdStrike co-founder Dmitri Alperovitch described the incident as "the worst hack of a major social media platform yet", and security researchers highlighted the risks of social media manipulation during large events such as the lead-up into the 2020 United States presidential election.

**RESPONSE TO THE ATTACK:** On July 31, 2020, the U.S. Department of Justice announced charges against three individuals in connection with the incident. 

**CHANGES THEY MADE**:Severely Restricted Access Permission,Increased System Logging \& Monitoring,Mandatory Physical Security Keys,Zero-Trust Framework Adjustments,

Human \& Behavioral Security Adjustments like Targeted Spear-Phishing Training



### 3.4 Three preventive measures:



1. &#x20;**Examine the pretext carefully**
Pretexting's major flaw is that users frequently use a well-known brand name. This means that a potential victim can get in touch with the company the criminal claims to work for and inquire about the attacker’s credibility. Employees should always make an effort to confirm the pretext as part of your organization’s standard operating procedures.

2. **Limit what is public and what staff can disclose:** reduce oversharing on social media and company sites, and train staff on what information may *never* be given over the phone or email.

3. **Educate your staff**: Employees are the first line of defense against attacks. Teach them about security best practices, including how to prevent pretexting attacks. Staff members should be comfortable double-checking credentials, especially if they have a reason to doubt them.



## 4\. Baiting

### 4.1 Definition

Baiting lures victims with the **promise of something attractive** (free software, a movie, a prize, or simply a found device) to get them to infect their own system or surrender information. It exploits **curiosity and greed**.For example, an ad might invite website visitors to click on an offer for a free movie download, but responding to the offer requires the victim to provide their email information, setting the stage for follow-up identity theft attacks.



### Types of baiting

### 4.2 Physical baiting

* **Infected USB drives** are left in car parks, lobbies, toilets or mailed to targets, often labelled with tempting text such as "Salary 2026" or "Confidential".
* When plugged in, the device may run malware automatically, or pretend to be a keyboard (a "BadUSB" device) that types malicious commands.
* Other physical lures include CDs/DVDs and fake "free gift" packages.

### 4.3 Digital baiting

Tricking the victim into providing sensitive information, such as email addresses, login credentials, or financial data

* **Fake downloads:** cracked software, game cheats, pirated films and fake "free" tools bundled with malware.
* **Malicious ads and fake download buttons** on file-sharing and streaming sites.
* **Fake prizes and surveys** that ask for personal details.
* **Poisoned search results** that lead to trojanised installers of popular software.





### 4.4 Case study: Operation Buckshot Yankee (2008)

**What happened:** In 2008, malware spread through US military networks, including classified systems, after an **infected flash drive** was inserted into a laptop at a US military base in the Middle East. The malware (known as *agent.btz*) installed itself, searched for other systems and opened a path for data to leave the network.



**Response and impact:**

* The Pentagon launched a major clean-up effort called **Operation Buckshot Yankee**.
* The Department of Defense temporarily banned removable media such as USB drives.
* William Lynn, then US Deputy Secretary of Defense, described it as a turning point, and the incident is often cited as one reason US Cyber Command was created.



**Supporting research:** A 2016 study by researchers at the University of Illinois (Tischer et al., IEEE Symposium on Security and Privacy) dropped nearly 300 USB drives around a university campus. About 98% were picked up and roughly 45% were plugged in and had files opened, showing how reliably the curiosity lure works.

**Lessons:** Technical networks can be isolated, but one curious person plugging in a drive can bridge the gap. Device control policies and user awareness are both necessary.



### 4.5 Three prevention measures

1. **Control removable media:** disable USB autorun, block or restrict USB storage through endpoint policy, and allow only approved, encrypted company devices.
2. **Use endpoint protection and safe download practices:** keep EDR/antivirus updated, download software only from official sources, and use application allow-listing where possible.
3. **Train staff never to plug in found devices:** hand them to IT or security instead, and provide an easy way to report them.



## 5\. Quid Pro Quo (Bonus)

### 5.1 Explanation

*Quid pro quo* means "something for something". The attacker **offers a service or benefit in exchange for information or access**. The victim feels they are receiving help or a reward, so they cooperate.



**Typical scenarios:**

* A caller pretends to be **IT support** and offers to "fix a problem" if the employee disables antivirus, installs remote-access software or shares credentials. Attackers often ring many numbers until they find someone who really does have a problem.
* Free gifts, vouchers or software in return for filling in a survey that collects login details.
* Surveys at public events have reported people giving away passwords in exchange for small gifts such as chocolate or pens, showing how little reward is needed.



### 5.2 Prevention

* Staff should only accept IT support through **official channels** (ticketing system, known helpdesk numbers) and should **call back** using a verified number if someone contacts them unexpectedly.
* Never disable security tools or install remote-access software at the request of an unsolicited caller.
* Never share passwords with anyone, including IT: legitimate support does not need them.
* Publish clearly how IT will and will not contact employees.



## 6\. Comparison Table



|Attack type|Primary target|Psychological lever exploited|Best countermeasure|
|-|-|-|-|
|**Phishing** (spear, whaling, vishing, smishing)|Email/phone/SMS users, with executives and finance staff for spear phishing and whaling|Urgency, fear, authority, trust in a known brand|Phishing-resistant MFA plus regular user training and simulations|
|**Pretexting**|Helpdesk, customer service, HR and finance staff who hold or can release information|Trust, authority, helpfulness, social obligation|Strict identity verification and callback procedures|
|**Baiting**|General employees and anyone who finds or downloads "free" items|Curiosity and greed|Removable-media controls and endpoint protection|
|**Quid pro quo**|Non-technical staff who want help or rewards|Reciprocity and desire for help or benefit|Use only official support channels and verify unsolicited offers|



## 7\. Organizational Recommendations

### 7.1 Five-point employee security awareness training checklist

* **1. Onboarding and annual training:** every new hire and every employee completes security awareness training covering phishing, pretexting, baiting and quid pro quo, with a short assessment.
* **2. Regular phishing simulations:** run simulated phishing, vishing and USB-drop exercises at least quarterly, and give instant, non-punitive feedback to those who fail.
* **3. Clear reporting procedure:** provide one simple way (button, email address or phone number) to report suspicious messages, calls and devices, and acknowledge each report.
* **4. Verification rules for sensitive actions:** require out-of-band verification (callback to a known number) for payment changes, password resets, data requests and access grants.
* **5. Ongoing reinforcement and measurement:** use short refreshers, posters and real incident stories, and track metrics such as click rate, report rate and time-to-report to improve the program.

### 7.2 Supporting technical controls

* Multi-factor authentication everywhere, with phishing-resistant methods for administrators and executives.
* Email security: SPF, DKIM, DMARC, filtering and sandboxing.
* Endpoint protection and removable-media policies.
* Least-privilege access and network segmentation to limit damage when someone is tricked.
* Incident response plan that includes social engineering scenarios.



## 8\. Conclusion

Social engineering remains one of the most effective attack vectors because it targets human behavior rather than technical weaknesses. Phishing, pretexting, baiting and quid pro quo all rely on a few repeating psychological levers: trust, urgency, authority, curiosity and the wish to help. The case studies (RSA 2011, Twitter 2020, HP 2006 and Operation Buckshot Yankee) show that no organization is immune, including security companies and the military. The most effective defense combines **technical controls** (MFA, email security, device control), **clear verification processes**, and a **security-aware culture** where employees are trained, tested, and encouraged to question and report anything unusual.



## 9\. References

1. Verizon. *2024 Data Breach Investigations Report (DBIR)*. https://www.verizon.com/business/resources/reports/dbir/
2. FBI Internet Crime Complaint Center (IC3). *2023 Internet Crime Report*. https://www.ic3.gov/AnnualReport/Reports/2023\_IC3Report.pdf
3. CISA. *Avoiding Social Engineering and Phishing Attacks*. https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks
4. Coviello, A. (2011). *Open Letter to RSA SecurID Customers*, RSA / EMC, 17 March 2011.
5. Rivner, U. (2011). *Anatomy of an Attack*, RSA blog, April 2011.
6. Twitter (2020). *An update on our security incident*, 30 July 2020.
7. New York State Department of Financial Services (2020). *Report on Investigation of Twitter's July 15, 2020 Cybersecurity Incident*. https://www.dfs.ny.gov/Twitter\_Report
8. Lynn, W. J. III (2010). *Defending a New Domain: The Pentagon's Cyberstrategy*. Foreign Affairs, September/October 2010.
9. Tischer, M., et al. (2016). *Users Really Do Plug in USB Drives They Find*. IEEE Symposium on Security and Privacy.
10. US Congress (2006). *Telephone Records and Privacy Protection Act of 2006*.
11. Mitnick, K. \& Simon, W. (2002). *The Art of Deception: Controlling the Human Element of Security*. Wiley.

> \*\*Disclaimer:\*\* This report is for educational purposes. Always verify the latest statistics and URLs against the original sources before citing them.

