# FulfilmentService Release Notes
Dit zijn de Release Notes voor het Fulfilment service.  Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

***
## v5.0.15 - 2026-04-08
### Added
- Een nieuw commando `if` die op basis van de `condition` attribuut de `then` of `else` sub-tag uitvoert.
```
<if condition="<boolean expression>">
    <then>
        ...
    </then>
    <else>
        ...
    </else>
</if>
```
### Fixed
- De `\JS` parameter negeerde alle resultaten van parameters die ervoor werden uitgevoerd. Dat is hiermee opgelost.
- In de webservice action is een extra tag toegevoegd om formdata te kunnen sturen. Sommige api's werken met een formdata blok, bijvoorbeeld om bestanden te uploaden en dat kan nu ook. Het is met deze methode niet mogelijk om complete formulieren te sturen, op dit moment wordt 1 data element ondersteunt. In plaats van een `<payload></payload>` moet dan een `<formdata></formdata>` tag worden gebruikt.

### Changed
- **BREAKING** Voor actions die gebruik maken van templates is het opgeven van de source van de template nu verplicht. Zonder dit attribuut wordt ervan uitgegaan dat de template in de tag staat. 
    - Alle `<input>` tags moeten worden voorzien van een `source="file"` als de template uit een bestand komt. Dus in de tag wordt verwezen naar een bestand dat de template bevat.
    - Alle `<payload>` tags moeten worden voorzien van een `source="file"` als de template uit een bestand komt. 
    - In de Email action moet bij de `<body>` tag ook gebruik worden gemaakt van `source="file"` als de template uit een bestand komt.
- **BREAKING** Er zijn geen actieve fulfilment taken die gebruik maken van de oude schedule types `daily`, `weekly` en `monthly` en ze worden met deze release dan ook al verwijderd hoewel dit een patch verienummer is!
- **BREAKING** Er zijn geen actieve fulfilment taken die gebruik van legacy schrijfwijze van encoding en ze worden met deze release dan ook verwijderd. Het gaat om de schrijfwijze `bigendianunicode`, `utf7`, `utf8`, `utf32`, `unicode`, `ascii` en `latin1` die resp. `utf-16BE`, `utf-7`, `utf-8`, `utf-32`, `utf-16` `us-ascii` en `iso-8859-1` zijn geworden. De encoding `default` is ook verwijderd, als de default encoding gebruikt moet worden geef dan geen encoding parameter mee.
- **BREAKING** `onsuccesfull` is in deze release verwijderd omdat overal `onsuccess` wordt gebruikt.
- **BREAKING** Niemand gebruikt dit meer in actieve configs dus we hebben de `connectstring` tag verwijderd. Het is nu verplicht om het nieuwe  `connectionstring` tag te gebruiken om af te wijken van de connectionstring.
- **BREAKING** `innersource` attribuut moet worden vervangen door `source`. De `source` attribuut is dan de enige optie om aan te geven of de bron uit een Bestand komt of niet. En in veel gevallen is dit nu ook verplicht om op te geven!
- **BREAKING** `ErrorsMailTo` tag en alle onderliggende tags zijn verwijderd. Alleen `Errors` wordt nog ondersteund.

***
## v5.0.14 - 2025-04-08
### Fixed
- Herstel het oude Cache gedrag omdat de nieuwe methode veel problemen gaf en het noodzakelijk maakte dat elke taak 10 seconden bleef wachten. Onacceptabel.

***
## v5.0.13 - 2025-03-07
### Changed
- Vanwege de vele API integratie configs is een optie `\JS` JsonSafe toegevoegd die uit het mergeveld bepaalde karakters vervangt of verwijderd. Dit maakt het maken van een json payload een stuk leesbaarder.
    * " wordt vervangen door '
    * crlf wordt vervangen door een spatie
    * cr wordt vervangen door een spatie
    * lf wordt vervangen door een spatie
    * tab wordt vervangen door een spatie
    * \ wordt vervangen door \\


*** 
## v5.0.12 - 2025-03-03
### Changed
- Verbetering van de opmaak van cellen bij het genereren van Excel bestanden. Voorheen werden alle cellen tekst, wat voor getallen een irritant driehoekje in Excel oplevert die aangeeft dat de cell tekst is maar het lijkt of er een getaal in staat. Ook werden cellen met tijdweergave opmaak niet correct afgebeeld, maar als getal. Met deze update worden de meeste cellen correct afgebeeld op basis van de opmaak die in Excel is ingesteld.

### Fixed
- Bij het uitvoeren van queries is het normaal niet nodig om een unlimited query timeout te gebruiken, maar bij sommige langdurige queries of database operaties kan het wel makkelijk zijn om geen benoemde bovengrens op te geven. Met deze versie wordt QueryTimeout=0 geaccepteert.

*** 
## v5.0.11 - 2024-10-03
### Fixed
- De response naar aanleiding van een webservice call werd op json content gecontroleert en dan werden velden eruit gehaald. De controle of iets een geldige json was was niet voldoende en leverde soms errors. Dit is nu verbeterd, illegale json responses worden nu netjes afgehandeld.

*** 
## v5.0.10 - 2024-09-16
### Fixed
- Door een recente wijziging was een probleem ontstaan met het overnemen van instellingen van de MailServer tag. Bij gebruik van afwijkende instellingen voor poort, username en password kon het gebeuren dat verkeerde gegevens werden gebruikt waardoor het versturen van een email niet lukte. Met deze update wordt dat opgelost.

Doordat bij sommige fulfilment taken de fulfilment markering veld (uit het EXP_... veld) werd gevuld met **ERROR** als het versturen niet lukte leverde dit ook verwarring bij gebruiks van de Fulfilment Validatie die niet eerder error markeringen hadden gezien. Al geruimte tijd, sinds maart dit jaar, worden **ERROR** markeringen met een rode achtergrond kleur getoond.

*** 
## v5.0.9 - 2024-08-26
### Fixed
- Het normale error gedrag van de `action` objecten is hersteld. Er was een probleem ontstaan waarbij als een `action` geen `onfailure` handling deed een fout die was opgetreden tijdens het uitvoeren van de `action` niet werd doorgegeven waardoor het uitvoeren van opvolgende `actions` gewoon door ging. Dit is niet het juiste gedrag! De Fulfilment werd altijd afgebroken in de loop waarna de uitvoering van de hele loop voor een opvolgend record werd gestart.
Met deze update is het originele gedrag als er geen `onfailure` handler is weer hersteld!

*** 
## v5.0.8 - 2024-07-22
### Fixed
- Een issue met API calls waarbij de CacheSeconds0 werd gebruikt leverde errors. Dat is in deze release opgelost.

*** 
## v5.0.7 - 2024-07-22
### Fixed
- Fix voor een probleem met Excel file caching die ervoor zorgde dat opvolgende `actions` de file niet konden gebruiken vanwege een Fil I/O locking.

*** 
## v5.0.6 - 2024-07-22
### Fixed
- Vanwege issues met Excel file caching is in deze versie de cache uitgeschakeld zodat fulfilment batches de files kunnen emailen. Dit heeft wel impact op de performance omdat er nu veel meer file I/O wordt gedaan. Een betere fix is incoming.

*** 
## v5.0.5 - 2024-07-16
### Fixed
- Fix voor weergave van datetime velden die een `null` waarde bevatten. Deze worden nu als lege string waarde afgebeeld.

*** 
## v5.0.4 - 2024-04-25
### Fixed
- Door recente aanpassingen werden log regels niet altijd vorrect voorzien van waardes. In deze release is dat grotendeels gefixt waardoor logging weer beter gebruikt kan worden voor probleem opsporing.

*** 
## v5.0.3 - 2024-04-03
### Changed
- Update library ClosedXml om zo de laatste versie van OpenXml (Word en Excel) te ondersteunen.

*** 
## v5.0.2 - 2023-12-07
### Fixed
- Een probleem in de errorhandling icm `onsuccess` en `onfailure` doorgevoerd weaardoro het aantal incorrecte errors drastisch lager zal worden.

*** 
## v5.0.1 - 2023-07-26
### Fixed
- Herstel van het `ReferenceId` veld in de logging
