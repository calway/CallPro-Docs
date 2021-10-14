# Resource Explorer Releases
Dit zijn de Release Notes voor de Resource Explorer. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v4/release-notes.md) te vinden.

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

