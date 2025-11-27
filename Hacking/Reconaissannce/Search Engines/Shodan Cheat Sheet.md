# What is Shodan?

Shodan is a search engine for Internet-connected devices.

IT gathers information about all devices directly connected to the Internet. If a device is directly hooked up to the Internet then Shodan queries it for various publicly-available information. The types of devices that are indexed can vary tremendously: ranging from small desktops up to nuclear power plants and everything in between.

So what does Shodan index then? The bulk of the data is taken from banners, which are metadata about a software that's running on a device. This can be information about the server software, what options the service supports, a welcome message or anything else that the client would like to know before interacting with the server.

The information gained from these services is applied to many areas:
- **Network Security**:
	>keep an eye on all devices at your company that are facing the Internet.
- **Market Research**:
	>find out which products people are using in the real-world.
- **Cyber Risk**:
	>include the online exposure of your vendors as a risk metric.
- **Internet of Things**:
	>track the growing usage of smart devices.
- **Tracking Ransomware**:
	>measure how many devices have been impacted by ransomware.

---
# Advanced Search Filters

To get the most out of Shodan it's important to understand the search query syntax. Below are the Cheat Sheets used for different categories:

<details>

<summary>General Search</summary>

### Network Search Filters

<details>

<summary><strong>asn:</strong> <em>Search results to hosts whose IP addresses fall within the AS you specify.</em></summary>

---
**Examples:**
- Browser Example:
	> `asn:AS13335`
- Command Line Example:	
	> `shodan search --limit 3 asn:AS13335`
---
</details>
<details>

<summary><strong>has_ipv6:</strong> <em>Identifies devices or services that are <u>reachable via IPv6 rather than (or in addition to) IPv4</u>.</em></summary>

---
**Example:**
- Browser Example:
	> `has_ipv6:true`
- Command Line Example:
	> `shodan search --limit 3 has_ipv6:true`
---
</details>
<details>

<summary><strong>hostname:</strong> <em>Search for devices or hosts by their <ins>DNS hostname</ins>.</em></summary>

---
**Example:**
- Browser Example:
	> `hostname:"example.com"`
- Command Line Example:
	> `shodan search --limit 3 hostname:"example.com"`
---
</details>


| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `ip` | Search for a specific IP address. | `ip:104.21.7.138` | `shodan search --limit 3 ip:104.21.7.138` |
| `isp` | Search for hosts or devices based on their Internet Service Provider (ISP). | `isp:"Amazon.com"` | `shodan search --limit 3 isp:"Amazon.com"` |
| `net` | Search for hosts within a *specific IP network or range*, using *CIDR notation*. | `net:5.252.178.0/24` | `shodan search --limit 3 net:5.252.178.0/24` |
| `org` | Search for hosts based on the *organization* that owns or is assigned the IP address. | `org:"Amazon.com"` | `shodan search --limit 3 org:"Amazon.com"` |
| `port` | Find hosts that have a *specific network port open*. | `port:80,443` | `shodan search --limit 3 port:80,443` |

---
### Location

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `city` | Returns only hosts that Shodan has geolocated to the specified city. | `city:"New York"` | `shodan search --limit 3 city:"New York"` |
| `country` | Restricts search results to hosts that Shodan identifies as being in the specified country, using the *two-letter ISO country code*. | `country:US` | `shodan search --limit 3 country:US` |
| `geo` | Restricts results to hosts located within a radius of a given latitude/longitude point. `geo:<latitude>,<longitude>,<radius_in_km>` | `geo:47.06181007599137,28.868065103036265` | `shodan search --limit 3 geo:47.06181007599137,28.868065103036265` |
| `postal` | Search for hosts based on their *postal code (ZIP code)*. | `postal:75001` | `shodan search --limit 3 postal:75001` |
| `region` | Search for hosts based on a *geographical region, state, or province*. | `region:"New York"` | `shodan search --limit 3 region:"New York"` |
| `state` | Filter hosts based on the *state, province, or administrative region* associated with their IP address. It is similar to the region filter, though Shodan sometimes uses state for certain countries (like the U.S.) where “state” is the standard administrative unit. | `state:"New York"` | `shodan search --limit 3 state:"New York"` |

---
### Metadata

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `cpe` | Filters Shodan results to devices that report a specific software/hardware platform. | `cpe:"cpe:2.3:o:microsoft:windows_10"` | `shodan search --limit 3 cpe:"cpe:2.3:o:microsoft:windows_10"` |
| `device` | Restricts search results to systems that Shodan has identified as a particular *kind of device*. | `device:voip` | `shodan search --limit 3 device:voip` |
| `hash` | Used to locate files, firmware, or data that match a specific cryptographic hash. | `hash:"d41d8cd98f00b204e9800998ecf8427e"` | `shodan search --limit 3 hash:"d41d8cd98f00b204e9800998ecf8427e"` |
| `os` | Search for hosts based on their *operating system*. | `os:"Windows 7"` | `shodan search --limit 3 os:"Windows 7` |
| `product` | Find hosts running a *specific software product, service, or application*. | `product:Redis` | `shodan search --limit 3 product:Redis` |
| `version` | find hosts running a *specific version of a software product or service*. | `version:"2.4.49"` | `shodan search --limit 3 version:"2.4.49"` |

| Common device types |
| :--: |
| `router` |
| `webcam` |
| `switch` |
| `firewall` |
| `pbx` |
| `storage` |
| `printer` |
| `ics` |
| `voip` |
| `nas` |
| `vpn` |

</details>

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
