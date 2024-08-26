# FulfilmentService Release Notes
Dit zijn de Release Notes voor het Fulfilment service.  Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

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
