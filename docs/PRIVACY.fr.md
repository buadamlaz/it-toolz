# IT-ToolZ — Politique de confidentialité

<p align="right"><a href="../PRIVACY.md">English</a> · <a href="PRIVACY.tr.md">Türkçe</a> · <a href="PRIVACY.de.md">Deutsch</a> · <a href="PRIVACY.es.md">Español</a> · <a href="PRIVACY.pt-BR.md">Português (Brasil)</a> · <b>Français</b> · <a href="PRIVACY.ru.md">Русский</a> · <a href="README.fr.md">IT-ToolZ</a></p>

**Contact :** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Date d'entrée en vigueur :** 28 octobre 2026

*Cette traduction est fournie pour faciliter la lecture. Seule la [version anglaise](../PRIVACY.md) fait foi.*

## 1. À propos de l'app
IT-ToolZ est une boîte à outils pour les professionnels de l'IT et des réseaux. Elle effectue des diagnostics réseau (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), propose des outils pour le réseau local (Wake-on-LAN, LAN Device Discovery), des calculateurs et convertisseurs hors ligne (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, Hash Generator pour du texte, Password Generator) et affiche des informations sur votre connexion réseau actuelle (« Mon réseau »).

IT-ToolZ n'a pas de comptes utilisateur, pas d'analyse d'audience, pas de rapports de plantage, pas de publicité et pas de serveur propre. **L'éditeur ne reçoit aucune donnée de l'app.**

## 2. Données stockées sur votre appareil
- L'**historique** des outils réseau (par exemple l'hôte vérifié, le statut du résultat et l'heure ; pour Wake-on-LAN, l'adresse MAC saisie ; pour LAN Device Discovery, uniquement la plage analysée et le nombre d'appareils trouvés), les **favoris** (quels outils et dans quel ordre) et les **paramètres** (langue, thème, options de Password Generator) sont stockés uniquement dans l'espace de stockage privé de l'app sur votre appareil.
- L'historique ne contient jamais de mots de passe, jetons, cookies, identifiants dans des URL ni paramètres de requête d'URL. Password Generator, Hash Generator, Base64, URL Encoder/Decoder et JSON Formatter n'écrivent jamais rien dans l'historique.
- Les informations de la page « Mon réseau » et les résultats de Public IP ne sont pas stockés.
- **Sauvegardes :** les données de l'app sont exclues de la sauvegarde cloud d'Android et du transfert d'appareil à appareil. Elles restent uniquement sur cet appareil.
- **Supprimer vos données :** vous pouvez supprimer une entrée de l'historique (appui long) ou tout l'historique (Paramètres > Données > Effacer l'historique). Effacer les données de l'app dans les paramètres d'Android ou désinstaller l'app supprime toutes ses données. Comme l'éditeur n'en conserve aucune copie, il n'y a rien d'autre à supprimer.

## 3. Données envoyées sur le réseau
L'app ne se connecte à internet que lorsque vous lancez un outil réseau ou appuyez sur un bouton qui le demande.

- **Destinations que vous choisissez.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker et HTTP Headers se connectent à l'hôte, à l'adresse ou à l'URL que vous saisissez (HTTP Headers suit aussi les redirections). Comme pour toute connexion internet, cette destination voit l'adresse IP de votre appareil ; pour Traceroute, les routeurs le long du chemin voient aussi les paquets de test. SSL Certificate Checker envoie le nom d'hôte pendant la négociation TLS et aucune autre donnée. HTTP Headers envoie une requête par adresse, sans cookies ni données de connexion ; les adresses `http://` simples ne sont pas chiffrées.
- **Votre réseau local.** Wake-on-LAN envoie un « magic packet » (UDP) contenant l'adresse MAC saisie à l'adresse que vous choisissez, généralement votre réseau local. LAN Device Discovery analyse uniquement la plage du réseau local que vous choisissez (plages d'adresses privées uniquement) par ICMP echo et tentatives de connexion TCP, et demande les noms des appareils à votre résolveur DNS. Les listes d'appareils s'affichent à l'écran et ne sont ni stockées ni envoyées nulle part.
- **DNS.** DNS Lookup et Reverse DNS envoient le nom ou l'adresse saisi au résolveur DNS de votre appareil (le serveur DNS de votre réseau, votre fournisseur de DNS privé ou votre VPN). Les requêtes DNS ne sont généralement pas chiffrées, sauf si le DNS privé est actif. Dans DNS Lookup, vous pouvez aussi choisir vous-même un serveur DNS (1.1.1.1 de Cloudflare, 8.8.8.8 de Google ou une adresse que vous saisissez) : la requête part alors directement vers ce serveur par le port 53, sans chiffrement, et contourne le DNS privé et les réglages DNS de votre appareil. L'app mémorise votre dernier choix uniquement sur l'appareil.
- **RDAP/WHOIS.** Pour un nom de domaine, l'app télécharge des listes publiques auprès de l'IANA (data.iana.org ; ces requêtes ne contiennent aucune recherche) puis interroge le registre responsable de ce domaine (par exemple Verisign). Pour une adresse IP, l'app interroge le service tiers **ipwho.is**, qui renvoie la localisation approximative et le fournisseur réseau de l'adresse. Le registre ou ipwho.is reçoit votre recherche et votre adresse IP. Les adresses privées et locales (par exemple 192.168.x.x) ne sont jamais envoyées.
- **Public IP.** Pour afficher votre adresse IP publique avec son fournisseur réseau et sa localisation approximative, l'app interroge le service tiers **ipwho.is**. Seulement si ipwho.is est injoignable, l'app interroge en même temps deux autres services tiers : **ipify** (api.ipify.org, api6.ipify.org) et **ifconfig.me**. Chaque service interrogé reçoit votre adresse IP publique ; aucune autre donnée n'est envoyée en dehors de la langue de l'app (pour les noms de lieux). Cela ne se produit que lorsque vous appuyez sur le bouton dans l'outil Public IP ou sur la page « Mon réseau ». Si vous touchez les coordonnées approximatives affichées pour une adresse IP, elles sont transmises à l'app de cartes de votre appareil (sur iPhone, Plans d'Apple) ; l'app elle-même n'envoie rien.

Ces destinations sont exploitées par des tiers et traitent les requêtes selon leurs propres politiques de confidentialité. L'app n'utilise pas votre adresse IP pour déterminer votre position.

## 4. Autorisations
- **Internet, état du réseau** — pour exécuter les outils réseau et afficher votre connexion actuelle.
- **État du Wi-Fi** — pour afficher la fréquence, la puissance du signal et le débit du lien Wi-Fi dans « Mon réseau ».
- **Réseau local (iOS)** — iOS demande l'autorisation avant que l'app puisse joindre des appareils de votre réseau local (Wake-on-LAN). Elle n'est utilisée que pour l'outil que vous lancez.
- **Localisation (facultative)** — Android n'affiche le nom du réseau Wi-Fi connecté (SSID/BSSID) qu'aux apps ayant accès à la position exacte. IT-ToolZ ne la demande que lorsque vous touchez le bouton dans « Mon réseau ». Le nom du réseau s'affiche à l'écran et n'est jamais stocké ni envoyé. L'app ne lit jamais votre position. Tout le reste fonctionne sans cette autorisation.

L'app n'accède pas à votre numéro de téléphone, vos contacts, messages, fichiers, appareil photo ou micro, et ne lit pas les identifiants de la SIM ou de l'appareil (IMSI, ICCID, IMEI).

## 5. Presse-papiers
Lorsque vous copiez une valeur, elle est placée dans le presse-papiers de votre appareil, où d'autres apps ou votre clavier peuvent la lire. Les mots de passe copiés depuis Password Generator sont marqués comme sensibles, si bien qu'Android 13 et versions ultérieures les masquent dans l'aperçu du presse-papiers. « Vider le presse-papiers » supprime le mot de passe copié uniquement s'il est encore le contenu actuel du presse-papiers ; ce que vous avez copié ensuite n'est pas touché. L'app ne lit pas le contenu de votre presse-papiers.

## 6. Password Generator
Les mots de passe sont générés sur votre appareil avec la source aléatoire sécurisée du système. Ils ne sont jamais stockés, journalisés, envoyés ni écrits dans l'historique. Tant que Password Generator est ouvert, Android bloque les captures et enregistrements d'écran et le masque dans la vue des apps récentes.

## 7. Enfants
IT-ToolZ est un outil professionnel et ne s'adresse pas aux enfants.

## 8. Modifications
Si cette politique change, la nouvelle version sera publiée à cette adresse avec une nouvelle date d'entrée en vigueur.

## 9. Contact
Pour toute question sur cette politique, [ouvrez une issue sur GitHub](https://github.com/buadamlaz/it-toolz/issues). L'adresse e-mail d'assistance figure aussi dans l'app, sous Paramètres → Contact et assistance.
