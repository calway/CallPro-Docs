# CallProPortal Release Notes
Dit zijn de Release Notes voor CallProPortal. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v4/release-notes.md) te vinden.

<br/>

***

<br/>

## v4.3.2.57 - 2021-09-14
### Fixed
- Fix audioplayer weergave issue door update in Chromium player
### Changed
- Login pagina cleanup. Oude tekst verwijderd die niet echt iets toevoegt.

***
## v4.3.2.56 - 2021-06-01
### Fixed
- Sommige api endpoints konden anonymous worden opgeroepen. Nu kan dit alleen met authentication.

***
## v4.3.2.55 - 2021-05-19
### Fixed
- Lijst met agenda's in de afsrpaken pagina toonde altijd de eerste 50, bij filteren kwamen hier niet meer resultaten bij maar 
werd binnen deze eerste 50 gefiltert.

***
## v4.3.2.54 - 2021-05-11
### Changed
- First en LastCall data toegevoegd aan Wachtrij informatie voor zodat 'average calls/hour' kan wordne berekend.

***
## v4.3.2.53 - 2021-03-23
### Changed
- Dropdown combobox controls geven twee kolommen weer in plaats van ee nopgemaakte string om de leesbaarheid te vebeteren.

***
## v4.3.2.52 - 2021-03-23
### Changed
- Fulfilmentvalidatie houdt ook rekening met de rechten van de ingelogde gebruiker en laat alleen bellijsten zien waar de gebruiker toegang voor heeft.

***
## v4.3.2.51 - 2021-03-08
### Changed
- Verbetering van zoeken belopdrachten op basis van telefoonnummer.

***
## v4.3.2.50 - 2021-03-05
### Fixed
- Enkele onderdelen deden geen check of de ingelogde gebruiker wel toegang had tot bellijsten en gaven ongeacht de security-role settings resultaten
van alle bellisjten terug. Nu gaan de odnerdelen Recordings, Het hele menu analyse (op de webparts na) en Zoeken goed en geven alleen resultaten terug 
van bellijsten waar de ingelogde gebruiker toegang toe heeft.

***
## v4.3.2.47 - 2020-07-07
### Changed
- Audioplayer "download" optie weer geactiveerd. Hoewel deze vanwege AVG was uitgeschakeld is het technisch alsnog mogelijk om vanuit de browser de gedownloadde stream op te slaan.
Voorlopig de downlaod button weer geactiveerd. Voor de toekomst wordt gekeken of we deze functie achter een security optie kunnen plaatsen. Technisch is het altijd mogelijk om
een opname die kan worden afgespeeld ook te downloaden.

***
## v4.3.2.46
### Fixed
- Gespreksonames van een agent webpart honoreerde de geselecteerde agent niet waardoor alle opnames getoond werden. Nu wordt deze paramater wel toegepast en is de lijst correct beperkt
- Extra fix voor caching de Cache key gebruikte geen parameters en was dus page-wide waardoor wijzigingen in de paramaters soms niet werden getoond totdat de cache invalid werd.

***
## v4.3.2.45
### Fixed
- Schedule had en probleem bij het instellen van statussen doordat statussen en en statusgroepen eigen unieke ID waarden hebben en hierdoor overlap kan ontstaan. 
Bij een upgrade van een klant bleek dit te zijn ontstaan en kwam deze issue naar boven.

***
## v4.3.2.44
### Changed
- Fulfilment validatie slaat nu de notitie ook op bij de laatste attempt zodat dit in de history bewaarde blijft.

## v4.3.2.43 - 2020-04-02
### Fixed
- Queue webparts gebruiken nu de queueid als paramater in plaats van de queue naam

***
## v4.3.2.42 - 2020-03-05
### Fixed
- bmnr handler gelijkgetrokken met CallProProxy versie. Vanaf v4.3.3 wordt deze verwijderd uit CallProPortal. 

***
## v4.3.2.41 - 2020-03-02
### Fixed
- Fix voor fulfilment validatie waar het afspelen van opnames niet meer werkte na de recente aanpassing van de audioplayer. 

***
## v4.3.2.41 - 2020-03-02
### Changed
- Terugdraaien van eeen eerdere aanpassing waarbij de opnames inline in de pagina werde nafgespeeld. Dit blijkt met de werkwijze van meerdere gebruikers erg onhandig. Ze openen losse opnames in een venster en zijn vrij om in de opnamelijst dan te bladeren zonder dat dit het afspelen beinvloed.

***
## v4.3.2.40 - 2020-02-20
### Changed
- Aanpassing van de gespreksopnames functie. Opnames worden nu inline in de pagina afgespeelt met de nieuwe audioplayer control.

***
## v4.3.2.38 - 2020-01-21
### Changed
- De audioplayer control aangepast naar een betere weergave met enkele extra opties voor afspeelsnelheid en skip +10 -10 seconden.

***
## v4.3.2.37 - 2019-11-11
### Changed
- We zoeken voor wachtrijen niet alleen naar directe campagne relatyies, maar ook omhoog in de campagne folder hierarchy.

***
## unreleased - 2019-06-21
### Changed
- Diverse resource keuzelijsten laten nu standaard ene top 50 zien en zoeken gaat al vanaf 1 teken.

***
## v4.3.2.31 - 2019-06-18
### Added
- SignalR conversie van diverse interne API's
- Agenda pagina robuuster gemaakt voor gebruikers die geen agenda rechten hebben
- Updates van àssets` folder en libman conversie
- Bootstrap 4
