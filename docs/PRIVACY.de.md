# IT-ToolZ — Datenschutzerklärung

<p align="right"><a href="../PRIVACY.md">English</a> · <a href="PRIVACY.tr.md">Türkçe</a> · <b>Deutsch</b> · <a href="PRIVACY.es.md">Español</a> · <a href="PRIVACY.pt-BR.md">Português (Brasil)</a> · <a href="PRIVACY.fr.md">Français</a> · <a href="PRIVACY.ru.md">Русский</a> · <a href="README.de.md">IT-ToolZ</a></p>

**Kontakt:** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Gültig ab:** 28. Oktober 2026

*Diese Übersetzung dient dem besseren Verständnis. Maßgeblich ist die [englische Fassung](../PRIVACY.md).*

## 1. Über die App
IT-ToolZ ist ein Werkzeugset für IT- und Netzwerkprofis. Die App führt Netzwerkdiagnosen durch (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), bietet Tools für das lokale Netzwerk (Wake-on-LAN, LAN Device Discovery), Offline-Rechner und -Konverter (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, Hash Generator für Text, Password Generator) und zeigt Informationen zu Ihrer aktuellen Netzwerkverbindung („Mein Netzwerk“).

IT-ToolZ hat keine Benutzerkonten, keine Analyse, keine Absturzberichte, keine Werbung und keinen eigenen Server. **Der Herausgeber erhält keinerlei Daten aus der App.**

## 2. Auf Ihrem Gerät gespeicherte Daten
- Der **Verlauf** der Netzwerk-Tools (zum Beispiel der geprüfte Host, der Ergebnisstatus und die Uhrzeit; bei Wake-on-LAN die eingegebene MAC-Adresse; bei LAN Device Discovery nur der gescannte Bereich und die Anzahl der gefundenen Geräte), **Favoriten** (welche Tools und in welcher Reihenfolge) und **Einstellungen** (Sprache, Design, Optionen des Password Generator) werden ausschließlich im privaten Speicher der App auf Ihrem Gerät abgelegt.
- Der Verlauf enthält niemals Passwörter, Tokens, Cookies, Zugangsdaten in URLs oder URL-Abfrageparameter. Password Generator, Hash Generator, Base64, URL Encoder/Decoder und JSON Formatter schreiben nie etwas in den Verlauf.
- Die Informationen auf der Seite „Mein Netzwerk“ und die Ergebnisse von Public IP werden nicht gespeichert.
- **Backups:** App-Daten sind von der Android-Cloud-Sicherung und der Übertragung von Gerät zu Gerät ausgeschlossen. Sie bleiben nur auf diesem Gerät.
- **Löschen Ihrer Daten:** Sie können einen einzelnen Verlaufseintrag (lange drücken) oder den gesamten Verlauf (Einstellungen > Daten > Verlauf löschen) löschen. Wenn Sie die App-Daten in den Android-Einstellungen löschen oder die App deinstallieren, werden alle ihre Daten entfernt. Da der Herausgeber keine Kopie besitzt, gibt es nichts weiter zu löschen.

## 3. Über das Netzwerk gesendete Daten
Die App verbindet sich nur dann mit dem Internet, wenn Sie ein Netzwerk-Tool starten oder eine Schaltfläche drücken, die dies anfordert.

- **Von Ihnen gewählte Ziele.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker und HTTP Headers verbinden sich mit dem Host, der Adresse oder der URL, die Sie eingeben (HTTP Headers folgt auch Weiterleitungen). Wie bei jeder Internetverbindung sieht dieses Ziel die IP-Adresse Ihres Geräts; bei Traceroute sehen zusätzlich die Router entlang des Pfades die Testpakete. SSL Certificate Checker sendet während des TLS-Handshakes nur den Hostnamen und keine weiteren Daten. HTTP Headers sendet pro Adresse eine Anfrage ohne Cookies oder Anmeldedaten; einfache `http://`-Adressen sind nicht verschlüsselt.
- **Ihr lokales Netzwerk.** Wake-on-LAN sendet ein „Magic Packet“ (UDP) mit der eingegebenen MAC-Adresse an die von Ihnen gewählte Adresse, in der Regel in Ihrem lokalen Netzwerk. LAN Device Discovery scannt nur den von Ihnen gewählten lokalen Netzwerkbereich (nur private Adressbereiche) mit ICMP Echo und TCP-Verbindungsversuchen und fragt Ihren DNS-Resolver nach Gerätenamen. Gerätelisten werden auf dem Bildschirm angezeigt und weder gespeichert noch irgendwohin gesendet.
- **DNS.** DNS Lookup und Reverse DNS senden den eingegebenen Namen oder die Adresse an den DNS-Resolver Ihres Geräts (den DNS-Server Ihres Netzwerks, Ihren Anbieter für privates DNS oder Ihr VPN). DNS-Anfragen sind in der Regel unverschlüsselt, sofern privates DNS nicht aktiv ist. In DNS Lookup können Sie stattdessen selbst einen DNS-Server wählen (1.1.1.1 von Cloudflare, 8.8.8.8 von Google oder eine eigene Adresse): Die Anfrage geht dann direkt und unverschlüsselt über Port 53 an diesen Server und umgeht privates DNS und die DNS-Einstellungen Ihres Geräts. Die App merkt sich Ihre letzte Wahl nur auf dem Gerät.
- **RDAP/WHOIS.** Bei einem Domainnamen lädt die App öffentliche Listen von der IANA (data.iana.org; diese Anfragen enthalten keine Abfrage) und fragt dann die für diese Domain zuständige Registry (zum Beispiel Verisign). Bei einer IP-Adresse fragt die App den Drittanbieterdienst **ipwho.is**, der den ungefähren Standort und den Netzbetreiber der Adresse liefert. Die Registry bzw. ipwho.is erhält Ihre Abfrage und Ihre IP-Adresse. Private und lokale Adressen (zum Beispiel 192.168.x.x) werden nie gesendet.
- **Public IP.** Um Ihre öffentliche IP-Adresse mit Netzbetreiber und ungefährem Standort anzuzeigen, fragt die App den Drittanbieterdienst **ipwho.is**. Nur wenn ipwho.is nicht erreichbar ist, fragt die App gleichzeitig zwei andere Drittanbieterdienste: **ipify** (api.ipify.org, api6.ipify.org) und **ifconfig.me**. Jeder angefragte Dienst erhält Ihre öffentliche IP-Adresse; außer der App-Sprache (für Ortsnamen) werden keine weiteren Daten gesendet. Das geschieht nur, wenn Sie im Tool Public IP oder auf der Seite „Mein Netzwerk“ die Schaltfläche drücken. Wenn Sie auf die ungefähren Koordinaten einer IP-Adresse tippen, werden sie an die Karten-App Ihres Geräts übergeben (auf dem iPhone Apple Karten); die App selbst sendet nichts.

Diese Ziele werden von Dritten betrieben und verarbeiten Anfragen nach ihren eigenen Datenschutzrichtlinien. Die App verwendet Ihre IP-Adresse nicht, um Ihren Standort zu bestimmen.

## 4. Berechtigungen
- **Internet, Netzwerkstatus** — um Netzwerk-Tools auszuführen und Ihre aktuelle Verbindung anzuzeigen.
- **WLAN-Status** — um auf „Mein Netzwerk“ WLAN-Frequenz, Signalstärke und Verbindungsgeschwindigkeit anzuzeigen.
- **Lokales Netzwerk (iOS)** — iOS fragt um Erlaubnis, bevor die App Geräte in Ihrem lokalen Netzwerk erreichen darf (Wake-on-LAN). Sie wird nur für das Tool verwendet, das Sie starten.
- **Standort (optional)** — Android zeigt den Namen des verbundenen WLANs (SSID/BSSID) nur Apps mit Zugriff auf den genauen Standort. IT-ToolZ fragt diese Berechtigung nur an, wenn Sie auf „Mein Netzwerk“ die Schaltfläche antippen. Der Netzwerkname wird auf dem Bildschirm angezeigt und nie gespeichert oder gesendet. Die App liest Ihren Standort nie aus. Alles andere funktioniert ohne diese Berechtigung.

Die App greift nicht auf Ihre Telefonnummer, Kontakte, Nachrichten, Dateien, Kamera oder Ihr Mikrofon zu und liest keine SIM- oder Gerätekennungen (IMSI, ICCID, IMEI).

## 5. Zwischenablage
Wenn Sie einen Wert kopieren, wird er in die Zwischenablage Ihres Geräts gelegt, wo andere Apps oder Ihre Tastatur ihn möglicherweise lesen können. Aus dem Password Generator kopierte Passwörter werden als vertraulich markiert, sodass Android 13 und neuer sie in der Vorschau der Zwischenablage ausblendet. „Zwischenablage leeren“ entfernt das kopierte Passwort nur, wenn es noch der aktuelle Inhalt der Zwischenablage ist; später Kopiertes bleibt unberührt. Die App liest den Inhalt Ihrer Zwischenablage nicht.

## 6. Password Generator
Passwörter werden auf Ihrem Gerät mit der sicheren Zufallsquelle des Systems erzeugt. Sie werden nie gespeichert, protokolliert, gesendet oder in den Verlauf geschrieben. Solange der Password Generator geöffnet ist, blockiert Android Screenshots und Bildschirmaufnahmen davon und blendet ihn in der Ansicht der letzten Apps aus.

## 7. Kinder
IT-ToolZ ist ein professionelles Werkzeug und richtet sich nicht an Kinder.

## 8. Änderungen
Wenn sich diese Erklärung ändert, wird die neue Fassung unter dieser Adresse mit einem neuen Gültigkeitsdatum veröffentlicht.

## 9. Kontakt
Fragen zu dieser Erklärung: Bitte [eröffnen Sie ein Issue auf GitHub](https://github.com/buadamlaz/it-toolz/issues). Die Support-E-Mail-Adresse finden Sie auch in der App unter Einstellungen → Kontakt & Support.
