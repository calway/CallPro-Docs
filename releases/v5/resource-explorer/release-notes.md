# Resource Explorer Releases
Dit zijn de Release Notes voor de Resource Explorer. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.6 - 2023-10-17
### Fixed
- Extra applicatie icoon in Start menu voor Campagne Grid en Suppressielijsten import.
### Change
- In de Agendamodule is een calendar maand control toegevoegd voor snellere navigatie door de agenda.

***
## v5.0.5 - 2023-07-18
### Changed
- De icons in de toolbar zijn nu uniform van afmeting. Dit ziet er een stuk beter uit
### Fixed
- In de terugbeltijd expressie berekening die gebruikt wordt voor de status datum berekening, specifiek voor TimeAdd, konden door een fout geen minuten meer gebruikt worden. De syntax `TimeAdd=5m` (5 minuten) werd niet herkend als geldig, maar `TimeAdd=1h` (1 uur) nog steeds wel. Dit was een feature regressie bug die snel kon worden opgelost.

***
## v5.0.4 - 2023-07-17
In deze versie is een begin gemaakt met de mogelijkheid om meerdere eigenschappen vensters tegelijkertijd open te kunnen hebben, veel CallPro vensters zijn "modal" wat betekent dat als dit venster open is, geen enkel ander programma venster kan worden gebruikt tot dit venster is gesloten. Voor diverse gebruik scenario's is het handig als je meerdere vensters naast elkaar open kunt hebben, en kunt gebruiken.

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
