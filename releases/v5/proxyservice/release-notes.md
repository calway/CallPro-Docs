# ProxyService Release Notes
Dit zijn de Release Notes voor het ProxyService. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.10 - 2024-09-27
### Fix
- Bij het markeren voor RVV werd strikt gecontroleerd of het suppressielijst gedrag op de bellijst aan staat. Dit is niet de intentie omdat deze API wordt opgeroepen vanuit de telefonie waar een beller aangeeft zich voor RVV af te melden. Dat wij dit gedrag op de ebllijst niet aan hebben zou dan geen blokkade mogen zijn.

*** 
## v5.0.5 - 2024-08-02
### Fix
- In de nieuwe v2 Entry Patch endpoint werd een verkeerde validatie gedaan waardoor het niiet mogelijk was om de `callbackAgentId` te zetten. In deze versie is dat gefixt.

## v5.0.4 - 2024-07-31
### Fix
- Bij het meegeven van een ongeldige `statusId` gaf de api ene exception, in plaats van een nette error response. Dat is nu gefixt.


## v5.0.3 - 2024-07-17
### Change
- De api geeft nu status 201 Created terug na het succesvol aanmaken van een nieuwe entry conform de REST standaard.

## v5.0.2 - 2024-07-17
### Change
- Betere api results met standaard error response.

## v5.0.1 - 2023-07-26
### Add
- Eerste officiele v5 release

