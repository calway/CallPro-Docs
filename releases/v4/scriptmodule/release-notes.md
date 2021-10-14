# Scriptmodule Releases
Dit zijn de Release Notes voor de Scriptmodule. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v4/release-notes) te vinden.

<br/>

***

<br/>

## v4.3.2.92 - unreleased
***
## v4.3.2.91 - 2021-10-07
### Fixed
***
## v4.3.2.90 - 2021-07-05
### Fixed
-- Sessieid werden alleen bij de laatste attempt gezet bij meerdere belpogingen op dezelfde call.
***
## v4.3.2.89 - 2021-06-30
### Fixed
- Setuptijd werd niet goed gezet bij meerdere belpogingen in dezelfde call waardoor alle belpogingen dezelfde setuptijd kregen.

***
## v4.3.2.88 - 2021-05-27
## Changed
- Mogelijkheid toegevoegd voor de Agent om zijn wachtwoord te veranderen
- Waarschuwing als een leeg password wordt gebruikt. Vanaf v5.0 wordt een leeg password niet meer toegestaan.

***
## v4.3.2.87 - 2021-05-19

***
## v4.3.2.86 - 2021-05-17
### Changed
- Check op meerdere instanties van Scriptmodule gestart veranderd

***
## v4.3.2.85 - 2021-04-08
### Changed
- Extra interne variabelen toegevoegd voor betere support van de nieuwe RVB wetgeving

***
## v4.3.2.84 - 2021-03-29
### Changed
- Detectie van window positie op scherm, en of deze off-screen is aangepast.

***
## v4.3.2.83 - 2021-03-11
### Fixed
- Navigatie in calendargrid gaf exception

***
## v4.3.2.82 - 2021-03-02

***
## v4.3.2.81 - 2021-02-26

***
## v4.3.2.80 - 2021-02-16
### Fixed
- Betere afhandeling van computers die uit Hibernate/Sleep komen

***
## v4.3.2.79 - 2021-01-19

***
## v4.3.2.78 - 2021-01-13
### Fixed
***
## v4.3.2.77 - 2020-12-18
### Fixed
***
## v4.3.2.76 - 2020-08-18
### Fixed
***
## v4.3.2.75 - 2020-07-23
### Fixed
***
## v4.3.2.74 - 2020-07-20
### Changed
- Supprt menu item toegevoegd
***
## v4.3.2.73 - 2020-07-15
### Fixed
***
## v4.3.2.72 - 2020-07-13
### Fixed
***
## v4.3.2.71 - 2020-07-06
### Fixed
***
## v4.3.2.70 - 2021-06-15
### Fixed
***
## v4.3.2.69 - 2021-06-10
### Fixed
***
## v4.3.2.68 - 2021-06-09
### Changed
-- Usabality verbetering Entry Find module
***
## v4.3.2.67 - 2020-06-08
### Fixed
***
## v4.3.2.66 - 2020-05-28
### Changed
-- Versienummer controle bijgesteld voor auto-update process
***
## v4.3.2.65 - 2020-03-18
### Changed
- Fix met matching van uppercase die onbedoeld ook de veldwaarde naar uppercase zetten.

***
## v4.3.2.64 - 2020-02-25
### Changed
- Manual blending toegevoegd ivm Inbound campagne voor chat sessies

***
## v4.3.2.11 - 2019-03-06
### Changed
- We gebruiken nu een andere nummering voor versies
### Fixed
- Als het belopdracht een leeg telefoonnummer veld had dan bleef de dialer soms in een ongeldige state hangen waardoor het bellen niet meer automatisch doorging. 
- Bij inbound werkte de bellijst keuze niet als in een inbound campagne meerdere bellijsten stonden

***
## v4.3.824 (4.3.2) - 2019-02-26
### Added
- Als een agent naar pauze gaat en deze is gekoppeld aan een inbound campagne waarbij de agent de laatste agent is op die campagne dan volgt een extra waarschuwing zodat de agent zich bewust is dat hij/zij de laatste agent op de inbound campagne is. Dit om te voorkomen dat alle agenten op pauze gaan tijdens de openingstijden van een inbound campagne waardoor er niemand beschikbaar is om een gesprek te beantwoorden.
- Extra setting in "AgentDialModeProgressAudio" om aan te geven of ringback audio hoorbaar is voor de agent. Dit werkt uiteraard alleen bij preview- en autodialing.

### Changed
- Meer instellingen van venster worden bewaard in het windows register zodat venster op dezelfde plaats openene als waar ze het laatste stonden.

***
## v4.3.700 (4.3.2) - 2018-09-12
### Changed
- Mogelijkheid toegevoegd om de afspraakduur te wijzigen door het afspraakblok in de agenda te resiizen met de muis
- Bij het zoeken naar telefoonnummers wordt nu in alle telefoonnummervelden gezocht in plaats van alleen in het 1e veld.
### Fixed
- Sporadisch probleem met interne nummering van belpoging opgelost die een primary key vilocation opleverde bij het schrijven van de belpoging
- Bij het oproepen van een voor de agent onzichtbare status via de paramater SELECTSTAT ewrrd deze niet correct getoond. Dit is aangepast zodat via de scripting expliciet meegegeven statussen altijd selecteerbaar zijn.
### Not fixed
- Als in de FoxPro script client (legacy) de "Sql Client native 11.0" ODBC driver werd gebruikt dan werden memo velden niet opgehaald. Bekend prrobleem: https://www.tek-tips.com/viewthread.cfm?qid=1776880

***
## v4.3.431 (4.3.1) - 2018-09-05
### Changed
- Activiteit "ping" ingesteld van 15 naar 10 minuten zodat de database connectie bij cloud databases niet verloren gaat. Voorheen traden onnodig connectie problemen op door het opruimen van open connecties naar de database.

***
## v4.3.374 (4.3.1) - 2018-07-02
### Added
- Extra optie STOPALL om alle actieve opnames uit te schakelen. Deze optie is toegevoegd vanwege AVG/GDPR waarbij een persoon die gebeld is mondeling aangeeft geen toestemming te geven voor een opname.

***
## v4.3.339 (4.3.1) - 2018-02-07
### Fixed
- Een probleem met het inplannen van afspraken als de reistijdocntrole was uitgeschakeld is opgelost. Voorheen volgde een foutmelding "SetAddressLocation not found" waardoor geen afspraak kon wordne ingepland.

### Added
- Dialplan variablen worden nu vanuit het Asterisk diaplan doorgegeven via de dialer naar de scriptmodule en worden daar gematched met script velden. Bijvoorbeeld SYS_QUEUENAME.
