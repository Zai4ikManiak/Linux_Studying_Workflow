### What is Reconaissannce / Footprinting ?

> [!NOTE]
> Reconaissannce refers to the preparatory phase where an attacker seeks to *gather as much information as possible about a target of evaluation* prior to launching an attack.

This technique can be categorized into <ins>2 categories</ins>:

- **Passive Footprinting**
	> Gethering information about the target <ins>without direct interaction</ins> with the it.
	- Search Engines
		- [Google Searching](https://github.com/Zai4ikManiak/Linux_Studying_Workflow/blob/main/Reconaissannce/Advanced_Google_Search_Operators%20Cheat%20Sheet.md)
	- Social networking
	- Open-Source Intelligence (OSINT) gathering
	- Proprietary database and paid services
	- Sharing intelligence with partner organizations or industry groups.

- **Active Footprinting**
	> Gathering information about the target <ins>with direct interaction</ins> with it.
	> It may requires more preparation than passive footprinting, as it may leave traces that may alert the target organization.
	- DNS interrogation
	- Social networking
	- Network/Port scanning
	- User and services enumeration

---

A detailed footprinting provides maximal information about the target (placement of firewalls, proxies, and other security solutions), allowing the attacker to identify vulnerabilities in the target system to select appropriate exploits.

---

### Information Obtained in Footprinting

There are <ins>3 main categories of information obtained</ins> during reconaissannce:

<details>

<summary>Organization Information</summary>

- Employee details (employee names, contact addresses, designations, and work experience).
- Addresses and mobile/telephone numbers.
- Branch and location details.
- Partners of the organization.
- Web links to other company-related sites.
- Background of the organization.
- Web technologies.
- New articles, press releases, and related documents.
- Legal documents related to the organization.
- Patents and trademarks related to the organization.

Attackers can access organizational information and use such information to identify key personnel and launch social engineering attacks to extract sensitive data about the entity.

</details>

<details>

<summary>Network Information</summary>

- Domain and sub-domains.
- Network blocks.
- Network topology, trusted routers, and firewalls.
- IP addresses of the reachable systems.
- Whois records.
- DNS records and related information.

</details>

<details>

<summary>System Information</summary>

- Web server OS.
- Location of web servers.
- Publicly available email addresses.
- Usernames, passwords, and so on.

</details>

---

### Footprinting Threats

The following are assorted threats made possible through reconaissannce:

- **Social Engineering**
	> Without using any intrusion methods, hackers directly and indirectly collect information through persuasion and other means. Hackers gather crucial information from wiling employees who are unaware of the hacker's intent.

- **System and Network Attacks**
	>Footprinting enables an attacker to perform system and network attacks. Thus, attackers can gather information related to the target organization's system configuration, the OS running on the machine, and so on.
	>Using this information, attackers can find vulnerabilities in the target system and then exploit such vulnerabilities. They can then take control of the target system or the entire network.

- **Information Leakage**
	> Information leakage poses a threat to any organization. If sensitive information of an entity falls into the hands of attackers, they can mount an attack based on the information or alternatively use it for monetary benefit.

- **Privacy Loss**
	>Through footprinting, hackers can access the systems and networks of the organization and even escalate the privileges up to admin levels, resulting in the loss of privacy for the organization as a whole and for its individual personnel.

- **Corporate Espionage**
	> Corporate espionage is a central threat to organizations, as competitors often aim to attempt to acquire sensitive data through footprinting. Through this approach, competitors can launch similar products in the market, alter prices, and generally undermine the market position of a target organization.

- **Business Loss**
	> Footprinting can have a major effect on organizations such as online business and other e-commerce websites as well as banking and finance-related business. Billions of dollars are lost every year due to malicious attacks by hackers.
