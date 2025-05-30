# FulfilmentService Release Notes
Dit zijn de Release Notes voor het Fulfilment service.  Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.13 - 2025-03-07
### Change
- Vanwege de vele API integratie configs is een optie `\JS` JsonSafe toegevoegd die uit het mergeveld bepaalde karakters vervangt of verwijderd. Dit maakt het maken van een json payload een stuk leesbaarder.
    * " wordt vervangen door '
    * crlf wordt vervangen door een spatie
    * cr wordt vervangen door een spatie
    * lf wordt vervangen door een spatie
    * tab wordt vervangen door een spatie
    * \ wordt vervangen door \\


*** 
## v5.0.12 - 2025-03-03
### Change
- Verbetering van de opmaak van cellen bij het genereren van Excel bestanden. Voorheen werden alle cellen tekst, wat voor getallen een irritant driehoekje in Excel oplevert die aangeeft dat de cell tekst is maar het lijkt of er een getaal in staat. Ook werden cellen met tijdweergave opmaak niet correct afgebeeld, maar als getal. Met deze update worden de meeste cellen correct afgebeeld op basis van de opmaak die in Excel is ingesteld.

### Fix
- Bij het uitvoeren van queries is het normaal niet nodig om een unlimited query timeout te gebruiken, maar bij sommige langdurige queries of database operaties kan het wel makkelijk zijn om geen benoemde bovengrens op te geven. Met deze versie wordt QueryTimeout=0 geaccepteert.

*** 
## v5.0.11 - 2024-10-03
### Fix
- De response naar aanleiding van een webservice call werd op json content gecontroleert en dan werden velden eruit gehaald. De controle of iets een geldige json was was niet voldoende en leverde soms errors. Dit is nu verbeterd, illegale json responses worden nu netjes afgehandeld.

*** 
## v5.0.10 - 2024-09-16
### Fix
- Door een recente wijziging was een probleem ontstaan met het overnemen van instellingen van de MailServer tag. Bij gebruik van afwijkende instellingen voor poort, username en password kon het gebeuren dat verkeerde gegevens werden gebruikt waardoor het versturen van een email niet lukte. Met deze update wordt dat opgelost.

Doordat bij sommige fulfilment taken de fulfilment markering veld (uit het EXP_... veld) werd gevuld met **ERROR** als het versturen niet lukte leverde dit ook verwarring bij gebruiks van de Fulfilment Validatie die niet eerder error markeringen hadden gezien. Al geruimte tijd, sinds maart dit jaar, worden **ERROR** markeringen met een rode achtergrond kleur getoond.

*** 
## v5.0.9 - 2024-08-26
### Fix
- Het normale error gedrag van de `action` objecten is hersteld. Er was een probleem ontstaan waarbij als een `action` geen `onfailure` handling deed een fout die was opgetreden tijdens het uitvoeren van de `action` niet werd doorgegeven waardoor het uitvoeren van opvolgende `actions` gewoon door ging. Dit is niet het juiste gedrag! De Fulfilment werd altijd afgebroken in de loop waarna de uitvoering van de hele loop voor een opvolgend record werd gestart.
Met deze update is het originele gedrag als er geen `onfailure` handler is weer hersteld!

*** 
## v5.0.8 - 2024-07-22
### Fix
- Een issue met API calls waarbij de CacheSeconds0 werd gebruikt leverde errors. Dat is in deze release opgelost.

*** 
## v5.0.7 - 2024-07-22
### Fix
- Fix voor een probleem met Excel file caching die ervoor zorgde dat opvolgende `actions` de file niet konden gebruiken vanwege een Fil I/O locking.

*** 
## v5.0.6 - 2024-07-22
### Fix
- Vanwege issues met Excel file caching is in deze versie de cache uitgeschakeld zodat fulfilment batches de files kunnen emailen. Dit heeft wel impact op de performance omdat er nu veel meer file I/O wordt gedaan. Een betere fix is incoming.

*** 
## v5.0.5 - 2024-07-16
### Fix
- Fix voor weergave van datetime velden die een `null` waarde bevatten. Deze worden nu als lege string waarde afgebeeld.

*** 
## v5.0.4 - 2024-04-25
### Fix
- Door recente aanpassingen werden log regels niet altijd vorrect voorzien van waardes. In deze release is dat grotendeels gefixt waardoor logging weer beter gebruikt kan worden voor probleem opsporing.

*** 
## v5.0.3 - 2024-04-03
### Update
- Update library ClosedXml om zo de laatste versie van OpenXml (Word en Excel) te ondersteunen.

*** 
## v5.0.2 - 2023-12-07
### Fix
- Een probleem in de errorhandling icm `onsuccess` en `onfailure` doorgevoerd weaardoro het aantal incorrecte errors drastisch lager zal worden.

*** 
## v5.0.1 - 2023-07-26
### Fix
- Herstel van het `ReferenceId` veld in de logging
