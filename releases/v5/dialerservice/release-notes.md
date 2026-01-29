# DialerService Release Notes
Dit zijn de Release Notes voor het DialerService. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.8 - 2026-01-29
### Fixed
- Door de aanpassingen in de vorige versie 5.0.7 kwam een bug aan het licht die al heel lang aanwezig is maar nooit eerder optrad. Afhankelijk van de belasting van de dialerservice kon een concurrency probleem optreden waardoor de service crasht en opnieuw start. Bellers merken dit doordat
ze naar het pauze scherm worden teruggezet bij het afcoderen van de huidige call en zich dan opnieuw moeeten aanmelden.

***
## v5.0.7 - 2026-01-23
### Changed
- Dit is een onderhoud release waar oud optioneel gedrag is verwijderd en nu het standaard gedrag is geworden. Deze versie is nodig om in de scriptmodule vanaf v5.0.24 het belvloer overzicht correct af te beelden.

***
## v5.0.6 - 2025-09-19
### Changed
- Interne wijzigingen met het opruimen van feature switches voor functionaliteit en toevoegen van tracing support voor logs.

*** 
## v5.0.5 - 2025-09-05
### Changed
- Met deze versie is ondersteuning voor Asterisk 22 toegevoegd. 

*** 
## v5.0.4 - 2024-09-25
### Fixed
- Bij het maken van de vorige versie container was een bepaalde dll niet meegekomen. Dit is de fix

*** 
## v5.0.3 - 2024-09-23
Rebuild vanwege sommige klanten die een oude SQL Server gebruiken die geen tls1.2 of tls1.3 support heeft. 

