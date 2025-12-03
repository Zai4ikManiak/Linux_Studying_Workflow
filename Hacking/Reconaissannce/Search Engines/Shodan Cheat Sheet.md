# What is Shodan?

Shodan is a search engine for Internet-connected devices.

IT gathers information about all devices directly connected to the Internet. If a device is directly hooked up to the Internet then Shodan queries it for various publicly-available information. The types of devices that are indexed can vary tremendously: ranging from small desktops up to nuclear power plants and everything in between.

---
# Advanced Search Filters

To get the most out of Shodan it's important to understand the search query syntax. Below are the Cheat Sheets used for different categories:

---

<details> 

<summary><strong><em>Network Search Filters</em></strong></summary>

---

<details>

<summary><strong>asn:</strong> <em>Search results to hosts whose IP addresses fall within the AS you specify.</em></summary>

| Browser Example | Console Example |
| :---: | :---: |
| `asn:AS13335` | `shodan search --limit 3 asn:AS13335` |
---
</details>
<details>

<summary><strong>has_ipv6:</strong> <em>Identifies devices or services that are <ins>reachable via IPv6 rather than (or in addition to) IPv4</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `has_ipv6:true` | `shodan search --limit 3 has_ipv6:true` |
---
</details>
<details>

<summary><strong>hostname:</strong> <em>Search for devices or hosts by their <ins>DNS hostname</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `hostname:"example.com"` | `shodan search --limit 3 hostname:"example.com"` |
---
</details>
<details>

<summary><strong>ip:</strong> <em>Search for a <ins>specific IP address</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `ip:104.21.7.138` | `shodan search --limit 3 ip:104.21.7.138` |
---
</details>

<details>

<summary><strong>isp:</strong> <em>Search for hosts or devices <ins>based on their Internet Service Provider (ISP)</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `isp:"Amazon.com"` | `shodan search --limit 3 isp:"Amazon.com"` |
---
</details>
<details>

<summary><strong>net:</strong> <em>Search for hosts within a <ins>specific IP network or range</ins>, using <ins>CIDR notation</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `net:5.252.178.0/24` | `shodan search --limit 3 net:5.252.178.0/24` |
---
</details>
<details>

<summary><strong>org:</strong> <em>Search for hosts based on the <ins>organization</ins> that owns or is assigned the IP address.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `org:"Amazon.com"` | `shodan search --limit 3 org:"Amazon.com"` |
---
</details>
<details>

<summary><strong>port:</strong> <em>Find hosts that have a <ins>specific network port open</ins>.</em></summary>

---
| Browser Example | Console Example |
| :---: | :---: |
| `port:80,443` | `shodan search --limit 3 port:80,443` |
</details>

---
</details>

<details>

<summary><strong><em>Location</em></strong></summary>

---

<details>

<summary><strong>city:</strong> <em>Search results to devices located in a <ins>specific city</ins>.</em></summary>

---
> ***NOTE***
>
> - City names with spaces must be wrapped in quotes.
> - Geolocation is based on IP-to-location databases, so accuracy depends on the provider.

| Browser Example | Console Example |
| :---: | :---: |
| `city:"New York"` | `shodan search --limit 3 city:"New York"` |
---
</details>
<details>

<summary><strong>country:</strong> <em>Search results to devices located in a <ins>specific country</ins>.</em></summary>

---
The filter uses the **ISO-3166-1 alpha-2** country code (two-letter code), not the country’s full name.

> ***NOTE***
>
> - Always use two-letter country codes.
> - Geolocation is based on IP databases and may not be 100% accurate.
> - Works well when narrowing down large, broad searches.

| Browser Example | Console Example |
| :---: | :---: |
| `country:US` | `shodan search --limit 3 country:US` |
---
</details>
<details>

<summary><strong>geo:</strong> <em>Searches for devices based on <ins>geographical coordinates</ins> (latitude and longitude) with an optional radius in kilometers.</em></summary>

---
> ***NOTE***
>
> <ins>geo:\<latitude>,\<longitude>,\<radius>.</ins>
>
> - Latitude and longitude can be positive or negative.
> - The radius is measured in **kilometers**.
> - Without a radius, Shodan uses a very small default radius around the point.

| Browser Example | Console Example |
| :---: | :---: |
| `geo:47.06181007599137,28.868065103036265` | `shodan search --limit 3 geo:47.06181007599137,28.868065103036265` |
---
</details>
<details>

<summary><strong>postal:</strong> <em>Search for hosts based on their <ins>postal code (ZIP code)</ins>.</em></summary>

---
> ***NOTE***
>
> - Works with **numeric and alphanumeric codes**.
> - Accuracy depends on IP geolocation databases.

| Browser Example | Console Example |
| :---: | :---: |
| `postal:75001` | `shodan search --limit 3 postal:75001` |
| `postal:"SW1A 1AA"` | `shodan search --limit 3 postal:"SW1A 1AA"` |
---
</details>
<details>

<summary><strong>region:</strong> <em>Search for hosts based on a <ins>geographical region, state, or province</ins>.</em></summary>

---
> ***NOTE***
>
> Region names must match **Shodan’s internal geolocation database names**; check spelling carefully.
> Works best for **large-area searches** where city-level granularity is not needed.

| Browser Example | Console Example |
| :---: | :---: |
| `region:California` | `shodan search --limit 3 region:California` |
---
</details>
<details>

<summary><strong>state:</strong> <em>Filter hosts based on the <ins>state, province, or administrative region</ins> associated with their IP address.</em></summary>

---
> ***NOTE***
>
> - In Shodan, state and region are often interchangeable depending on the country, but some geolocations may only recognize one of the two.
> - Works best for medium-scale geographic searches (larger than city, smaller than country).

| Browser Example | Console Example |
| :---: | :---: |
| `state:Florida` | `shodan search --limit 3 state:Florida` |
</details>

---

</details>


<details>

<summary><strong><em>Metadata</em></strong></summary>

---

<details>

<summary><strong>cpe:</strong> <em>Search for devices or services based on their <ins>Common Platform Enumeration (CPE) identifier</ins>.</em></summary>

---
> ***NOTE***
>
> CPE is a standardized way to name software, hardware, and operating systems, often used for vulnerability tracking (e.g., CVEs). This filter is extremely precise for identifying specific software versions or platforms across the internet.
>
> - **CPE format**: `cpe:/<part>:<vendor>:<product>:<version>:<update>:<edition>`
>	- `part` = `a`(application), `o`(operating system), `h`(hardware)
>	- `vendor` = software or hardware vendor
>	- `product` = product name
>	- `version` = version number
>	- The remaining fields (`update`, `edition`) are optional)
>
> - Extremely useful for vulnerability research or tracking specific software deployments.

| Browser Example | Console Example |
| :---: | :---: |
| `cpe:cpe:/o:canonical:ubuntu_linux:20.04` | `shodan search --limit 3 cpe:cpe:/o:canonical:ubuntu_linux:20.04` |
---
</details>
<details>

<summary><strong>device:</strong> <em>Search for internet‑connected systems based on <ins>the device type Shodan has identified</ins>.</em></summary>

---
> ***NOTE***
>
> <ins>device:\<device_type></ins>
>
> | device_type | What it returns |
> | :-- | :-- |
> | `webcam` | Devices recognized as webcams or IP cameras. |
> | `router` | Network routers detected by Shodan. |
> | `firewall` | Firewalls or security appliances. |
> | `pbx` | VoIP PBX systems. |
> | `scada` | Industrial control systems (ICS/SCADA). |
> | `printer` | Network‑connected printers. |
> | `nvr` | Network video recorders. |
>
> - The **device types are not user‑defined**; they come from Shodan’s classification engine.
> - Accuracy depends on **banner information** and **fingerprints**.
> - `device:` is different from `product:`
>	- `device:` broad category (router, webcam, etc.)
>	- `product:` specific software or firmware (e.g., Apache, OpenSSH).

| Browser Example | Console Example |
| :---: | :---: |
| `device:printer` | `shodan search --limit 3 device:printer` |
---
</details>
<details>

<summary><strong>hash:</strong> <em>Search for specific files on the internet <ins>using their cryptographic hash</ins>.</em></summary>

---
> ***NOTE***
>
> Shodan can index files exposed through web servers, FTP, SMB, and other services, and you can use this filter to locate a file by its **MD5**, **SHA-1**, or **SHA-256 hash**.
>
> - Useful for **malware research, identifying leaked files, or verifying file integrity** across public servers.
> - Only **files indexed by Shodan** can be searched with this filter.

| Browser Example | Console Example |
| :---: | :---: |
| `hash:5d41402abc4b2a76b9719d911017c592` | `shodan search --limit 3 hash:5d41402abc4b2a76b9719d911017c592` |
---
</details>
<details>

<summary><strong>os:</strong> <em>Search for devices based on their <ins>operating system</ins>.</em></summary>

---
> ***NOTE***
>
> - OS detection is **not always 100% accurate**; it relies on banner information and fingerprinting.
> - The search is **case-insensitive**.
> - Useful for network reconnaissance, security research, and vulnerability assessment.

| Browser Example | Console Example |
| :---: | :---: |
| `os:"Windows 10"` | `shodan search --limit 3 os:"Windows 10"` |
| `os:linux` | `shodan search --limit 3 os:linux` |
---
</details>
<details>

<summary><strong>product:</strong> <em>Search for devices or servers <ins>based on the software they run</ins>, rather than their hardware type.</em></summary>

---
> ***NOTE***
>
> Unlike `device:`, which identifies hardware categories, `product:` focuses on **specific software or services**.
> Useful for **finding specific technologies across the internet**, rather than broad device categories. 

| Browser Example | Console Example |
| :---: | :---: |
| `product:OpenSSH` | `shodan search --limit 3 product:OpenSSH` |
---
</details>
<details>

<summary><strong>version:</strong> <em>Search for <ins>specific versions of software</ins> or products.</em></summary>

---
> ***NOTE***
>
> - Is most effective when you know the exact version string Shodan reports.

| Browser Example | Console Example |
| :---: | :---: |
| `version:1.18 product:nginx` | `shodan search --limit 3 version:1.18 product:nginx` |
</details>

---
</details>

<details>

<summary><strong><em>Screenshots</em></strong></summary>

---

<details>

<summary><strong>has_screenshot:</strong> <em>Limit results to hosts for which Shodan has captured a <ins>web interface screenshot</ins>.</em></summary>

---
> ***NOTE***
>
> - Screenshots are often associated with **web interfaces** (port 80/443/8080) or **RDP interfaces**.
> - This filter is extremely useful for **visual browsing**, particularly during **research**, **auditing**, or **OSINT** work.

| Browser Example | Console Example |
| :---: | :---: |
| `has_screenshot:true` | `shodan search --limit 3 has_screenshot:true` |
---
</details>
<details>

<summary><strong>screenshot.hash:</strong> <em>Search for devices based on the <ins>perceptual hash (pHash)</ins> of their screenshot.</em></summary>

---
> ***NOTE***
>
> Shodan computes a visual similarity hash of each screenshot it captures.
> This lets you search for screenshots that look similar, not necessarily identical.
>
>
> - You might use this to:
>	- Find interfaces that share the same layout or branding.
>	- Group visually similar login pages.
>	- Locate other devices with the same dashboard UI.
>	- Identify clusters of similar services across the internet
>
> - The hash is **not a cryptographic hash** like MD5 or SHA—it's a **perceptual hash** used for similarity detection.
> - You cannot generate these hashes yourself with Shodan; you use ones that **Shodan already provides in search results**.
> - Often used during **research**, **asset discovery**, or **visual grouping** of public-facing interfaces.

| Browser Example | Console Example |
| :---: | :---: |
| `screenshot.hash:123456789` | `shodan search --limit 3 screenshot.hash:123456789` |
---
</details>
<details>

<summary><strong>screenshot.label:</strong> <em>Search for devices based on <ins>labels assigned to their screenshots by Shodan’s machine‑learning classifier</ins>.</em></summary>

---
> ***NOTE***
>
> - Shodan analyzes each screenshot and applies descriptive labels such as:
>	- login
>	- dashboard
>	- webcam
>	- rdp
>	- router
>	- storage
>	- industrial
>	- error
>	- printer
>	- vnc
>	- many others
>
> - Labels are generated by Shodan’s ML classifier, not manually.
> - A screenshot can have multiple labels.

| Browser Example | Console Example |
| :---: | :---: |
| `screenshot.label:webcam` | `shodan search --limit 3 screenshot.label:webcam` |
</details>

---
</details>

<details>

<summary><strong><em>Cloud</em></strong></summary>

---

<details>

<summary><strong>cloud.provider:</strong> <em>Search for devices, services, or hosts that Shodan has identified as running on a specific <ins>cloud provider’s infrastructure</ins>.</em></summary>

---
> ***NOTE***
>
> Below are typical values you can use (not exhaustive):
> | Provider | Value |
> | :-- | :-- |
> | Amazon Web Services | `amazon` |
> | Microsoft Azure | `microsoft` |
> | Google Cloud Platform | `google` |
> | Alibaba Cloud | `alicloud` |
>
> ...
> Shodan may recognize additional regional or specialized cloud providers as well.

| Browser Example | Console Example |
| :---: | :---: |
| `cloud.provider:amazon` | `shodan search --limit 3 cloud.provider:amazon` |
---
</details>
<details>

<summary><strong>cloud.region:</strong> <em>Search filter that lets you limit results to systems hosted in a <ins>specific region of a cloud provider</ins>.</em></summary>

---
> ***NOTE***
>
> Shodan identifies the region based on the cloud provider’s internal IP allocations and metadata.
> Region names match the provider’s naming conventions.
>
> Examples of Region Names by Provider
> - AWS
>	- `us-east-1`
>	- `us-west-2`
>	- `eu-central-1`
>	- `ap-southeast-1`
>
> - Azure
>	- `westeurope`
>	- `eastus`
>	- `northeurope`
>	- `japaneast`
>
> - Google Cloud
>	- `us-central1`
>	- `europe-west4`
>	- `asia-south1`
>
> Not all providers have region-level mapping in Shodan, but many major ones do.

| Browser Example | Console Example |
| :---: | :---: |
| `cloud.region:us-east-1` | `shodan search --limit 3 cloud.region:us-east-1` |
---
</details>
<details>

<summary><strong>cloud.service:</strong> <em>Search for hosts based on <ins>the specific cloud service</ins> they belong to.</em></summary>

---
> ***NOTE***
>
> It limits your results to systems that Shodan has classified as using a particular <ins>cloud service type</ins>, not just a cloud provider overall.
>
> This allows you to target:
> - Compute instances (EC2, Azure VM, GCP Compute Engine)
> - Storage services (S3, Azure Blob Storage)
> - Serverless platforms
> - Managed databases
> - Edge/CDN services
> - Load balancers
>
> And more—depending on what Shodan is able to classify.

| Browser Example | Console Example |
| :---: | :---: |
| `cloud.service:ec2` | `shodan search --limit 3 cloud.service:ec2` |
</details>

---
</details>

<details>

<summary><strong><em>HTTP</em></strong></summary>

---

<details>

<summary><strong>http.component:</strong> <em>Search for devices based on <ins>web technologies detected in their HTTP responses</ins>.</em></summary>

---
> ***NOTE***
>
> | Common Component Names | |
> | :-- | :-- |
> | CMS | - `wordpress`<br> - `joomla`<br> - `drupal`<br> - `ghost` |
> | Frameworks | - `laravel`<br> - `django`<br> - `express`<br> - `rails`<br> - `spring` |
> | JavaScript libraries | - `jquery`<br> - `angular`<br> - `react`<br> - `vue` |
> | E-commerce | - `magento`<br> - `woocommerce`<br> - `shopify` |
> | Misc | - `socket.io`<br> - `bootstrap`<br> - `cloudflare`<br> - `matomo` |

| Browser Example | Console Example |
| :---: | :---: |
| `http.component:wordpress` | `shodan search --limit 3 http.component:wordpress` |
---
</details>
<details>

<summary><strong>http.component_category:</strong> <em>Search for web technologies by their <ins>category</ins> rather than a specific component name.</em></summary>

---
> ***NOTE***
>
> <ins>Common Shodan Component Categories</ins>
> | Category | Meaning |
> | :-- | :-- |
> | `cms` | Content management systems (WordPress, Joomla, etc.) |
> | `framework` | Backend frameworks (Django, Laravel, Rails…) |
> | `javascript` | Front-end JS libraries (jQuery, Vue, React…) |
> | `ecommerce` | Magento, WooCommerce, PrestaShop… |
> | `analytics` | Google Analytics, Matomo, etc. |
> | `security` | WAFs, security headers, Cloudflare tech |
> | `server` | Web servers and modules |
> | `cdn` | CDN-based components (Cloudflare, Akamai…) |
> | `blog` | Blog engines |
> | `marketing` | Marketing and tracking components |

| Browser Example | Console Example |
| :---: | :---: |
| `http.component_category:analytics` | `shodan search --limit 3 http.component_category:analytics` |
---
</details>
<details>

<summary><strong>http.dom_hash:</strong> <em>Search for hosts whose <ins>DOM (Document Object Model) content matches a specific hash</ins>.</em></summary>

---
> ***NOTE***
>
> Shodan renders the HTML of a web page, builds its DOM, and then computes a hash of that structure.
> You can then use this hash to find identical or nearly identical web pages across the internet.
>
> - This is heavily used in threat hunting, phishing detection, and OSINT.

| Browser Example | Console Example |
| :---: | :---: |
| `http.dom_hash:1239617585` | `shodan search --limit 3 http.dom_hash:1239617585` |
---
</details>
<details>

<summary><strong>http.favicon.hash:</strong> <em>Search filter that lets you find hosts by the <ins>hash of their website’s favicon.ico file</ins>.</em></summary>

---
> ***NOTE***
>
> Shodan downloads the favicon from the HTTP service, computes a MurmurHash3 value of the Base64-encoded favicon, and stores it. You can then search for all hosts using the exact same favicon.
>
> This is one of the most powerful OSINT filters in Shodan.
>
> ---
> **Why this filter is extremely powerful?**
>
> Favicons often uniquely identify
> - Web applications
> - Frameworks
> - Routers / IoT admin pages
> - Security camera dashboards
> - VPN portals
> - Firewalls
> - Load balancers
> - C2 servers
> - Phishing pages
> - SaaS login portals
> - Internal tools accidentally exposed
>
> Even if:
> - the URL changes
> - HTML changes
> - DNS changes
> - title changes

| Browser Example | Console Example |
| :---: | :---: |
| `http.favicon.hash:551003356` | `shodan search --limit 3 http.favicon.hash:551003356` |
---
</details>
<details>

<summary><strong>http.headers_hash:</strong> <em>Search for hosts based on the <ins>hash of their HTTP response headers</ins>.</em></summary>

---
> ***NOTE***
>
> Shodan takes all the HTTP headers received from a service, normalizes them, then generates a 32-bit hash. You can use this hash to find other systems with identical header structures, which is extremely useful for fingerprinting technologies and infrastructure.
>
> | What this filter Does? | |
> | :-- | :-- |
> | It filters hosts by the exact same set of HTTP headers, including: | - Header names<br> - Header ordering<br> - Header values (in normalized form) |
> | This can reveal: | - Same software stack<br> - Same server configuration<br> - Same reverse proxy setup<br> - Same CDN configuration<br> - Identical phishing or malware pages<br> - The same WAF or load balancer<br> - Shared hosting templates |

| Browser Example | Console Example |
| :---: | :---: |
| `http.headers_hash:987654321` | `shodan search --limit 3 http.headers_hash:987654321` |
---
</details>
<details>

<summary><strong>http.html:</strong> <em>Searches the <ins>raw HTML content</ins> of a webpage exactly as Shodan downloaded it.</em></summary>

---
> ***NOTE***
>
> This is one of the most flexible and powerful filters in Shodan because it searches inside the **raw HTML body** returned by the server, including:
> - Visible text
> - Hidden text
> - Script tags
> - Inline JavaScript
> - Comments
> - Meta tags
> - HTML attributes
> - Embedded URLs
> - Error pages
> - Login forms
> - Any keyword or string inside the page
>
> If the text appears in the HTML source, you can find it.

| Browser Example | Console Example |
| :---: | :---: |
| `http.html:"/static/js/main.js"` | `shodan search --limit 3 http.html:"/static/js/main.js"` |
---
</details>


| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `http.html` | Search for web servers by looking for *specific text inside the raw HTML body* of their HTTP responses. | `http.html:"Admin Login"` | `shodan search --limit 3 http.html:"Admin Login"` |
| `http.html_hash` | Search for web servers based on a *hash of their HTML content*. Unlike http.html, which searches for literal text strings in the HTML, this filter identifies pages that are structurally identical by comparing the hash of the full HTML response. | `http.html_hash:1234567890abcdef` | `shodan search --limit 3 http.html_hash:1234567890abcdef` |
| `http.robots_hash` | Search for web servers based on a *hash of their robots.txt file*. | `http.robots_hash:abcdef1234567890` | `shodan search --limit 3 http.robots_hash:abcdef1234567890` |
| `http.securitytxt` | Used to search for web servers that *host a security.txt file* and optionally match specific text inside it. | `http.securitytxt:"security@example.com"` | `shodan search --limit 3 http.securitytxt:"security@example.com"` |
| `http.server_hash` | Used to search for web servers based on a *hash of the Server HTTP header*. | `http.server_hash:547046460` | `shodan search --limit 3 http.server_hash:547046460` |
| `http.status` | Search for web servers based on the HTTP status code they return in response to Shodan’s crawl request. | `http.status:403` | `shodan search --limit 3 http.status:403` |
| `http.title` | Search for web servers based on the *text inside the <title> HTML* tag of their webpage. | `http.title:"Admin Login"` | `shodan search --limit 3 http.title:"Admin Login"` |
| `http.title_hash` | Search for web servers based on a *hash of the <title> tag* from their HTML response | `http.title_hash:123456789` | `shodan search --limit 3 http.title_hash:123456789` |
| `http.waf` | Search for web servers where Shodan has detected the presence of a *Web Application Firewall (WAF)*. | `http.waf:"Cloudflare"` | `shodan search --limit 3 http.waf:"Cloudflare"` |

</details>

<details>

<summary>SSL</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `ssl` | Used to match *raw SSL/TLS data blocks* that Shodan captured from a service. | `ssl:"TLSv1.2"` | `shodan search --limit 3 ssl:"TLSv1.2"` |
| `has_ssl` | Returns results based solely on whether a service *provides SSL/TLS information, regardless of the port or protocol*. | `has_ssl:true` | `shodan search --limit 3 has_ssl:true` |
| `ssl.alpn` | Search for hosts based on the *Application-Layer Protocol Negotiation (ALPN)* protocols they advertise during the TLS handshake. | `ssl.alpn:imap` | `shodan search --limit 3 ssl.alpn:imap`|
| `ssl.cert.alg` | Search for hosts based on the *algorithm used to sign the SSL/TLS certificate*. It matches the *certificate signature algorithm* (not the key algorithm), meaning the crypto algorithm used by the Certificate Authority (CA) to sign the certificate. | `ssl.cert.alg:sha1` | `shodan search --limit 3 ssl.cert.alg:sha1` |
| `ssl.cert.expired` | Search for hosts based on whether the SSL/TLS certificate they presented is currently expired. | `ssl.cert.expired:true` | `shodan search --limit 3 ssl.cert.expired:true` |
| `ssl.cert.extension` | Search for hosts based on the X.509 certificate extensions present in the certificate the host provides. | `ssl.cert.extension:certificatePolicies` | `shodan search --limit 3 ssl.cert.extension:certificatePolicies` |
| `ssl.cert.fingerprint` | Search for hosts by the *cryptographic fingerprint (hash)* of the certificate they present during the TLS handshake. | `ssl.cert.fingerprint:AB:CD:EF:01:23:45:67:89:AA:BB:CC:DD:EE:FF:11:22:33:44:55:66` | `shodan search --limit 3 ssl.cert.fingerprint:AB:CD:EF:01:23:45:67:89:AA:BB:CC:DD:EE:FF:11:22:33:44:55:66` |
| `ssl.cert.issuer.cn` | search for hosts based on the *Common Name (CN)* of the *certificate issuer* — essentially, the Certificate Authority (CA) that signed the certificate. | `ssl.cert.issuer.cn:"DigiCert TLS RSA SHA256 2020 CA1"` | `shodan search --limit 3 ssl.cert.issuer.cn:"DigiCert TLS RSA SHA256 2020 CA1"` |
| `ssl.cert.pubkey.bits` | Search for hosts based on the *size (in bits) of the public key* in the SSL/TLS certificate presented by the server. This is useful for identifying certificates that may be weak (small key sizes) or strong (modern large key sizes). | `ssl.cert.pubkey.bits:1024` | `shodan search --limit 3 ssl.cert.pubkey.bits:1024` |
| `ssl.cert.pubkey.type` | Search for hosts based on the *type of public key* used in the SSL/TLS certificate the host presents. | `ssl.cert.pubkey.type:ECDSA` | `shodan search --limit 3 ssl.cert.pubkey.type:ECDSA` |
| `ssl.cert.serial` | Search for hosts based on the *serial number of the SSL/TLS certificate* they present. | `ssl.cert.serial:0x1A2B3C4D5E6F` | `shodan search --limit 3 ssl.cert.serial:0x1A2B3C4D5E6F` |
| `ssl.cert.subject.cn` | Search for hosts based on the *Common Name (CN)* in the *subject* of the SSL/TLS certificate they present. This represents the *primary domain or hostname* the certificate was issued for. | `ssl.cert.subject.cn:"example.com"` | `shodan search --limit 3 ssl.cert.subject.cn:"example.com"` |
| `ssl.chain_count` | Search for hosts based on the *number of certificates in the SSL/TLS chain* presented by the server. | `ssl.chain_count:3` | `shodan search --limit 3 ssl.chain_count:3` |
| `ssl.cipher.bits` | Search for hosts based on the *bit strength of the cipher* used in the SSL/TLS connection during the handshake. | `ssl.cipher.bits:128` | `shodan search --limit 3 ssl.cipher.bits:128` |
| `ssl.cipher.name` | Search for hosts based on the *name of the cipher suite* used in the SSL/TLS connection during the handshake. | `ssl.cipher.name:TLS_AES_256_GCM_SHA384` | `shodan search --limit 3 ssl.cipher.name:TLS_AES_256_GCM_SHA384` |
| `ssl.cipher.version` | Search for hosts based on the *TLS/SSL protocol version* negotiated during the handshake for a particular cipher. | `ssl.cipher.version:TLSv1` | `shodan search --limit 3 ssl.cipher.version:TLSv1` |
| `ssl.ja3s` | Search for hosts based on their *JA3S fingerprint* — the *server-side TLS fingerprint* created from the parameters a server uses in its *Server Hello* message during a TLS handshake. | `ssl.ja3s:"b32309a26951912be6e0c6d1b99b6f20"` | `shodan search --limit 3 ssl.ja3s:"b32309a26951912be6e0c6d1b99b6f20"` |
| `ssl.jarm` | Search for hosts based on their *JARM fingerprint* — a server‑side TLS fingerprinting method created by Salesforce to identify, classify, or cluster servers by the way they respond to *multiple crafted TLS Client Hello probes*. | `ssl.jarm:"2ad2ad0002ad2ad0002ad2ad2ad2ad000d7c3f6f8a4a3d0f66f03b6e3f6c4"` | `shodan search --limit 3 ssl.jarm:"2ad2ad0002ad2ad0002ad2ad2ad2ad000d7c3f6f8a4a3d0f66f03b6e3f6c4"` |
| `ssl.version` | Search for hosts based on the *SSL/TLS protocol version* they support or negotiate during the TLS handshake. | `ssl.version:TLSv1.2` | `shodan search --limit 3 ssl.version:TLSv1.2` |

</details>

<details>

<summary>Unknown per now</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `asset` | Used to target specific assets that have been tagged in Shodan’s Asset Inventory system (used in Shodan Monitor / Enterprise features). restricts results to hosts that Shodan has grouped under a particular *asset label*. | `asset:web` | `shodan search --limit 3 asset:web` |
| `google_ads` | Returns results for devices or websites that include a specific Google AdSense Publisher ID. | `google_ads:pub-1234567890123456` | `shodan search --limit 3 google_ads:pub-1234567890123456` |
| `google_analytics` | Allows you to find devices, websites, or hosts that have Google Analytics tracking enabled. | `google_analytics:"UA-12345678-1"` | `shodan search --limit 3 google_analytics:"UA-12345678-1"` |
| `google_tag_manager` | This filter helps locate websites, web applications, or devices that have *Google Tag Manager installed*. | `google_tag_manager:"GTM-ABC1234"` | `shodan search --limit 3 google_tag_manager:"GTM-ABC1234"` |
| `has_vuln` | Find hosts that are *known to have one or more vulnerabilities*. | `has_vuln:true` | `shodan search --limit 3 has_vuln:true` |
| `shodan.module` | Search for hosts *based on the specific Shodan scanning module that collected the data*. | `shodan.module:http` | `shodan search --limit 3 shodan.module:http` |
| `tiktok_pixel` | Find hosts or websites that have a TikTok Pixel installed. | `tiktok_pixel:1234567890` | `shodan search --limit 3 tiktok_pixel:1234567890` |
| `x_pixel` | Find hosts or websites that have an “X Pixel” tracking script installed. The exact “X Pixel” can refer to a proprietary or third-party analytics/tracking tool that uses a unique numeric or alphanumeric pixel ID. | `x_pixel:1234567890` | `shodan search --limit 3 x_pixel:1234567890` |

</details>

As reference was used:
- [Shodan Filter Reference]()
- [Advanced Shodan Search Filter](https://www.shodan.io/search/advanced)
- [External Links](https://github.com/JavierOlmedo/shodan-filters?utm_source=chatgpt.com)
