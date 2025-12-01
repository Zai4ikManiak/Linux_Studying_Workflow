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
> - In Shodan, state and region are often interchangeable depending on the country, but some geolocations may only recognize one of the two.
> - Works best for medium-scale geographic searches (larger than city, smaller than country).

| Browser Example | Console Example |
| :---: | :---: |
| `state:Florida` | `shodan search --limit 3 state:Florida` |
</details>

---

</details>
### Metadata

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


| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `device` | Restricts search results to systems that Shodan has identified as a particular *kind of device*. | `device:voip` | `shodan search --limit 3 device:voip` |
| `hash` | Used to locate files, firmware, or data that match a specific cryptographic hash. | `hash:"d41d8cd98f00b204e9800998ecf8427e"` | `shodan search --limit 3 hash:"d41d8cd98f00b204e9800998ecf8427e"` |
| `os` | Search for hosts based on their *operating system*. | `os:"Windows 7"` | `shodan search --limit 3 os:"Windows 7` |
| `product` | Find hosts running a *specific software product, service, or application*. | `product:Redis` | `shodan search --limit 3 product:Redis` |
| `version` | find hosts running a *specific version of a software product or service*. | `version:"2.4.49"` | `shodan search --limit 3 version:"2.4.49"` |

<details>

<summary>Screenshots</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `has_screenshot` | Limit results to hosts for which Shodan has captured a *web interface screenshot*. | `has_screenshot:true` | `shodan search --limit 3 has_screenshot:true` |
| `screenshot.hash` | Find devices whose visual appearance (as captured in Shodan’s automatic screenshots) matches a specific image hash. | `screenshot.hash:1437554350` | `shodan search --limit 3 screenshot.hash:1437554350` |
| `screenshot.label` | Is used to filter devices or hosts based on labels detected in their screenshots. | `screenshot.label:ics` | `shodan search --limit 3 screenshot.label:ics` |

</details>

<details>

<summary>Cloud</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `cloud.provider` | Used to search for devices, services, or hosts that are running on a specific cloud provider. | `cloud.provider:"Amazon"` | `shodan search --limit 3 cloud.provider:"Amazon"` |
| `cloud.region` | Used to search for hosts that are located in a specific geographic region within a cloud provider’s infrastructure. | `cloud.region:"us-east-1"` | `shodan search --limit 3 cloud.region:"us-east-1"` |
| `cloud.service` | Search for hosts that Shodan has identified as running on a *specific cloud service offering*, such as a managed service or infrastructure product provided by a cloud vendor. | `cloud.service:"Cloudflare"` | `shodan search --limit 3 cloud.service:"Cloudflare"` |

</details>

<details>

<summary>HTTP</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `http.component` | Search for web servers whose *HTML content, scripts, assets, or metadata indicate they are using a specific software component*. | `http.component:"wordpress"` | `shodan search --limit 3 http.component:"wordpress"` |
| `http.component_category` | Search for web servers based on the category of web technologies detected in their HTTP responses. | `http.component_category:"wordpress"` | `shodan search --limit 3 http.component_category:"wordpress"` |
| `http.dom_hash` | search for web servers based on the *hash of their HTML DOM (Document Object Model)*. This is useful for detecting *identical or very similar web pages*, even if other metadata like headers or IPs differ. | `http.dom_hash:"abcd1234efgh5678"` | `shodan search --limit 3 http.dom_hash:"abcd1234efgh5678"` |
| `http.favicon.hash` | Search for web servers based on the hash of their favicon. | `http.favicon.hash:1234567890` | `shodan search --limit 3 http.favicon.hash:1234567890` |
| `http.headers_hash` | Search for web servers based on a *hash of their HTTP headers*. Instead of looking at the content of the web page or favicon, this filter focuses on the structure and values of the HTTP headers returned by the server. | `http.headers_hash:987654321` | `shodan search --limit 3 http.headers_hash:987654321` |
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
