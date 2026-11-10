# IT-ToolZ — Política de privacidade

<p align="right"><a href="../PRIVACY.md">English</a> · <a href="PRIVACY.tr.md">Türkçe</a> · <a href="PRIVACY.de.md">Deutsch</a> · <a href="PRIVACY.es.md">Español</a> · <b>Português (Brasil)</b> · <a href="PRIVACY.fr.md">Français</a> · <a href="PRIVACY.ru.md">Русский</a> · <a href="README.pt-BR.md">IT-ToolZ</a></p>

**Contato:** [GitHub Issues](https://github.com/buadamlaz/it-toolz/issues)  
**Data de vigência:** 28 de outubro de 2026

*Esta tradução é oferecida para facilitar a leitura. A versão válida é a [versão em inglês](../PRIVACY.md).*

## 1. Sobre o app
O IT-ToolZ é um conjunto de ferramentas para profissionais de TI e redes. Ele faz diagnósticos de rede (Ping, Traceroute, DNS Lookup, Reverse DNS, Port Check, NTP Time Checker, SSL Certificate Checker, HTTP Headers, RDAP/WHOIS, Public IP), oferece ferramentas de rede local (Wake-on-LAN, LAN Device Discovery), calculadoras e conversores offline (Subnet Calculator, IP Converter, Base64, URL Encoder/Decoder, JSON Formatter, Hash Generator para texto, Password Generator) e mostra informações sobre a sua conexão de rede atual ("Minha rede").

O IT-ToolZ não tem contas de usuário, análises, relatórios de falhas, anúncios nem servidor próprio. **O editor não recebe nenhum dado do app.**

## 2. Dados armazenados no seu dispositivo
- O **histórico** das ferramentas de rede (por exemplo, o host que você verificou, o status do resultado e o horário; no Wake-on-LAN, o endereço MAC que você digitou; no LAN Device Discovery, apenas a faixa verificada e o número de dispositivos encontrados), os **favoritos** (quais ferramentas e em que ordem) e as **configurações** (idioma, tema, opções do Password Generator) ficam armazenados apenas no armazenamento privado do app no seu dispositivo.
- O histórico nunca contém senhas, tokens, cookies, credenciais em URLs ou parâmetros de consulta de URL. Password Generator, Hash Generator, Base64, URL Encoder/Decoder e JSON Formatter nunca gravam nada no histórico.
- As informações da página "Minha rede" e os resultados do Public IP não são armazenados.
- **Backups:** os dados do app são excluídos do backup em nuvem do Android e da transferência entre dispositivos. Eles ficam apenas neste dispositivo.
- **Excluir seus dados:** você pode excluir um item do histórico (toque e segure) ou todo o histórico (Configurações > Dados > Limpar histórico). Limpar os dados do app nas configurações do Android ou desinstalar o app remove todos os dados dele. Como o editor não guarda nenhuma cópia, não há mais nada a excluir.

## 3. Dados enviados pela rede
O app só se conecta à internet quando você inicia uma ferramenta de rede ou toca em um botão que solicita isso.

- **Destinos que você escolhe.** Ping, Traceroute, Port Check, NTP Time Checker, SSL Certificate Checker e HTTP Headers se conectam ao host, endereço ou URL que você digita (o HTTP Headers também segue os redirecionamentos). Como em qualquer conexão com a internet, esse destino vê o endereço IP do seu dispositivo; no Traceroute, os roteadores ao longo do caminho também veem os pacotes de teste. O SSL Certificate Checker envia o nome do host durante o handshake TLS e nenhum outro dado. O HTTP Headers envia uma solicitação por endereço, sem cookies nem dados de login; endereços `http://` simples não são criptografados.
- **Sua rede local.** O Wake-on-LAN envia um "magic packet" (UDP) com o endereço MAC que você digita para o endereço que você escolhe, normalmente a sua rede local. O LAN Device Discovery verifica apenas a faixa de rede local que você escolhe (somente faixas de endereços privados) com ICMP echo e tentativas de conexão TCP, e pede ao seu resolvedor DNS os nomes dos dispositivos. As listas de dispositivos são mostradas na tela e não são armazenadas nem enviadas a lugar nenhum.
- **DNS.** DNS Lookup e Reverse DNS enviam o nome ou endereço que você digita ao resolvedor DNS do seu dispositivo (o servidor DNS da sua rede, o seu provedor de DNS privado ou a sua VPN). As consultas DNS geralmente não são criptografadas, a menos que o DNS privado esteja ativo. No DNS Lookup você pode escolher um servidor DNS (1.1.1.1 da Cloudflare, 8.8.8.8 do Google ou um endereço que você digitar): a consulta vai então diretamente para esse servidor pela porta 53, sem criptografia, e ignora o DNS privado e as configurações de DNS do seu dispositivo. O app lembra a sua última escolha apenas no dispositivo.
- **RDAP/WHOIS.** Para um nome de domínio, o app baixa listas públicas da IANA (data.iana.org; essas solicitações não contêm nenhuma consulta) e depois consulta o registro responsável por esse domínio (por exemplo, a Verisign). Para um endereço IP, o app consulta o serviço de terceiros **ipwho.is**, que retorna a localização aproximada e o provedor de rede do endereço. O registro ou o ipwho.is recebe a sua consulta e o seu endereço IP. Endereços privados e locais (por exemplo, 192.168.x.x) nunca são enviados.
- **Public IP.** Para mostrar o seu endereço IP público com o provedor de rede e a localização aproximada, o app consulta o serviço de terceiros **ipwho.is**. Somente se o ipwho.is não estiver acessível, o app consulta ao mesmo tempo dois outros serviços de terceiros: **ipify** (api.ipify.org, api6.ipify.org) e **ifconfig.me**. Cada serviço consultado recebe o seu endereço IP público; nenhum outro dado é enviado além do idioma do app (para nomes de lugares). Isso só acontece quando você toca no botão da ferramenta Public IP ou da página "Minha rede". Se você tocar nas coordenadas aproximadas mostradas para um endereço IP, elas são passadas ao app de mapas do seu dispositivo (no iPhone, o Apple Mapas); o próprio app não envia nada.

Esses destinos são operados por terceiros e tratam as solicitações de acordo com as próprias políticas de privacidade. O app não usa o seu endereço IP para determinar a sua localização.

## 4. Permissões
- **Internet, estado da rede** — para executar as ferramentas de rede e mostrar a sua conexão atual.
- **Estado do Wi-Fi** — para mostrar a frequência, a intensidade do sinal e a velocidade do link Wi-Fi em "Minha rede".
- **Rede local (iOS)** — o iOS pede permissão antes que o app possa acessar dispositivos na sua rede local (Wake-on-LAN). Ela é usada apenas para a ferramenta que você inicia.
- **Localização (opcional)** — o Android mostra o nome da rede Wi-Fi conectada (SSID/BSSID) apenas para apps com acesso à localização precisa. O IT-ToolZ pede essa permissão somente quando você toca no botão em "Minha rede". O nome da rede é mostrado na tela e nunca é armazenado nem enviado. O app nunca lê a sua localização. Todo o resto funciona sem essa permissão.

O app não acessa o seu número de telefone, contatos, mensagens, arquivos, câmera ou microfone, e não lê identificadores do chip SIM nem do dispositivo (IMSI, ICCID, IMEI).

## 5. Área de transferência
Quando você copia um valor, ele é colocado na área de transferência do seu dispositivo, onde outros apps ou o seu teclado podem lê-lo. As senhas copiadas do Password Generator são marcadas como confidenciais, para que o Android 13 e versões posteriores as ocultem na pré-visualização da área de transferência. "Limpar área de transferência" remove a senha copiada somente se ela ainda for o conteúdo atual da área de transferência; o que você copiar depois não é alterado. O app não lê o conteúdo da sua área de transferência.

## 6. Password Generator
As senhas são geradas no seu dispositivo com a fonte aleatória segura do sistema. Elas nunca são armazenadas, registradas em log, enviadas nem gravadas no histórico. Enquanto o Password Generator está aberto, o Android bloqueia capturas e gravações de tela e o oculta na visualização de apps recentes.

## 7. Crianças
O IT-ToolZ é uma ferramenta profissional e não é destinado a crianças.

## 8. Alterações
Se esta política mudar, a nova versão será publicada neste endereço com uma nova data de vigência.

## 9. Contato
Dúvidas sobre esta política: [abra uma issue no GitHub](https://github.com/buadamlaz/it-toolz/issues). O e-mail de suporte também aparece no app em Configurações → Contato e suporte.
