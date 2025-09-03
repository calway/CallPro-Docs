# Configuratie van een extern domein
Om mail te versturen vanaf een domein van de klant/opdrachtgever kan gebruik worden gemaakt van verschillende opties. Afhankelijk van de voorkeur en/of mogelijkheden van de klant/opdrachtgever kan een van deze opties worden gekozen.

## Smtp server login 
Als de SMTP server van de klant/opdrachtgever basic authentication ondersteunt kan gebruik worden gemaakt van deze optie. Om het call center direct gebruik te laten maken van de smtp server van de klant/opdrachtgever dient het volgende te worden aangeleverd:
* DNS naam van de smtp server (ie. smtp.klant.nl)
* De poort waar de smtp server op luistert (meestal 587)
* De gebruikernaam om mee in te loggen
* Het wachtwoord van de gebruiker om mee in te loggen

 Deze gegevens worden in CallPro gebruikt om voor de fulfilment de juiste smtp server te selecteren.

#### Sendgrid
Ook Sendgrid biedt de mogelijkheid om smtp servers te gebruiken, dus als een klant/opdrachtgever Sendgrid gebruikt kan dit ook worden ingezet. Sendgrid biedt bovendien aardige statistieken en metrics.

## Gebruik mailserver van callcenter
Om mail namens het domein van de klant/opdrachtgever te kunnen versturen moeten SPF records op het externe domein worden ingesteld.
Op het externe domein wordt in de SPF record een extra include opgenomen van het call center door een `include:spf.callcenter.nl` op te nemen.

Wij adviseren om een `spf.callcenter.nl` TXT record te maken als call center met geldige spf string. Het call center geeft deze naam door aan de klant/opdrachtgever die deze opneemt in zijn spf op het externe domein met als een include.

> **Let op!** Vanaf April 2024 hebben Google en Yahoo aangegeven dat ze alleen nog mail accepteren voor hun klanten als zowel SPF als DKIM correct zijn geconfigureerd. Effectief moet de mail DMARC ondersteunen. Dit betekent ondermeer dat de werkwijze die in deze paragraaf wordt geschreven niet meer werkt, omdat CallPro intern gebruik maakt van een smtp server die geen DKIM ondersteunt.

## Microsoft 365 connector
Indien de klant/opdrachtgever gebruik maakt van Microsoft 365 kan een Mailflow\connector worden aangemaakt in de Microsoft 365 Exchange administrator. De connector legt het IPv4 adres van het callcenter vast dat gebruik mag maken van de Microsoft 365 SMTP server van de klant/opdrachtgever.

Als de connector goed is geconfigureerd kan het callcenter connectie leggen via `extern-domain.mail.protection.outlook.com` met een geldig email adres uit de Microsoft 365 omgeving.

Bij het gebruik van een connector wordt het instellen van SPF records zoals eerder beschreven aangeraden om te voorkomen dat email als spam wordt aangemerkt. Omdat nu gebruik wordt gemaakt van de Microsoft 365 omgeving van de klant/opdrachtgever is DKIM meestal goed ingesteld.

## Microsoft Graph API
Voor Microsoft 365 gebruikers kan ook een Applicatie worden gemaakt in hun Entra ID voor CallPro. Door deze applicatie het recht te geven om email te versturen kan. Kijk [hier](./mailserver-instellingen-microsoft-365-graph-api.md) voor een guide om een applicatie te maken. Belangrijk is dat dat het `SMTP.Send` en `Mail.Send` recht ook wordt toegekend.

Ook hier dient de Microsoft 365 omgeving nog steeds een correcte DKIM configuratie te hebben.


## Stuur email van een mailbox van het call center
Soms is de branding van het from adres minder belangrijk. Dan kan email ook direct vanuit het callcenter verstuurd worden. De email komt dan van klant@callcenter.nl waarbij als Friendly naam "Klantnaam" wordt gebruikt.

Ook kan worden gekozen om als call center enkele **fun** domeinen te registreren. De mooiste namen zijn al bezet, maar namen als `fulfilmentservices.nl`, `emailservices.nl`, `marketingservices.nl` of `klant-leukenaam.nl` zijn mogelijkheden. Dit domein wordt aan de mail omgeving van het call center gekoppeld en kan vervolgens gebruikt worden voor het versturen van mail. De klant/opdrachtgaver hoeft niks verder in te stellen.

Het is nog steeds nodig om deze domeinen te koppelen aan een mailserver/dienst die spf en DKIM DMARC ondersteunt. Vanwege de mail volumes die een call center genereert wordt afgeraden om dit te doen met een Microsoft 365 tenant.

## Gebruik een externe dienst zoals SendGrid
Neem als callcenter , of vraag de klant om een sendgrid account te nemen. Gebruik de SMTP instellingen van deze account om mail te versturen. Diensten als SendGrid hebben voorzieningen voor spf, DKIM en DMARC wat de ontvangts tegoed komt. Bovendien hebben deze diensten ook aardige telemetry om de email volumes te monitoren.

* [SendGrid](https://sendgrid.com/)
* [Mailgun](https://www.mailgun.com/)
* [Campaignmonitor](https://campaignmonitor.com/)