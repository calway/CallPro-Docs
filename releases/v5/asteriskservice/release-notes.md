# AsteriskService Release Notes
Dit zijn de Release Notes voor het AsteriskService (dialer support service). Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

*** 
## v5.0.6 - 2025-12-09
### Changed
- Met de support voor Asterisk 22 zijn er extra events die we `zien` maar waar de AsteriskService niks mee doet. Dit werd als warning `Unknown Asterisk Message Received:` gelogged wat de logs onnodig vult. In deze versie zijn enkele events waar de AsteriskService niks mee doet op een ignore lijst gezet zodat ze niet meer gelogged worden.

*** 
## v5.0.5 - 2025-05-20
### Fixed
- In de vorige versie is bij he twijzigen ook gedrag veranderd waardoor Abandoned gesprekken niet meer als zodanig werden weergegeven in de rapportages en monitoring. Deze versie lost dit probleem op.

*** 
## v5.0.4 - 2025-04-11
### Changed
- Alleen interne wijzigingen

*** 
## v5.0.3 - 2024-09-25
### Fixed
- Bij het maken van de vorige versie container was een bepaalde dll niet meegekomen. Dit is de fix

*** 
## v5.0.2 - 2024-09-23
Rebuild vanwege sommige klanten die een oude SQL Server gebruiken die geen tls1.2 of tls1.3 support heeft. 

