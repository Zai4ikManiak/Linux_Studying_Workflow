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
# Search Query Cheat Sheets

To get the most out of Shodan it's important to understand the search query syntax. Below are the Cheat Sheets used for different categories:

<details>

<summary>General Search</summary>

### Network Search Filters

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `asn` | Restricts your Shodan search results to hosts whose IP addresses fall within the AS you specify. | `asn:AS13335` | `shodan search --limit 3 asn:AS13335` |
| `has_ipv6` | Identifies devices or services that are reachable via IPv6 rather than (or in addition to) IPv4. | `has_ipv6:true` | `shodan search --limit 3 has_ipv6:true` |
| `hostname` | Search for devices or hosts by their *DNS hostname*. | `hostname:"example.com"` | `shodan search --limit 3 hostname:"example.com"` |
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

---

</details>

<details>

<summary>Screenshots</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `has_screenshot` | Limit results to hosts for which Shodan has captured a *web interface screenshot*. | `has_screenshot:true` | `shodan search --limit 3 has_screenshot:true` |
| `screenshot.hash` | Find devices whose visual appearance (as captured in Shodan’s automatic screenshots) matches a specific image hash. | `screenshot.hash:1437554350` | `shodan search --limit 3 screenshot.hash:1437554350` |
| `screenshot.label` | Is used to filter devices or hosts based on labels detected in their screenshots. | `screenshot.label:ics` | `shodan search --limit 3 screenshot.label:ics` |

---

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
