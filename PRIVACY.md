# IT-ToolZ — Privacy Policy

<p align="right"><b>English</b> · <a href="PRIVACY.tr.md">Türkçe</a> · <a href="README.md">IT-ToolZ</a></p>

**Contact:** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Effective date:** 28 October 2026

## 1. About the app
IT-ToolZ is a toolkit for IT and network professionals. It runs network diagnostics (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), local network tools (Wake-on-LAN, LAN Device Discovery), offline calculators and converters (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, Hash Generator for text, Password Generator) and shows information about your current network connection ("My Network").

IT-ToolZ has no user accounts, no analytics, no crash reporting, no advertising and no server of its own. **The publisher does not receive any data from the app.**

## 2. Data stored on your device
- **History** of network tool runs (for example the host you checked, the result status and the time; for Wake-on-LAN the MAC address you entered; for LAN Device Discovery only the scanned range and the number of devices found), **favorites** (which tools and their order) and **settings** (language, theme, Password Generator options) are stored only in the app's private storage on your device.
- History never contains passwords, tokens, cookies, credentials in URLs or URL query strings. The Password Generator, Hash Generator, Base64, URL Encoder/Decoder and JSON Formatter never write anything to history.
- Information shown on the "My Network" page and Public IP results are not stored.
- **Backups:** app data is excluded from Android cloud backup and from device-to-device transfer. It stays on this device only.
- **Deleting your data:** you can delete a single history entry (long-press it) or all history (Settings > Data > Clear history). Clearing the app's data in Android settings or uninstalling the app removes all of its data. Because the publisher holds no copy, there is nothing else to delete.

## 3. Data sent over the network
The app contacts the internet only when you start a network tool or press a button that asks for it.

- **Destinations you choose.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker and HTTP Headers connect to the host, address or URL you enter (HTTP Headers also follows its redirects). Like any internet connection, that destination sees your device's IP address; for Traceroute, the routers along the path see the probe packets as well. SSL Certificate Checker sends the host name during the TLS handshake and no other data. HTTP Headers sends one request per address without cookies or login data; plain `http://` addresses are not encrypted.
- **Your local network.** Wake-on-LAN sends a "magic packet" (UDP) containing the MAC address you enter to the address you choose, usually your local network. LAN Device Discovery scans only the local network range you choose (private address ranges only) with ICMP echo and TCP connection attempts, and asks your DNS resolver for device names. Device lists are shown on screen and are not stored or sent anywhere.
- **DNS.** DNS Lookup and Reverse DNS send the name or address you enter to your device's DNS resolver (your network's DNS server, your Private DNS provider or your VPN). DNS queries are usually not encrypted unless Private DNS is active. In DNS Lookup you can instead choose a DNS server yourself (1.1.1.1 by Cloudflare, 8.8.8.8 by Google, or an address you enter): the query then goes directly to that server over port 53, unencrypted, and bypasses Private DNS and your device's DNS settings. The app remembers your last choice on the device only.
- **RDAP/WHOIS.** For a domain name, the app downloads public lists from IANA (data.iana.org; these requests contain no query) and then asks the registry responsible for that domain (for example Verisign). For an IP address, the app asks the third-party service **ipwho.is**, which returns the address's approximate location and network provider. The registry or ipwho.is receives your query and your IP address. Private and local addresses (for example 192.168.x.x) are never sent.
- **Public IP.** To show your public IP address with its network provider and approximate location, the app asks the third-party service **ipwho.is**. Only if ipwho.is cannot be reached does the app ask two other third-party services at the same time: **ipify** (api.ipify.org, api6.ipify.org) and **ifconfig.me**. Each service asked receives your public IP address; no other data is sent besides the app language (for place names). This happens only when you press the button in the Public IP tool or on the "My Network" page. If you tap the approximate coordinates shown for an IP address, they are handed to the maps app of your device (on iPhone, Apple Maps); the app itself sends nothing.

These destinations are operated by third parties and handle requests under their own privacy policies. The app does not use your IP address to determine your location.

## 4. Permissions
- **Internet, network state** — to run network tools and to show your current connection.
- **Wi-Fi state** — to show Wi-Fi frequency, signal strength and link speed on "My Network".
- **Local network (iOS)** — iOS asks for permission before the app may reach devices on your local network (Wake-on-LAN). It is used only for the tool you start.
- **Location (optional)** — Android shows the name of the connected Wi-Fi network (SSID/BSSID) only to apps with precise location access. IT-ToolZ asks for it only when you tap the button on "My Network". The network name is shown on screen and never stored or sent. The app never reads your location. Everything else works without this permission.

The app does not access your phone number, contacts, messages, files, camera or microphone, and does not read SIM or device identifiers (IMSI, ICCID, IMEI).

## 5. Clipboard
When you copy a value, it is placed on your device's clipboard, where other apps or your keyboard may be able to read it. Passwords copied from the Password Generator are marked as sensitive, so Android 13 and later hide them in the clipboard preview. "Clear clipboard" removes the copied password only if it is still the current clipboard content; anything you copied later is left untouched. The app does not read your clipboard content.

## 6. Password Generator
Passwords are generated on your device with the system's secure random source. They are never stored, logged, sent or written to history. While the Password Generator is open, Android blocks screenshots and screen recordings of it and hides it in the recent apps view.

## 7. Children
IT-ToolZ is a professional tool and is not directed at children.

## 8. Changes
If this policy changes, the new version will be published at this address with a new effective date.

## 9. Contact
Questions about this policy: please [open an issue on GitHub](https://github.com/buadamlaz/it-toolz/issues). The support e-mail address is also shown in the app under Settings → Contact & Support.
