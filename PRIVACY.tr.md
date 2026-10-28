# IT-ToolZ — Gizlilik Politikası

<p align="right"><a href="PRIVACY.md">English</a> · <b>Türkçe</b> · <a href="README.tr.md">IT-ToolZ</a></p>

**İletişim:** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Yürürlük tarihi:** 28 Ekim 2026

## 1. Uygulama hakkında
IT-ToolZ, BT ve ağ uzmanları için bir araç setidir. Ağ teşhis araçları (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), yerel ağ araçları (Wake-on-LAN, LAN Device Discovery), çevrimdışı hesaplama ve dönüştürme araçları (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, metin için Hash Generator, Password Generator) sunar ve mevcut ağ bağlantınızla ilgili bilgileri gösterir ("Ağ Bilgilerim").

IT-ToolZ'de kullanıcı hesabı, analitik, çökme raporlama, reklam ve kendi sunucusu yoktur. **Yayıncı, uygulamadan hiçbir veri almaz.**

## 2. Cihazınızda saklanan veriler
- Ağ araçlarının **geçmişi** (örneğin kontrol ettiğiniz host, sonuç durumu ve zaman; Wake-on-LAN için girdiğiniz MAC adresi; LAN Device Discovery için yalnızca taranan aralık ve bulunan cihaz sayısı), **favoriler** (hangi araçlar ve sıraları) ve **ayarlar** (dil, tema, Password Generator seçenekleri) yalnızca cihazınızdaki uygulamaya özel depolama alanında saklanır.
- Geçmiş hiçbir zaman parola, token, çerez, URL içindeki kimlik bilgisi veya URL sorgu dizesi içermez. Password Generator, Hash Generator, Base64, URL Encoder/Decoder ve JSON Formatter geçmişe hiçbir şey yazmaz.
- "Ağ Bilgilerim" sayfasında gösterilen bilgiler ve genel IP sonuçları saklanmaz.
- **Yedekleme:** Uygulama verileri Android bulut yedeklemesinden ve cihazdan cihaza aktarımdan hariç tutulur; yalnızca bu cihazda kalır.
- **Verilerinizi silme:** Tek bir geçmiş kaydını (uzun basarak) veya tüm geçmişi (Ayarlar > Veri > Geçmişi temizle) silebilirsiniz. Android ayarlarından uygulama verilerini temizlemek veya uygulamayı kaldırmak tüm verilerini siler. Yayıncıda hiçbir kopya bulunmadığından silinecek başka veri yoktur.

## 3. Ağ üzerinden gönderilen veriler
Uygulama internete yalnızca bir ağ aracını başlattığınızda veya bunu isteyen bir düğmeye bastığınızda bağlanır.

- **Seçtiğiniz hedefler.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker ve HTTP Headers, girdiğiniz host'a, adrese veya URL'ye bağlanır (HTTP Headers yönlendirmeleri de izler). Her internet bağlantısında olduğu gibi bu hedef cihazınızın IP adresini görür; Traceroute'ta yol üzerindeki yönlendiriciler de deneme paketlerini görür. SSL Certificate Checker, TLS el sıkışması sırasında yalnızca host adını gönderir. HTTP Headers her adrese çerez veya oturum bilgisi olmadan bir istek gönderir; düz `http://` adresleri şifrelenmez.
- **Yerel ağınız.** Wake-on-LAN, girdiğiniz MAC adresini içeren bir "magic packet"i (UDP) seçtiğiniz adrese, genellikle yerel ağınıza gönderir. LAN Device Discovery yalnızca seçtiğiniz yerel ağ aralığını (yalnızca özel adres aralıkları) ICMP echo ve TCP bağlantı denemeleriyle tarar ve cihaz adlarını DNS çözümleyicinize sorar. Cihaz listeleri ekranda gösterilir; saklanmaz ve hiçbir yere gönderilmez.
- **DNS.** DNS Lookup ve Reverse DNS, girdiğiniz adı veya adresi cihazınızın DNS çözümleyicisine (ağınızın DNS sunucusu, Özel DNS sağlayıcınız veya VPN'iniz) gönderir. Özel DNS etkin değilse DNS sorguları genellikle şifrelenmez. DNS Lookup'ta bunun yerine DNS sunucusunu kendiniz seçebilirsiniz (Cloudflare'in 1.1.1.1'i, Google'ın 8.8.8.8'i veya sizin girdiğiniz bir adres): sorgu o zaman doğrudan bu sunucuya, 53 numaralı porttan şifresiz gider; Özel DNS'i ve cihazınızın DNS ayarlarını atlar. Uygulama son seçiminizi yalnızca cihazda hatırlar.
- **RDAP/WHOIS.** Alan adı sorgularında uygulama IANA'dan (data.iana.org) herkese açık listeleri indirir (bu istekler sorgunuzu içermez), ardından o alan adından sorumlu kayıt kuruluşuna (örneğin Verisign) sorar. IP adresi sorgularında uygulama üçüncü taraf **ipwho.is** servisine sorar; bu servis adresin yaklaşık konumunu ve ağ sağlayıcısını döndürür. Kayıt kuruluşu veya ipwho.is sorgunuzu ve IP adresinizi alır. Özel ve yerel adresler (örneğin 192.168.x.x) asla gönderilmez.
- **Genel IP.** Genel IP adresinizi ağ sağlayıcısı ve yaklaşık konumuyla birlikte göstermek için uygulama üçüncü taraf **ipwho.is** servisine sorar. Yalnızca ipwho.is'e ulaşılamazsa aynı anda iki başka üçüncü taraf servise sorar: **ipify** (api.ipify.org, api6.ipify.org) ve **ifconfig.me**. Sorulan her servis genel IP adresinizi alır; yer adları için uygulama dili dışında başka veri gönderilmez. Bu yalnızca Public IP aracında veya "Ağ Bilgilerim" sayfasında düğmeye bastığınızda olur. Bir IP adresi için gösterilen yaklaşık koordinatlara dokunursanız bunlar cihazınızın harita uygulamasına (iPhone'da Apple Haritalar) aktarılır; uygulamanın kendisi bir şey göndermez.

Bu hedefler üçüncü taraflarca işletilir ve istekleri kendi gizlilik politikalarına göre işler. Uygulama IP adresinizi konumunuzu belirlemek için kullanmaz.

## 4. İzinler
- **İnternet, ağ durumu** — ağ araçlarını çalıştırmak ve mevcut bağlantınızı göstermek için.
- **Wi-Fi durumu** — "Ağ Bilgilerim"de Wi-Fi frekansını, sinyal gücünü ve bağlantı hızını göstermek için.
- **Yerel ağ (iOS)** — iOS, uygulamanın yerel ağınızdaki cihazlara erişmesinden (Wake-on-LAN) önce izin ister. Yalnızca başlattığınız araç için kullanılır.
- **Konum (isteğe bağlı)** — Android, bağlı Wi-Fi ağının adını (SSID/BSSID) yalnızca hassas konum erişimi olan uygulamalara gösterir. IT-ToolZ bu izni yalnızca "Ağ Bilgilerim"deki düğmeye dokunduğunuzda ister. Ağ adı ekranda gösterilir; saklanmaz ve gönderilmez. Uygulama konumunuzu hiçbir zaman okumaz. Diğer her şey bu izin olmadan çalışır.

Uygulama telefon numaranıza, kişilerinize, mesajlarınıza, dosyalarınıza, kameranıza veya mikrofonunuza erişmez; SIM veya cihaz kimliklerini (IMSI, ICCID, IMEI) okumaz.

## 5. Pano
Bir değeri kopyaladığınızda cihazınızın panosuna yerleştirilir; diğer uygulamalar veya klavyeniz onu okuyabilir. Password Generator'dan kopyalanan parolalar hassas olarak işaretlenir; böylece Android 13 ve sonrası onları pano önizlemesinde gizler. "Panoyu temizle", kopyalanan parolayı yalnızca hâlâ panodaki içerikse kaldırır; sonradan kopyaladığınız içeriğe dokunulmaz. Uygulama pano içeriğinizi okumaz.

## 6. Password Generator
Parolalar cihazınızda, sistemin güvenli rastgele sayı kaynağıyla üretilir. Hiçbir zaman saklanmaz, günlüğe yazılmaz, gönderilmez ve geçmişe yazılmaz. Password Generator açıkken Android ekran görüntüsünü ve ekran kaydını engeller, son uygulamalar görünümünde ekranı gizler.

## 7. Çocuklar
IT-ToolZ profesyonel bir araçtır ve çocuklara yönelik değildir.

## 8. Değişiklikler
Bu politika değişirse yeni sürüm, yeni bir yürürlük tarihiyle bu adreste yayınlanır.

## 9. İletişim
Bu politika hakkındaki sorularınız için lütfen [GitHub'da bir issue açın](https://github.com/buadamlaz/it-toolz/issues). Destek e-posta adresi uygulamada da Ayarlar → İletişim ve Destek altında yer alır.
