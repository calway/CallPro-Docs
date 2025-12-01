# Autoscript Release Notes
Dit zijn de Release Notes voor het Autoscript. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.19 - 2025-12-01
### Fixed
- Met de vorige aanpassing was over het hoofd gezien dat de regex die wordt gebruikt om email adressen te controleren ook meerdere email adressen accepteert. Met de toevoeging van de DNS controle werkte dat niet meer. Deze fix lost dit probleem op, en nu werken meerdere email adressen gescheiden door een comma of punt-comma ook weer.

***
## v5.0.18 - 2025-11-27
### Fixed
- Op de email validatie nog een wijziging doorgevoerd omdat de check op A host records niet altijd werkt. Sommige grote bedrijven hebben hun email ook op sub-domeinen en daarvoor hebben ze dan mogelijk geen A host record, maar uiteraard wel een MX record.

***
## v5.0.17 - 2025-11-26
### Fixed
- Op de een of ander manier was het script nu standaard in Engels. Alle systeem teksten werden in het Engels weergegeven. De taalkeuze bij de Agent wordt nu weer goed toegepast.
- Extra check op de email validatie dat mocht Cloudflare een storing hebben dat de emails dan als correct worden gezien.

*** 
## v5.0.16 - 2025-11-25
### BREAKING
- Met deze versie van het autoscript wordt de oude IE11 MSHTML browser engine niet meer ondersteunt! Het is zover, we hebben nu async javascript functionaliteit gebruikt en het wordt te ingewikkeld om hiervoor onderscheidt te maken. Zorg ervoor dat op de Seats folder een variabele `WebView2Enabled` van type `boolean` met waarde `true` staat ingesteld zodat alle werkplekken de WebView2 (Chromium) engine gebruiken.

### Changed
- Bij foutieve invoer van een email adres bij gebruik van de `@F(Email)` functie wordt nu ook een validatiecontrole toegevoegd bij het afcoderen. Voorheen werd een controle uitgevoerd als het veld werd verlaten, maar het bleek dat het nog steeds mogelijk was om af te coderen en deze foutieve invoer te negeren. Dat zou met deze aanpassing nu niet meer mogelijk moeten zijn.
- Tevens in de email controle via een **cloudflare** API het domein gecontroleerd of dit een bestaand domein is. Zo kunnen typefouten in het domein beter worden herkend.

***
## v5.0.15 - 2025-09-16
### Fixed
- Issue in het pauze scherm waardoor de "Ververs Campagnelijst" knop niet meer werkte.
- javascript melding bij gebruikt functies over lodash ook verwijderd. De keuze om lodash te gebruiken voor zoveel mogelijk eigen functies is on hold gezet omdat de functionaliteit toch niet zo gelijk is als eerst leek.

***
## v5.0.14 - 2025-09-05
### Fixed
* Als de scriptvelden van type `Datum` of karakter velden die gebruik maken van de `@F(Date)` optie had de datepicker control die wordt gebruikt voor het invoeren van een datum via een calendar een bug waardoor de `Alleen lezen` scriptveld optie niet werkte.  Met deze fix wordt de control en de beide buttons wel uitgeschakeld zodat de gebruiker geen wijzigingen in de veldinhoud kan doen.
* Enkele javascript functies voor veld opmaak waren in juni omgezet naar het gebruik van de loDash library. Maar bij nadere inspectie bleken deze versies toch niet zo gelijk te zijn en o.a. internationale tekens te verwijderen en dubbele achternamen gescheiden door een streepje ook het streepje te verwijderen. Onze eigen functies waren nog zo gek niet.

***
## v5.0.13 - 2025-07-16
### Changed
* De AI gespreksnotitie kan worden geblokkeerd door `content policy violations`. In dat geval gebeurde er niks in de UI. Met deze aanpassing krijg je de melding die als `error` terugkomt van de service te zien.
* Performance optimalisaties waardoor het autoscript 30% sneller het script weergeeft.

***
## v5.0.12 - 2025-06-04
### Fixed
* In het antwoordservice script (answeringservice) hield het script geen rekening met de hoogte van de toolbar waardoor het bovenste deel van het script niet zichtbaar was, w.o. de eerste afcodeerstaussen.

***
## v5.0.11 - 2025-05-26
### Changed
* Velden die als verplicht zijn gemarkeerd in de scriptdefinitie worden nu bij de custom validatie meldingen genoemd, in plaats van als apart validatie popup venster. Dit geeft direct een compleet beeld van alle validatie problemen met de invoer.
* Performance optimalisatie voor met name inbound scripts.

***
## v5.0.10 - 2024-04-29
### Fixed
* Bij de conversie van de v2 endpoints was een fout geintroduceerd waardoor de belhistorie custom javascript niet meer werkte. Dit is nu opgelost.
### Changed
* De email validatie is uitgebreid met validatie van meerdere email adressen. De controle werkte voorheen alleen bij 1 email adres. Met deze aanpassing kunnen ook
meerdere email adressen gescheiden door een `,` of een `;` worden ingevoerd.

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