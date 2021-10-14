# Resource Explorer Releases
Dit zijn de Release Notes voor de Resource Explorer. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v4/release-notes) te vinden.

<br/>

***

<br/>

## v4.3.2.24 - 2021-10-12

Dit is een kritische bugfix release.

### Fixed

#### **Scriptdefinitie veldnaam lengte bugfix**
Bij het wijzigen van de scriptdefinitie werd niet gecontroleerd of de veldnaam maximaal 25 tekens lang is waardoor bij het bijwerken van de bellijsten die zijn gebseerd op deze scriptdefinitie een mismatch kan ontstaan tussen het veld in de database (langer dan 25 tekens) en het veld dat uiteindelijk in de scriptdefinite wordt bewaard (maximaal 25 tekens).
Het resultaat is dat de betreffende bellijsten die zijn gebaseerd op deze scriptdefinitie niet meer bruikbaar zijn omdat de scriptdefinite velden `noemt` die fysiek niet in de datasbe staan odner die naam. 

<br/>

## v4.3.2.23 - 2021-10-07

In deze release zijn de volgende functies toegevoegd, gewijzigd of verbeterd.


### Changed

#### **Importdefinitie ne Scriptdefinitie aanmaken gecombineerd**
In deze release is het inrichten van een nieuwe campagne verbeterd door het maken van de importdefinitie en de scriptdefinitie te combineren. 
Een aangeleverd importbestand kan nu bij het maken van de importdefinitie ook direct worden gebruikt om een bijbehorende scriptdefinitie te maken.

<br/>


## v4.3.2.21-22 - 2021-09-10

In deze release zijn de volgende functies toegevoegd, gewijzigd of verbeterd.


### Changed

#### **Multi-select voor exporteren van bellijsten**
In deze release is de mogelijkheid toegevoegd om een export te doen voor meerdere geselecteerde bellijsten. Het is ook mogelijk om een bellijst-groep (folder) te gebruiken om alle bellijsten in die bellijst-groep te exporteren. Voorwaarde voor dit gedrag is dat alle gekozen bellijsten *compatible* zijn met de gebruikte exportdefinitie.

#### **Excel bestanden importeren**
Het nieuwe import type "Excel" voegt een native ondersteuning voor Excel bestanden toe. Het is niet nodig om de juiste Excel ODBC drivers te installeren.

#### **Import preview weergave instelbaar**
Een nieuwe instelling in het control panel `Systeem\Geavanceerd\Import/Export\Maximaal aantal records bij import preview` bepaald of alle, of een beperkt aantal records in de import preview worden weergegeven.
Om het doorlopen van de preview te verbeteren is ook een zoek optie toegevoegd. Met <kbd>CTRL+F</kbd> kan worden gezocht in de import preview wat met name bij veel records nuttig is.

#### **Import preview data validatie weergave**
In de import preview worden nu voor bepaalde datatypes formaat fouten visueel zichtbaar gemaakt zodat eerder kan worden herkend dat er iets mis is met het importbestand.

#### **Verbeterde ondersteuning voor weergave kolommen in lijsten**
Op diverse plaatsen is de "Kiezen kolommen..." context-menu optie verbeterd. Als het resource-type bekend is kan op meer plaatsen gebruik worden gemakt van de specifieke kolommen die gelden voor het betreffende resource-type.

#### **Weergegeven bestandsnamen snel openen**
In schermen waar bestandsnamen worden afgebeeld kan dit bestand door middel van een dubbel-klik worden geopent. Ook kan vanuit het context-menu de bestandslocatie worden geopend in de Windows File Explorer.

***
**In de periode 2019-07-10 t/m 2021-09-10 ontbreken de release-notes. In deze periode is ook de versienummering gewijzigd. Mogelijk wordt deze later nog toegevoegd vanuit de version control notes.**
***
## v4.3.874 - 2019-07-10
- Bij het wijzigen van een Seat in de Resource Explroer volgt een waarschuwing als de extensie die is gebruikt ook al bij andere seats is gebruikt. 
Er zijn legitieme situaties dat dit kan voorkomen maar het is beter om ene extensie maar 1 keer te gebruiken per Seat.

***
## v4.3.847 (4.3.2) - 2019-03-25
### Changed
- In ID zoekvelden wordt nu selectonentry gebruikt om de invoer en het plakken van ID nummers te verbeteren. Voorheen was het niet altijd makkelijk om snel een waarde te plakken vanwege vreemd cursor positie gedrag bij het klikken in een veld van FoxPro.
### Fixed
- Bij uitlezen van de bellijst property in javascript (zowel via goCallpro object als via nieuwe window.external methode) trad bij het uitvragen van de GetCallList() een "automation not supported" error op.

***
## v4.3.700 (4.3.2) - 2018-08-01
### Added
- Ondersteuning voor "agent werktijd" en "Campagne facturabel" setting op de pauze registraties.
- Extra filter optie aan de rapprtages toegevoegd voor alle agenten behalve systeem/dialer. 
### Fixed
-- De oproep van een javascript functie `SetCallproAutoSelectStat` hersteld. Deze werd niet meer opgeroepen in voorgaande versies.

***
## v4.3.403 (4.3.1) - 2018-05-15
### Changed
- Bij het importeren wordt na 10000 geweigerde records het logbestand niet verder uitgebreid.
### Added
- Extra optie "ANNOUNCE" om bij een blind transfer een audio fragment af te spelen voordat de doorschakeling wordt gedaan.
- Mogelijkheid toegevoegd om een gemaakte opname te verwijderen vanuit de interface

***
## v4.3.362 (4.3.1) - 2018-05-09
### Changed
- In de Resource Explorer worden "gedisablede" resources nu grijs afgebeeld zodat sneller te zien is welke resources zijn uitgeschakeld. 
- Verbetering bij weergave van de status van koppelingen. Nu wordt altijd de juiste status afgebeeld als de resource uitgeschakeld is, maar de koppeling zelf niet. Dit wordt nu correct als uitgeschakeld afgebeeld.

***
## v4.3.337 (4.3.1) - 2018-03-08
### Added
- Extra optie om bij het wijzigen van de status van een belopdracht (Wijzigen belodprachten) te kiezen welke belpoginge wordt bijgewerkt. Voorheen werd altijd de laatste belpoging aangepast, maar in sommige situaties, als de dialer al weer een belpoging heeft gedaan, moest een eerdere belpoging worden bijegwerkt om een correcte goed te kunnen doorvoeren. Nu kan zelf worden bepaalde welke belpoging moet worden aangepast.
### Fixed
- De teller NrOfNoReach werd niet op 0 gezet als er wel iemand bereikt was ( ie. een terugbellen of verwerktresultaat).
- In de rapportage trad een fout op als bij een tijdkolom ene filter werd gebruikt op status. Er ontstond een illegale filter expressie waardoor geen resultaten werden gevonden.

***
## v4.3.333 (4.3.1) - 2018-02-08
### Fixed
- De Gewijzigd datum ewrd niet goed gezet bij het wijzigen van resource variabelen in het eigenschappen scherm.
