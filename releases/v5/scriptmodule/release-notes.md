# Scriptmodule Releases
Dit zijn de Release Notes voor de Scriptmodule. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.6 - 2023-10-17
### Fixed
- Bij het afcoderen via scripting werd de `MOVEENTRY` parameter genegeerd. De correcte werking van deze parameter is hersteld
- Bij het afcoderen via scripting werden alle status parameters  genegeerd en werden de op de status ingestelde instellingen gebruikt. Nu worden weer correct de via scripting ingestelde waarden gebruikt

### Change
- In de Agendamodule is een calendar maand control toegevoegd voor snellere navigatie door de agenda.

***
## v5.0.5 - 2023-07-18
### Fixed
- In de terugbeltijd expressie berekening die gebruikt wordt voor de status datum berekening, specifiek voor TimeAdd, konden door een fout geen minuten meer gebruikt worden. De syntax `TimeAdd=5m` (5 minuten) werd niet herkend als geldig, maar `TimeAdd=1h` (1 uur) nog steeds wel. Dit was een feature regressie bug die snel kon worden opgelost.


***
## v5.0.4 - 2023-07-17
In deze nieuwe versie is het dialer popup venster modeless gemaakt. Hierdoor kun je terwijl de dialer het nummer belt, maar er nog niet is opgenomen, toch al door het script scrollen en navigeren. Je kunt uiteraard **niet** afcoderen of andere systeemacties uitvoeren.
Voor scripts die langer zijn dan een scherm hoog is biedt dit meer vrijheid om alvast alles door te nemen. Ook scripts met meerdere tabbladen, of meerdere pagina's.

***
## v5.0.3 - 2023-03-01
Gebruikers op Windows 10 hadden veel problemen met automatische updates en installatie. Deze versie werkt alleen met het nieuwe developer certificaat en op zowel Windows 10 als Windows 11. Verwijder eerst voorgaande versies en installeer dan deze nieuwe versie.

*** 
## v5.0.2 - 2023-02-01
Door het verlopen van het developer certificaat werkten automatische updates niet meer. Deze versie gebruikt het nieuwe certificaat en ondersteunt op Windows 11 ook upgrade van het oude certificaat.

***
## v5.0.1 - 2022-02-01
Dit is de eerste officiele versie van deze client. Met deze versie gebruiken we https://installer.callpro.nl voor de installatie (voor Windows 10/11)

***
## v5.0.0 - unreleased
