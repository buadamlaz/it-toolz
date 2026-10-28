# Değişiklik günlüğü

IT-ToolZ'daki kullanıcıya dönük değişiklikler. En yeni en üstte. Tarihler ISO biçimindedir (YYYY-AA-GG).

English: [CHANGELOG.md](CHANGELOG.md)

## 1.0.1 — 2026-10-28 (Google Play'de kapalı test)

### Yeni
- **DNS Lookup: DNS sunucusu seçimi.** Cihazınızın DNS'ine (varsayılan), **1.1.1.1**'e, **8.8.8.8**'e veya sizin girdiğiniz bir sunucu IP adresine sorun; `nslookup example.com 1.1.1.1` gibi. Sonuç hangi sunucunun yanıt verdiğini ve UDP mi TCP mi kullanıldığını gösterir. Son seçiminiz cihazda hatırlanır.
- **Public IP ve RDAP/WHOIS: koordinatları harita uygulamasında açma.** Koordinatlara (veya yanındaki konum simgesine) dokunarak yaklaşık konumu cihazınızın harita uygulamasında görün; iPhone'da Apple Haritalar'da.

### Değişen
- **IP bilgi tabloları** (ağ, konum, saat dilimi): başlıklar solda, değerler sağa hizalı; servis sağlayıcı adı gibi uzun değerler sağ tarafta düzgünce alt satıra geçer.

## 1.0.0 — 2026-10-22

İlk sürüm.

- 19 araç: Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check (TCP ve UDP), Subnet Calculator, IP Converter, Public IP, NTP Time Checker, Wake-on-LAN, LAN Device Discovery, SSL Certificate Checker, RDAP/WHOIS, Password Generator, HTTP Headers, Hash Generator, Base64, URL Encoder/Decoder ve JSON Formatter.
- Ağ Bilgilerim sayfası, favoriler, yeniden çalıştırılabilen geçmiş.
- Açık, koyu ve sistem teması; 7 dil.
