### What is Shodan?

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
### Search Query Cheat Sheets

To get the most out of Shodan it's important to understand the search query syntax. Below are the Cheat Sheets used for different categories:

<details>

<summary>General Search</summary>

| Name | Description | Browser Example | Console Example |
| :---: | :---: | :---: | :---: |
| `after` | Only show results after the given date (dd/mm/yyyy) string. | | `shodan search apache --limit 3 after:2025-10-1` |
| `asn` | Autonomous system number string. | `asn:AS13335` | `shodan search --limit 3 asn:AS13335` |
| `before` | Only show results before the given date (dd/mm/yyyy) string. | | `shodan search apache --limit 3 before:2025-10-1` |
| `city` | Name of the city string. |  `city:Chisinau` | `shodan search apache --limit 3 city:Chisinau` |
| `country` | 2-letter country code string. | `country:MD` | `shodan search apache --limit 3 country:MD,city:Chisinau` |
| `geo` | Accepts between 2 and 4 parameters. If 2 parameters: latitude,longitude. If 3 parameters: latitude,longitude,range. If 4 parameters: top left latitude, top left longitude, bottom right latitude, bottom right longitude. | `geo:47.06146704730932,28.86888084378684,10` | `shodan search --limit 10 geo:47.06146704730932,28.86888084378684,10` |
| `hash` | Hash of the data property integer. | `hash:-82460412` | `shodan search --limit 10 hash:-82460412` |
| `has_ipv6` | True/False boolean. | `has_ipv6:true` | `shodan search --limit 10 country:MD has_ipv6:true` |
| `has_screenshot` | True/False boolean. | `has_screenshot:true` | `shodan search --limit 10 country:MD has_screenshot:true` |
| `hostname` | Full hostname for the device string. | `shodan search --limit 10 country:MD hostname:mivocloud` |
| `ip` | Alias for net filter string. | `ip:104.16.0.0/12` | `shodan search --limit 10 ip:104.16.0.0/12` |
| `isp` | ISP managing the netblocking string. | `isp:StarNet isp:Solutii isp:SRL` | `shodan search --limit 10 isp:StarNet isp:Solutii isp:SRL` |
| `net` | Network range in CIDR notation (ex. 199.4.1.0/24) string. | `net:104.16.0.0/12` | `shodan search --limit 10 net:104.16.0.0/12` |
| `org` | Organization assigned the netblock string. | `org:Cloudflare org:Inc` | `shodan search --limit 10 org:Cloudflare org:Inc` |
| `os` | Operating system string. | `ssh os:linux` | `shodan search ssh --limit 10 os:linux` |
| `port` | Port number for the service integer. | `port:80` | `shodan search --limit 10 port:80` |
| `product` | Name of the software/ product providing the banner string. | `product:ssh` | `shodan search --limit 10 product:ssh` |
| `region` | Name of the region/ state (US only) string. | `region:NY` | `shodan search --limit 10 region:NY` |
| `state` | Alias for region string. | `state:California` | `shodan search --limit 10 state:California` |
| `version` | Version for the product string. | `product:apache version:2.4.6` | `shodan search --limit 10 country:MD product:apache version:2.4.6` | 

</details>

As reference was used:
- [Shodan Filter Reference]()
- [Advanced Shodan Search Filter](https://www.shodan.io/search/advanced)
- [External Links](https://github.com/JavierOlmedo/shodan-filters?utm_source=chatgpt.com)
