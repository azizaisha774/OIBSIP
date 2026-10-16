# The Importance of Patch Management

**Author:** Aisha Aziz
**Topic:** Patch management, unpatched systems, and building an effective patching strategy
**Format:** Research report



## Table of Contents

1. [Introduction](#1-introduction)
2. [Why Patches Matter](#2-why-patches-matter)
3. [Consequences of Not Patching](#3-consequences-of-not-patching)
4. [The Patch Management Lifecycle](#4-the-patch-management-lifecycle)
5. [Best Practices: A Prioritised 7-Step Checklist](#5-best-practices-a-prioritised-7-step-checklist)
6. [Challenges and How to Overcome Them](#6-challenges-and-how-to-overcome-them)
7. [Conclusion](#7-conclusion)
8. [References](#8-references)



## 1\. Introduction

Patch management is the process of applying vendor-issued updates to close security vulnerabilities and optimize the performance of software and devices. Patch management is sometimes considered a part of vulnerability management.



In practice, patch management is about balancing cybersecurity with the business's operational needs. Hackers can exploit vulnerabilities in a company's IT environment to launch cyberattacks and spread malware. Vendors release updates, called "patches," to fix these vulnerabilities. However, the patching process can interrupt workflows and create downtime for the business. Patch management aims to minimize that downtime by streamlining patch deployment.



### Role in the vulnerability lifecycle



Every vulnerability moves through a lifecycle. Patch management is the stage that closes the gap between "a fix exists" and "the fix is installed":


Vulnerability     Vendor / researcher     CVE assigned      Patch released
introduced   -->  discovers it       -->  and CVSS scored --> by vendor
                                                                  |
                                                                  v
                  Attackers build         Organisation     <-- Window of exposure
                  exploits (PoC)  ------> applies patch        (patch management
                                                                 shrinks this)


## 2\. Why Patches Matter

### 2.1 How vulnerabilities are discovered, reported and scored



1. **Discovery.** Vulnerabilities are found by vendors, independent security researchers, bug bounty hunters, penetration testers, and unfortunately also by attackers and state-sponsored groups.
2. **Responsible disclosure.** Researchers usually report the flaw privately to the vendor, giving time to develop a fix before details are made public.
3. **CVE assignment.** The flaw is catalogued with a unique **CVE (Common Vulnerabilities and Exposures)** identifier, for example `CVE-2017-0144`. The CVE program, run by MITRE and sponsored by CISA, gives the whole industry a common name for each vulnerability.
4. **CVSS scoring.** The **Common Vulnerability Scoring System (CVSS)** rates severity from 0.0 to 10.0. The National Vulnerability Database (NVD) publishes these scores.



|CVSS score|Severity|
|-|-|
|0.0|None|
|0.1 - 3.9|Low|
|4.0 - 6.9|Medium|
|7.0 - 8.9|High|
|9.0 - 10.0|Critical|

5. **Exploitation.** Once a CVE is public, attackers can study the patch to understand the flaw and write exploit code. Exploits are often packaged into automated tools and malware. CISA maintains the **Known Exploited Vulnerabilities (KEV) catalog**, a list of CVEs confirmed to be exploited in the wild, which organizations should treat as top patching priority.



### 2.2 Real-world breach 1: WannaCry and EternalBlue (2017)



* **The vulnerability:** `CVE-2017-0144`, a flaw in Microsoft's SMBv1 protocol, exploited by a tool called **EternalBlue**, which was allegedly developed by the US National Security Agency and leaked by the Shadow Brokers group in April 2017.
* **The patch:** Microsoft released security bulletin **MS17-010** on **14 March 2017**, two months *before* the attack.
* **The attack:** On **12 May 2017**, the WannaCry ransomware worm began spreading automatically across networks using EternalBlue. It infected more than **200,000 computers in about 150 countries**.
* **Impact:** The UK's National Health Service was among the hardest hit, with hospitals cancelling appointments and diverting ambulances. Other victims included manufacturers, telecom companies and logistics firms.
* **Lesson:** The fix was available for two months. Organizations that had applied MS17-010, or retired SMBv1 and older unsupported Windows versions, were protected. WannaCry is the textbook example of an attack that was entirely preventable through patching.
* 

### 2.3 Real-world breach 2: Equifax (2017)



* **The vulnerability:** `CVE-2017-5638`, a remote code execution flaw in **Apache Struts**, a widely used web application framework.
* **The patch:** Apache released a fix in **March 2017**, and the US government alerted organisations to the flaw.
* **The failure:** Equifax did not patch an internet-facing dispute portal in time. Attackers gained access in **May 2017** and remained inside the network for about **76 days** before being detected in July 2017.
* **Impact:** Personal data of approximately **147 million people** (names, Social Security numbers, birth dates, addresses and in some cases driver's licence numbers) was exposed. Equifax later agreed to a settlement with the US FTC, CFPB and states of at least **USD 575 million**, which could rise to USD 700 million.
* **Lesson:** Poor asset inventory, a failed patch notification process and an expired scanning certificate meant the vulnerable system was never fixed or flagged. Patching is a *process* problem as much as a technical one.

### 2.4 Other notable examples



* **Not Petya (2017)** also used EternalBlue and caused billions of dollars in damage to global companies.
* **Log4Shell (December 2021)** affected millions of systems that embedded the Log4j library, many of which organizations struggled to even locate.
* **Edge-device flaws (VPNs, firewalls)** are now among the most actively exploited categories, often within days of disclosure.



## 3\. Consequences of Not Patching

|Consequence|Description|
|-|-|
|**Data breaches**|Attackers use known flaws to steal customer, employee and business data.|
|**Ransomware**|Unpatched systems are a common entry point for ransomware operators, who encrypt data and demand payment.|
|**Compliance violations**|Regulations and standards expect timely patching, including PCI DSS, HIPAA, ISO 27001 and GDPR (which requires appropriate security measures).|
|**Financial penalties**|Fines, legal settlements, incident response costs, and lost revenue from downtime.|
|**Reputation damage**|Loss of customer trust and market value after a public breach.|

### 

### Statistics



* **Vulnerability exploitation as an attack entry point is rising.** The **Verizon 2025 Data Breach Investigations Report (DBIR)**, covering 12,195 confirmed breaches, found that exploitation of vulnerabilities was the initial access vector in **20% of breaches**, a **34% increase** on the previous year.
* **Patching is too slow.** The same report found that organisations fully remediated only about **54%** of edge-device and VPN vulnerabilities, taking a **median of 32 days**. Meanwhile the median time for these vulnerabilities to be mass-exploited was effectively **zero days**: they were added to CISA's KEV catalog on or before the day the CVE was published.
* **Espionage groups rely on it.** In the 2025 DBIR, vulnerability exploitation was the initial access method in about **70%** of espionage-motivated breaches.
* **Breaches are expensive.** IBM's *Cost of a Data Breach Report 2025* put the global average cost of a breach at about **USD 4.44 million**, and the US average above **USD 10 million**.
* **Case costs:** Equifax's settlement was at least **USD 575 million**; the WannaCry outbreak was estimated to have caused hundreds of millions to billions of dollars in losses worldwide.

&#x20;



4\. **The Patch Management Lifecycle**

The lifecycle below follows the five phases **Discovery → Assessment → Testing → Deployment → Verification**, consistent with the process described in NIST SP 800-40 Rev. 4.

```
+------------+   +------------+   +---------+   +------------+   +--------------+
| 1.Discovery|-->|2.Assessment|-->|3.Testing|-->|4.Deployment|-->|5.Verification|
+------------+   +------------+   +---------+   +------------+   +--------------+
      ^                                                                  |
      +------------------------ continuous improvement <-----------------+
```

### Phase 1: Discovery

**Goal:** Know what you own and what needs patching.

* Maintain an accurate **asset inventory** (servers, endpoints, network devices, cloud workloads, containers, third-party software, IoT/OT devices).
* Monitor vendor security advisories, the NVD, CISA alerts and the KEV catalog.
* Run **vulnerability scans** (for example Nessus, OpenVAS) to find missing patches.
* *Output:* a list of available patches mapped to affected assets.



### Phase 2: Assessment

**Goal:** Decide what matters most.

* Evaluate each vulnerability using **CVSS score**, whether it is **actively exploited** (KEV), whether an exploit is public, and how **exposed** the asset is (internet-facing or internal).
* Consider **business criticality** of the affected system and the data it holds.
* Assign a priority and a target deadline (for example emergency, high, routine).
* *Output:* a prioritized patching schedule.
* 

### Phase 3: Testing

**Goal:** Make sure the patch does not break anything.

* Test patches in a **staging or pilot environment** that mirrors production.
* Check application compatibility, performance and rollback procedures.
* For emergency patches, use an accelerated test with a smaller pilot group.
* *Output:* approved patches with a documented rollback plan.



### Phase 4: Deployment

**Goal:** Install patches safely and on time.

* Use **automated tools** (WSUS, Microsoft Intune, Ansible, Red Hat Satellite, SCCM or similar) for consistency and speed.
* Roll out in **phases** (pilot group, then wider groups), scheduled in **maintenance windows**.
* Communicate with stakeholders and follow **change management** procedures.
* If a patch cannot be applied, use **compensating controls** (network segmentation, virtual patching, disabling the vulnerable service).
* *Output:* patches installed across target systems.



### Phase 5: Verification

**Goal:** Prove the fix worked.

* **Rescan** systems to confirm the vulnerability is gone.
* Check that systems are stable and applications are working.
* Record results for **audit and compliance** evidence.
* Track metrics such as time-to-patch, patch coverage percentage and number of overdue critical patches.
* Feed lessons learned back into Discovery.
* *Output:* verified closure and reporting.



## 5\. Best Practices: A Prioritized 7-Step Checklist

Steps are listed in priority order. Early steps provide the foundation for the later ones.

* &#x20;**1. Build and maintain a complete asset inventory.** You cannot patch what you do not know exists. Include cloud, shadow IT and third-party components, and assign an owner to each asset.
* **2. Prioritize by risk, not just CVSS.** Combine CVSS with CISA KEV status, exploit availability, asset exposure and business criticality. Patch actively exploited, internet-facing systems first.
* **3. Define patching policies and SLAs.** Set clear deadlines, for example: emergency (actively exploited) within 24-72 hours, critical within 7-14 days, high within 30 days, and others on a routine cycle. Get management approval.
* **4. Test before you deploy.** Use a staging environment and pilot group, and always prepare a rollback plan.
* **5. Automate deployment.** Use patch management tools to remove manual effort, reduce human error and shrink the window of exposure.
* **6. Verify and monitor continuously.** Rescan after patching, track compliance metrics, and report to leadership regularly.
* **7. Plan for exceptions and emergencies.** Document compensating controls for systems that cannot be patched, retire end-of-life software, and keep an out-of-band emergency patching process ready.



## 6\. Challenges and How to Overcome Them

|Challenge|Why it happens|How to overcome it|
|-|-|-|
|**Legacy and end-of-life systems**|Vendor no longer provides patches; old applications depend on outdated operating systems.|Plan migration or replacement; isolate with network segmentation; use virtual patching (IPS/WAF rules); apply compensating controls and restrict access; budget for lifecycle replacement.|
|**Downtime concerns**|Critical systems (hospitals, production lines, payment systems) cannot easily be taken offline.|Schedule maintenance windows; use redundancy, clustering and rolling updates; use live or hot patching where supported; communicate the cost of an outage versus a breach.|
|**Testing requirements**|Patches can break applications; thorough testing takes time and resources.|Maintain a staging environment; automate regression tests; test in pilot groups; define a faster path for emergency patches; always have a rollback plan.|
|**Lack of asset visibility**|Unknown, unmanaged or "shadow IT" devices are missed.|Use automated discovery and scanning; maintain a CMDB; enforce device enrolment.|
|**Too many patches / limited staff**|Large volume of updates overwhelms small IT teams.|Risk-based prioritisation; automation; managed patching services.|
|**Third-party and remote devices**|Laptops off the network, contractors and vendor-managed software are harder to update.|Cloud-based endpoint management (such as Intune); contractual patching requirements; vendor risk reviews.|
|**Organizational friction**|A divide between business owners (who want uptime) and security teams (who want fast patching).|Follow NIST's recommendation: leadership, business owners and security teams jointly create an enterprise patching strategy, and report metrics in business terms.|



## 7\. Conclusion

Patch management is one of the most effective and least glamorous defenses in cybersecurity. The breaches at Equifax and the global WannaCry outbreak show that attackers rarely need sophisticated techniques when known, fixable vulnerabilities remain open. Current data shows attackers exploiting vulnerabilities faster than many organizations can respond, especially on internet-facing edge devices.

An effective strategy rests on a few principles: know your assets, prioritize by real-world risk, test, automate, verify, and have a plan for exceptions. Just as importantly, patching needs support from leadership, because it is a business risk decision as much as a technical task. Organisations that treat patching as a continuous, measured process significantly shrink the window of exposure that attackers rely on.



## 8\. References

1. **Souppaya, M., \& Scarfone, K.** (2022). *Guide to Enterprise Patch Management Planning: Preventive Maintenance for Technology* (NIST Special Publication 800-40 Rev. 4). National Institute of Standards and Technology. https://doi.org/10.6028/NIST.SP.800-40r4
2. **NIST National Cybersecurity Center of Excellence.** *Improving Enterprise Patching for General IT Systems* (NIST SP 1800-31). https://www.nccoe.nist.gov/
3. **CISA.** *Known Exploited Vulnerabilities (KEV) Catalog.* Cybersecurity and Infrastructure Security Agency. https://www.cisa.gov/known-exploited-vulnerabilities-catalog
4. **MITRE.** *Common Vulnerabilities and Exposures (CVE) Program.* https://www.cve.org / https://cve.mitre.org
5. **NIST.** *National Vulnerability Database (NVD)*, including `CVE-2017-0144` and `CVE-2017-5638`. https://nvd.nist.gov
6. **FIRST.** *Common Vulnerability Scoring System (CVSS) Specification.* https://www.first.org/cvss/
7. **Microsoft.** *Microsoft Security Bulletin MS17-010 - Critical.* March 2017. https://learn.microsoft.com/en-us/security-updates/securitybulletins/2017/ms17-010
8. **CISA.** *Alert (TA17-132A): Indicators Associated With WannaCry Ransomware.* May 2017. https://www.cisa.gov/news-events/alerts/2017/05/12/indicators-associated-wannacry-ransomware
9. https://www.ibm.com/think/topics/patch-management

