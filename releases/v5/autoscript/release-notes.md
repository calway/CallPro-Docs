# Autoscript Release Notes
Dit zijn de Release Notes voor het Autoscript. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.9 - 2025-04-23
### Changed
* Interne aanpassing: Er zijn nieuwe v2 endpoints toegevoegd die json data in camelCase formaat teruggeven. De bestaande (v1) endpoints geven nog steeds PascalCase terug. Met deze aanpassing sluit he tAPI resultaat beter asan bij wat gebruikelijk is.

***
## v5.0.8 - 2025-02-12
### Changed
* Verbetering van de @F(Email) scriptveld controle functie zodat email adressen met accent-tekens ook niet worden geaccepteerd.

***
## v5.0.7 - 2025-02-07
### Added
* De mogelijkheid om de gespreksnotitie die de agent invult door een AI kun laten controler op spel- en type fouten en schrijfstijl. De standaard prompt is redelijk simpel:
> Als AI assistent bekijk je gespreksnotities van een call center agent. Je corrigeert deze gespreksnotitie op type- en spelfouten en corrigeert het taalgebruik naar een semi-formele stijl. Alle correcties zijn in het Nederlands.

* Je kunt een eigen prompt maken door op de scriptdefinitie (of een scriptdefinitie folder) een variabele `SCRIPT.EntrynoteSpellcheckPrompt` te maken van type `Memo` met een alternatieve prompt.

> **AI Transcriptie werkt op dit moment alleen voor klanten die ook al gebruikmaken van Gesprekstranscriptie.**

### Fixed
* De `campagnelijst verversen` knop in het pauze scherm werkte niet. Dit is opgelost.
* Oplossing van een probleem uit versie 5.0.6 die ervoor zorgde dat script variabelen niet goed werden uitgelezen en daardoor ontbrekende script functionaliteit kon opleveren. Zo staan afcodeer validaties meestal in de variabele `SCRIPT.HEADER` die dus niet werd overgenomen in het script waardoor deze validaties niet werden uitgevoerd, wat weer resulteerde in het niet verschijnen van deze gesprekken in de fulfilment validatie, maar het direct versturen van de emails zonder verder controle doro supervisie.

***
## v5.0.6 - 2025-01-08
### Changed
* Mogelijkheid om met de `@F(Email)` optie een email adres te controleren op geldigheid. Dit is alleen een invoer geldigheid, niet perse een bestaand email adres!
* Diverse buttons voorzien van een `tabindex="-"` zodat deze elementen worden genegeerd als je met <kbd>TAB</kbd> door de velden loopt.

***
## v5.0.5 - 2024-09-23
Op het leaderboard wordt nu optioneel de resterende beltijd voor vandaag getoond. Hiervoor dient op de `Campaigns` folder een variabale `Leaderboard..TargetAgentTimePerDay` van type Karakter die het aantal uren weergeeft dat gebeld moet worden. Een getal geeft het aantal dagen aan, dus `10` geeft aan 10x24 uur. Alternatief kan ook `14:00` worden gebruikt om aan te gaven dat erde doelstelling 14 uur is.

***
## v5.0.4 - 2024-09-19
Rebuild vanwege sommige klanten die een oude SQL Server gebruiken die geen tls1.2 of tls1.3 support heeft. 

***
## v5.0.3 - 2024-07-04
In deze versie is de `@F(Url)` feature aangepast zodat het juiste venster kan worden geopend als gebruik wordt gemaakt van de -- op dit moment -- experimentele implementatie van de WebView2 browser engine.

En veel interne library updates die functioneel geen verschil maken.

***
## v5.0.2 - 2023-12-08
Alleen interne updates

***
## v5.0.1 - 2023-02-01
Dit is de eerste officiele release van deze versie. Door de vertragingen is het autoscript ook compatible gemaakt met eerdere CallPro versies w.o. 4.3.2 en 4.3.1