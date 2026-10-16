# Common Network Security Threats: Research Report

A research report on four common network security threats: **DoS/DDoS, Man-in-the-Middle (MITM), IP spoofing and DNS poisoning**. For each threat it explains how the attack works, reviews a documented real-world incident, describes the impact, and gives specific mitigation strategies for network administrators.

**Author:** Aisha Aziz
**Report file:** [`network_security_threats_report.md`](./network_security_threats_report.md)
**Format:** Markdown

---

## Objective

Write a comprehensive, well-structured report on common network security threats, covering how each attack works, its real-world impact and practical defences.

## What the report covers

| Section | Contents |
|---|---|
| **1. Introduction** | Why network security threats matter in today's landscape |
| **2. DoS / DDoS** | Volumetric, protocol and application-layer attacks; real incidents: Mirai botnet attack on Dyn (2016) and GitHub memcached attack (2018); 3 mitigations |
| **3. MITM** | ARP spoofing, rogue Wi-Fi, DHCP spoofing, forged certificates; real incident: DigiNotar breach (2011); 3 mitigations |
| **4. IP Spoofing** | Forged source addresses, reflection and session hijacking; real incidents: GitHub 2018 and Mitnick/Shimomura 1994; 3 mitigations |
| **5. DNS Poisoning** | Cache poisoning mechanics; real incidents: Kaminsky vulnerability (2008), MyEtherWallet DNS/BGP hijack (2018), CISA DNS hijacking alert; 3 mitigations (bonus section) |
| **6. Comparison table** | Attack vector, who is at risk, difficulty to execute and ease of mitigation for all four threats |
| **7. Conclusion** | 3 key takeaways for a network administrator |
| **8. References** | 13 sources including NIST, CISA, MITRE ATT&CK, IETF RFCs and Krebs on Security |

## Key takeaways

1. **Never trust addresses or names alone.** Use cryptographic authentication (TLS, IPsec, DNSSEC, 802.1X).
2. **Layer your defences.** Filter spoofed traffic, harden switches and DNS servers, and patch promptly.
3. **Plan before an attack happens.** Arrange DDoS protection, monitor traffic and DNS, and test your incident response plan.

## Mitigations at a glance

| Threat | Example controls |
|---|---|
| DoS / DDoS | Scrubbing/CDN service, rate limiting and WAF, ISP cooperation and response plan |
| MITM | TLS with HSTS, Dynamic ARP Inspection and DHCP snooping, VPN and certificate validation |
| IP spoofing | BCP 38 ingress/egress filtering and uRPF, cryptographic authentication, hardened UDP services |
| DNS poisoning | DNSSEC, resolver hardening and patching, registrar lock and DNS change monitoring |

## Skills demonstrated

- Network security analysis and threat research
- Incident case study review
- Technical writing and structured documentation
- Use of credible sources (NIST, CISA, MITRE ATT&CK)

## Disclaimer

This report is for educational purposes only. Statistics and links should be checked against the original sources before citing them.

## Contact

- GitHub: [github.com/azizaisha774](https://github.com/azizaisha774)
- LinkedIn: [linkedin.com/in/aisha-aziz-334596306](https://linkedin.com/in/aisha-aziz-334596306)
