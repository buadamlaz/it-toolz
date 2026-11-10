# IT-ToolZ — Política de privacidad

<p align="right"><a href="../PRIVACY.md">English</a> · <a href="PRIVACY.tr.md">Türkçe</a> · <a href="PRIVACY.de.md">Deutsch</a> · <b>Español</b> · <a href="PRIVACY.pt-BR.md">Português (Brasil)</a> · <a href="PRIVACY.fr.md">Français</a> · <a href="PRIVACY.ru.md">Русский</a> · <a href="README.es.md">IT-ToolZ</a></p>

**Contacto:** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Fecha de entrada en vigor:** 28 de octubre de 2026

*Esta traducción se ofrece para facilitar la lectura. La versión válida es la [versión en inglés](../PRIVACY.md).*

## 1. Sobre la app
IT-ToolZ es un conjunto de herramientas para profesionales de IT y redes. Realiza diagnósticos de red (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), ofrece herramientas de red local (Wake-on-LAN, LAN Device Discovery), calculadoras y conversores sin conexión (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, Hash Generator para texto, Password Generator) y muestra información sobre tu conexión de red actual («Mi red»).

IT-ToolZ no tiene cuentas de usuario, ni analítica, ni informes de fallos, ni publicidad, ni servidor propio. **El editor no recibe ningún dato de la app.**

## 2. Datos guardados en tu dispositivo
- El **historial** de las herramientas de red (por ejemplo, el host que comprobaste, el estado del resultado y la hora; en Wake-on-LAN, la dirección MAC que introdujiste; en LAN Device Discovery, solo el rango escaneado y el número de dispositivos encontrados), los **favoritos** (qué herramientas y en qué orden) y los **ajustes** (idioma, tema, opciones de Password Generator) se guardan solo en el almacenamiento privado de la app en tu dispositivo.
- El historial nunca contiene contraseñas, tokens, cookies, credenciales dentro de URL ni parámetros de consulta de URL. Password Generator, Hash Generator, Base64, URL Encoder/Decoder y JSON Formatter nunca escriben nada en el historial.
- La información de la página «Mi red» y los resultados de Public IP no se guardan.
- **Copias de seguridad:** los datos de la app están excluidos de la copia de seguridad en la nube de Android y de la transferencia entre dispositivos. Permanecen solo en este dispositivo.
- **Eliminar tus datos:** puedes eliminar una entrada del historial (mantenla pulsada) o todo el historial (Ajustes > Datos > Borrar historial). Borrar los datos de la app en los ajustes de Android o desinstalarla elimina todos sus datos. Como el editor no guarda ninguna copia, no hay nada más que eliminar.

## 3. Datos enviados por la red
La app solo se conecta a internet cuando inicias una herramienta de red o pulsas un botón que lo requiere.

- **Destinos que eliges.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker y HTTP Headers se conectan al host, la dirección o la URL que introduces (HTTP Headers también sigue sus redirecciones). Como en cualquier conexión a internet, ese destino ve la dirección IP de tu dispositivo; en Traceroute, los routers del camino también ven los paquetes de prueba. SSL Certificate Checker envía el nombre del host durante el protocolo de enlace TLS y ningún otro dato. HTTP Headers envía una solicitud por dirección sin cookies ni datos de inicio de sesión; las direcciones `http://` simples no están cifradas.
- **Tu red local.** Wake-on-LAN envía un «magic packet» (UDP) con la dirección MAC que introduces a la dirección que eliges, normalmente tu red local. LAN Device Discovery escanea solo el rango de red local que eliges (solo rangos de direcciones privadas) con ICMP echo e intentos de conexión TCP, y pide a tu resolutor DNS los nombres de los dispositivos. Las listas de dispositivos se muestran en pantalla y no se guardan ni se envían a ningún sitio.
- **DNS.** DNS Lookup y Reverse DNS envían el nombre o la dirección que introduces al resolutor DNS de tu dispositivo (el servidor DNS de tu red, tu proveedor de DNS privado o tu VPN). Las consultas DNS normalmente no están cifradas salvo que el DNS privado esté activo. En DNS Lookup puedes elegir tú mismo un servidor DNS (1.1.1.1 de Cloudflare, 8.8.8.8 de Google o una dirección que introduzcas): la consulta va entonces directamente a ese servidor por el puerto 53, sin cifrar, y omite el DNS privado y los ajustes DNS de tu dispositivo. La app recuerda tu última elección solo en el dispositivo.
- **RDAP/WHOIS.** Para un nombre de dominio, la app descarga listas públicas de la IANA (data.iana.org; estas solicitudes no contienen ninguna consulta) y después consulta al registro responsable de ese dominio (por ejemplo, Verisign). Para una dirección IP, la app consulta al servicio de terceros **ipwho.is**, que devuelve la ubicación aproximada y el proveedor de red de la dirección. El registro o ipwho.is recibe tu consulta y tu dirección IP. Las direcciones privadas y locales (por ejemplo, 192.168.x.x) nunca se envían.
- **Public IP.** Para mostrar tu dirección IP pública con su proveedor de red y su ubicación aproximada, la app consulta al servicio de terceros **ipwho.is**. Solo si no se puede acceder a ipwho.is, la app consulta a la vez a otros dos servicios de terceros: **ipify** (api.ipify.org, api6.ipify.org) e **ifconfig.me**. Cada servicio consultado recibe tu dirección IP pública; no se envía ningún otro dato aparte del idioma de la app (para los nombres de lugares). Esto solo ocurre cuando pulsas el botón en la herramienta Public IP o en la página «Mi red». Si tocas las coordenadas aproximadas que se muestran para una dirección IP, se pasan a la app de mapas de tu dispositivo (en iPhone, Apple Mapas); la app en sí no envía nada.

Estos destinos los gestionan terceros y tratan las solicitudes según sus propias políticas de privacidad. La app no usa tu dirección IP para determinar tu ubicación.

## 4. Permisos
- **Internet, estado de la red** — para ejecutar las herramientas de red y mostrar tu conexión actual.
- **Estado de la Wi-Fi** — para mostrar la frecuencia, la intensidad de la señal y la velocidad del enlace Wi-Fi en «Mi red».
- **Red local (iOS)** — iOS pide permiso antes de que la app pueda acceder a dispositivos de tu red local (Wake-on-LAN). Se usa solo para la herramienta que inicias.
- **Ubicación (opcional)** — Android muestra el nombre de la red Wi-Fi conectada (SSID/BSSID) solo a las apps con acceso a la ubicación precisa. IT-ToolZ lo pide solo cuando tocas el botón en «Mi red». El nombre de la red se muestra en pantalla y nunca se guarda ni se envía. La app nunca lee tu ubicación. Todo lo demás funciona sin este permiso.

La app no accede a tu número de teléfono, contactos, mensajes, archivos, cámara ni micrófono, y no lee identificadores de la SIM ni del dispositivo (IMSI, ICCID, IMEI).

## 5. Portapapeles
Cuando copias un valor, se coloca en el portapapeles de tu dispositivo, donde otras apps o tu teclado podrían leerlo. Las contraseñas copiadas desde Password Generator se marcan como sensibles, de modo que Android 13 y posteriores las ocultan en la vista previa del portapapeles. «Vaciar portapapeles» elimina la contraseña copiada solo si sigue siendo el contenido actual del portapapeles; lo que hayas copiado después no se toca. La app no lee el contenido de tu portapapeles.

## 6. Password Generator
Las contraseñas se generan en tu dispositivo con la fuente aleatoria segura del sistema. Nunca se guardan, se registran, se envían ni se escriben en el historial. Mientras Password Generator está abierto, Android bloquea las capturas y grabaciones de pantalla y lo oculta en la vista de apps recientes.

## 7. Menores
IT-ToolZ es una herramienta profesional y no está dirigida a menores.

## 8. Cambios
Si esta política cambia, la nueva versión se publicará en esta dirección con una nueva fecha de entrada en vigor.

## 9. Contacto
Para preguntas sobre esta política, [abre un issue en GitHub](https://github.com/buadamlaz/it-toolz/issues). La dirección de correo de soporte también aparece en la app, en Ajustes → Contacto y soporte.
