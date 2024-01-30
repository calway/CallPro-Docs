# Configuratie van een extern domein
Om mail te versturen vanaf een domein van de klant/opdrachtgever kan gebruik worden gemaakt van verschillende opties. Afhankelijk van de voorkeur en/of mogelijkheden van de klant/opdrachtgever kan een van deze opties worden gekozen.

## Smtp server login 
Als de SMTP server van de klant/opdrachtgever basic authentication ondersteunt kan gebruik worden gemaakt van deze optie. De klant/opdrachtgever levert de dns naam en een gebruikersnaam en wachtwoord aan die worden ingesteld bij het call center in de fulfilment.

> Dit werkt nu (01-2024) ook nog met Microsoft 365

Ook Sendgrid biedt de mogelijkheid om smtp servers te gebruiken, dus als een klant/opdrachtgever Sendgrid gebruikt kan dit ook worden ingezet. Sendgrid biedt bovendien aardige statistieken en metrics.

## Gebruik mailserver van callcenter
Om mail namens het domein van de klant/opdrachtgever te kunnen versturen moetne SPF records op op het externe domein worden ingesteld.
Op het externe domein wordt in de SPF record een extra include opgenomen van het call center door een `include:spf.callcenter.nl` op te nemen.

Wij adviseren om een `spf.callcenter.nl` TXT record te maken als call center met geldige spf string. Het call center geeft deze naam door aan de klant/opdrachtgever die deze opneemt in zijn spf op het externe domein met als een include.

## Microsoft 365 connector
Indien de klant/opdrachtgever gebruik maakt van Microsoft 365 kan een Mailflow\connector worden aangemaakt in de Microsoft 365 Exchange administrator. De connector legt het IPv4 adres van het callcenter vast dat gebruik mag maken van de Microsoft 365 SMTP server van de klant/opdrachtgever.

Als de connector goed is geconfigureerd kan het callcenter connectie leggen via `extern-domain.mail.protection.outlook.com` met een geldig email adres uit de Microsoft 365 omgeving.

Bij het gebruik van een connector wordt het instellen van SPF records zoals eerder beschreven aangeraden om te voorkomen dat email als spam wordt aangemerkt.

## Stuur email van een mailbox van het call center
Soms is de branding van het from adres minder belangrijk. Dan kan email ook direct vanuit het callcenter verstuurd worden. de email komt dan van klant@callcenter.nl waarbij als Friendly naam "Klantnaam" wordt gebruikt.

Ook kan worden gekozen om als call center enkele **fun** domeinen te registreren. De mooiste namen zijn al bezet, maar namen als `filfilmentservices.nl`, `emailservices.nl`, `marketingservices.nl` of `klant-leukenaam.nl` zijn mogelijkheden. Dit domein wordt aan de mail omgeving van het call center gekoppeld en kan vervolgens gebruikt worden voor het versturen van mail. De klant/opdrachtgaver hoeft niks verder in te stellen.
