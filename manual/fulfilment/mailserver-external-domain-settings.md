# Configuratie van een extern domein
Om mail te versturen vanaf een domein van de klant/opdrachtgever kan gebruik worden gemaakt van verschillende opties. Afhankelijk van de voorkeur en/of mogelijkheden van de klant/opdrachtgever kan een van deze opties worden gekozen.

## Smtp server login 
Als de SMTP server van de klant/opdrachtgever basic authentication ondersteunt kan gebruik worden gemaakt van deze optie. Om het call center direct gebruik te laten maken van de smtp server van de klant/opdrachtgever dient het volgende te worden aangeleverd:
* DNS naam van de smtp server (ie. smtp.klant.nl)
* De poort waar de smtp server op luistert (meestal 587)
* De gebruikernaam om mee in te loggen
* Het wachtwoord van de gebruiker om mee in te loggen

 Deze gegevens worden in CallPro gebruikt om voor de fulfilment de juiste smtp server te selecteren.

## Gebruik mailserver van callcenter
Om mail namens het domein van de klant/opdrachtgever te kunnen versturen moeten SPF records op het externe domein worden ingesteld.
Op het externe domein van de klant/opdrachtgever wordt in de SPF record een extra include opgenomen van het call center door een `include:spf.callcenter.nl` op te nemen. Hier is `callcenter` de DNS naam van het callcenter. Dit ziet er dan bijvoorbeeld zo uit:
```
v=spf1 a:smtp.calway.nl mx include:spf.callcenter.nl include:spf.protection.outlook.com include:_spf.e-boekhouden.nl include:_spf.transip.email -all
```
Wij adviseren om een extra `spf.callcenter.nl` TXT record te maken als call center met geldige spf string. Hier is **x.x.x.x** het externe IPv4 van het CallPro platform.
```
v=spf1 a:x.x.x.x -all
```
> **Let op!** Vanaf April 2024 hebben Google en Yahoo aangegeven dat ze alleen nog mail accepteren voor hun klanten als zowel SPF als DKIM correct zijn geconfigureerd. Effectief moet de mail DMARC ondersteunen. Dit betekent dat bovenstaande niet voldoende is om email te bezorgen bij deze providers.

### Configuratie DKIM
Om ervoor te zorgen dat email ook bij gmail.com ontvangers niet in de spam terecht komt dient ook DKIM ingesteld te worden. Hiervoor wordt ene public private keypair gemaakt op de mailserver. Vervolgens moet deze als `callpro._domainkey` TXT record aan de DNS van het callcenter worden toegevoegd.

```
k=rsa; p=PUBLIC-KEY
```

Hier dient **PUBLIC-KEY** te worden vervange ndoor de vanuit Calway aangeleverde public key. Voor klanten/opdrahctgever moet ook een DKIM regel worden toegevoegd aan he tdomein waarvanuit het callcenter email kan versturen. Dit kan een CNAM record zijn voor `callpro._domainkey` met als waarde `callpro._domainkey.callcenter.nl`

Wij raden ook aan om altijd een `_dmarc` TXT record op hte domein te zetten met bijvoorbeeld `v=DMARC1; p=reject; sp=reject; pct=100`. 

## Microsoft 365 connector
Indien de klant/opdrachtgever gebruik maakt van Microsoft 365 kan een Mailflow\connector worden aangemaakt in de Microsoft 365 Exchange administrator. De connector legt het IPv4 adres van het callcenter vast dat gebruik mag maken van de Microsoft 365 SMTP server van de klant/opdrachtgever.

Als de connector goed is geconfigureerd kan het callcenter connectie leggen via `extern-domain.mail.protection.outlook.com` met een geldig email adres uit de Microsoft 365 omgeving.

Bij het gebruik van een connector worden correct ingestelde SPF records en DKIM instellingen verondersteld omdat dit een voorwaarde is om Microsoft 365 goed te gebruiken op een eigen domein.

## Microsoft Graph API
Voor Microsoft 365 gebruikers kan ook een Applicatie worden gemaakt in hun Entra ID voor CallPro. Door deze applicatie het recht te geven om email te versturen kan. Kijk [hier](./mailserver-instellingen-microsoft-365-graph-api.md) voor een guide om een applicatie te maken. Belangrijk is dat dat het `SMTP.Send` en `Mail.Send` recht ook wordt toegekend.

Ook hier dient de Microsoft 365 omgeving van de klant/opdrachtgever nog steeds een correcte SPF en DKIM configuratie te hebben.


## Stuur email van een mailbox van het call center
Soms is de branding van het from adres minder belangrijk. Dan kan email ook direct vanuit het callcenter verstuurd worden. De email komt dan van klant@callcenter.nl waarbij als Friendly naam "Klantnaam" wordt gebruikt.

Ook kan worden gekozen om als call center enkele **fun** domeinen te registreren. De mooiste namen zijn al bezet, maar namen als `fulfilmentservices.nl`, `emailservices.nl`, `marketingservices.nl` of `klant-leukenaam.nl` zijn mogelijkheden. Dit domein wordt aan de mail omgeving van het call center gekoppeld en kan vervolgens gebruikt worden voor het versturen van mail. De klant/opdrachtgaver hoeft niks verder in te stellen.

Het is nog steeds nodig om deze domeinen te koppelen aan een mailserver/dienst die spf en DKIM DMARC ondersteunt. Vanwege de mail volumes die een call center genereert wordt afgeraden om dit te doen met een Microsoft 365 tenant.

## Gebruik een externe dienst zoals SendGrid
Neem als callcenter, of vraag de klant om een sendgrid account te nemen. Gebruik de SMTP instellingen van deze account om mail te versturen. Diensten als SendGrid hebben voorzieningen voor spf, DKIM en DMARC wat de ontvangst tegoed komt. Bovendien hebben deze diensten ook aardige telemetry om de email volumes te monitoren.

* [SendGrid](https://sendgrid.com/)
* [Mailgun](https://www.mailgun.com/)
* [Campaignmonitor](https://campaignmonitor.com/)