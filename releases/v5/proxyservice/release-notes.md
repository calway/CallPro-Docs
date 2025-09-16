# ProxyService Release Notes
Dit zijn de Release Notes voor het ProxyService. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.18 - 2025-09-10
### Changed
- Interne wijzigingen aan de logging en tracing

***
## v5.0.17 - 2025-09-05
### Changed
- Obsolete alle v1 endpoints.

*** 
## v5.0.16 - 2025-09-03
### Changed
- Extra logging en kleine wijziging in de default rate-limiting voor gespreksopnames. Nu 5 opnames tegelijkertijd in een window van 10 seconden.

*** 
## v5.0.15 - 2025-08-29
### Fixed
- Fix voor een configuratiefout in de ratelimiting defaults die ervoor zorgde dat met lagere limits werd gewerkt dan waren ingesteld.

*** 
## v5.0.14 - 2025-08-19
### Changed
- Wijzigingen aan de v2 Recording endpoint zodat deze gebruikt kan worden door de Resource Explorer. Dit is een voorbereiding voor het omzetten van Recordings uit CallProPortal naar de ProxyService

*** 
## v5.0.13 - 2025-06-04
### Changed
- Interne wijzigingen aan de logging

*** 
## v5.0.12 - 2024-12-05
### Added
- Nieuw recording endpoint om een opname to downloaden. Tevens zijn enkele interne aanpassingen doorgevoerd mbt de toegang tot de fysieke opnames om alles over de verschillende modules uniformer te maken.
- Eenvoudig zoek endpoint om entries uit een periode met optioneel een status op te halen. Deze gaat mogelijk in de toekomst veranderen.

***
## v5.0.11 - 2024-10-14
### Changed
- Toevoegen Pipeline behaviour voor Logging en Tracing voor de v2 endpoints

***
## v5.0.10 - 2024-09-27
### Fix
- Bij het markeren voor RVV werd strikt gecontroleerd of het suppressielijst gedrag op de bellijst aan staat. Dit is niet de intentie omdat deze API wordt opgeroepen vanuit de telefonie waar een beller aangeeft zich voor RVV af te melden. Dat wij dit gedrag op de ebllijst niet aan hebben zou dan geen blokkade mogen zijn.

*** 
## v5.0.9 - 2024-09-25
### Fix
- Rebuild vanwege sommige klanten die een oude SQL Server gebruiken die geen tls1.2 of tls1.3 support heeft. 

*** 
## v5.0.5 - 2024-08-02
### Fix
- In de nieuwe v2 Entry Patch endpoint werd een verkeerde validatie gedaan waardoor het niiet mogelijk was om de `callbackAgentId` te zetten. In deze versie is dat gefixt.

## v5.0.4 - 2024-07-31
### Fix
- Bij het meegeven van een ongeldige `statusId` gaf de api ene exception, in plaats van een nette error response. Dat is nu gefixt.


## v5.0.3 - 2024-07-17
### Changed
- De api geeft nu status 201 Created terug na het succesvol aanmaken van een nieuwe entry conform de REST standaard.

## v5.0.2 - 2024-07-17
### Changed
- Betere api results met standaard error response.

## v5.0.1 - 2023-07-26
### Added
- Eerste officiele v5 release

