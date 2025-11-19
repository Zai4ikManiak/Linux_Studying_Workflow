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

---
### Location

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `city` | Returns only hosts that Shodan has geolocated to the specified city. | `city:"New York"` | `shodan search --limit 3 city:"New York"` |
| `country` | Restricts search results to hosts that Shodan identifies as being in the specified country, using the *two-letter ISO country code*. | `country:US` | `shodan search --limit 3 country:US` |
| `geo` | Restricts results to hosts located within a radius of a given latitude/longitude point. `geo:<latitude>,<longitude>,<radius_in_km>` | `geo:47.06181007599137,28.868065103036265` | `shodan search --limit 3 geo:47.06181007599137,28.868065103036265` |


---
### Metadata

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `cpe` | Filters Shodan results to devices that report a specific software/hardware platform. | `cpe:"cpe:2.3:o:microsoft:windows_10"` | `shodan search --limit 3 cpe:"cpe:2.3:o:microsoft:windows_10"` |
| `device` | Restricts search results to systems that Shodan has identified as a particular *kind of device*. | `device:voip` | `shodan search --limit 3 device:voip` |
| `hash` | Used to locate files, firmware, or data that match a specific cryptographic hash. | `hash:"d41d8cd98f00b204e9800998ecf8427e"` | `shodan search --limit 3 hash:"d41d8cd98f00b204e9800998ecf8427e"` |

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
### Screenshot

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `has_screenshot` | Limit results to hosts for which Shodan has captured a *web interface screenshot*. | `has_screenshot:true` | `shodan search --limit 3 has_screenshot:true` |

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


</details>

As reference was used:
- [Shodan Filter Reference]()
- [Advanced Shodan Search Filter](https://www.shodan.io/search/advanced)
- [External Links](https://github.com/JavierOlmedo/shodan-filters?utm_source=chatgpt.com)
