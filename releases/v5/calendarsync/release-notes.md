# CalendarSync Service Release Notes
Dit zijn de Release Notes voor het CalendarSync Service. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

*** 
## v5.0.9 - 2024-06-12
### Fix
- Probleem opgelost waardoor afspraken die vanuit CallPro naar Exchange werden gesynced via Microsoft Graph, **niet** werden hersteld als ze in Exchange werden verwijderd. Dit is het standaard gedrag wat nu is hersteld.
### Change
- Grote upgrade van de Microsoft Graph API 4.54 => 5.56. Dit leverde veel interne wijzigingen. Hou sync gedrag in de gaten en als er iets is gewijzigd laat het ons weten. 

***
## v5.0.8 - 2024-05-06
- Fix Exchange OAuth sync die geen Booking agenda's herkende waardoor tenants die dit gebruiken niet konden worden gesynchroniseert.

***
## v5.0.7 - 2024-04-25
### Fix
- Logger informatie verbeterd, dit is alleen intern voor Calway zichtbaar

***
## v5.0.6 - 2024-04-24
### Added
- Afspraken werden altijd direct gesynchroniseert. Echter als een afspraak voor Fulfilment validatie in aanmerking komt wil je de synchronisatie uitstellen tot na deze validatie. Dit werkt voor zowel Microsoft Exchange, Microsoft 365 Graph API als voor de Google API synchronisatie. Met deze update herkend de calendarsync dat een belopdracht nog wacht op validatie voor de afspraak, hiervoor wordt het speciale veld "EXP_APP" gebruik dat dan is gezet.

***
## v5.0.5 - 2024-02-08
### Added
- Toevoegen van het synchroniseren van herhalende afsrpaken die in Google worden gemaakt. Dit is dezeflde functionaliteit die in versie 5.0.2 is toegevoegd voor Microsoft 365 Graph API.

***
## v5.0.4 - 2024-01-12
### Fixed
- In deze versie is de Google Calendar synchronisatie hersteld. Vanaf nu, icm CallProPortal v5.0.17, werkt dit nu wel.

***
## v5.0.2 - 2023-09-28
### Added
- Toevoegen van het synchroniseren van herhalende afspraken die in Exchange worden gemaakt. Voor versie 5.0.2 werden deze herhalende afspraken uit Exchange **niet** naar CallPro gesynchroniseert doordat de EWS API gegevens niet compatibel waren met CallPro. De Microsoft 365 Graph API geeft deze gegevens veel beter terug waardoor het nu mogelijk is geworden om deze synchronisatie voor de Microsoft 365 Graph API koppeling toe te voegen.
- Toevoegen van een optie om CallPro afspraken direct als Teams meeting aan te maken voor de Microsoft 365 Graph API koppeling. Op agenda nivuea kan een variabele `calendarsync.IsOnlineMeeting` worden gemaakt die op `TRUE` wordt gezet om aan te geven dat een Teams meeting gemaakt moet owrden. Hierbij kan ook gebruik worden gemaakt van scriptvelden zoals `%SCRIPT.AFSPRAAK_TYPE \IF"ONLINE"?TRUE:FALSE%` 
- Toevoegen van de mogelijkheid om bij de afspraak meteen de prospect/lead/klant uit te nodigen door deze als `RequiredAttendee` of `OptionalAttendee` vast te leggen bij de afspraak. Hiervoor wordt het email adres van de prospect/lead uit de belopdracht gebruikt. Dit kan wordne ingesteld door de `calendarsync.RequiredAttendees` en/of `calendarsync.OptionalAttendees` variabele bij de Agenda in Callpro vast te leggen. Bijvoorbeeld als `%SCRIPT.NAME_EMAIL%` om het email adres van de contactpersoon te gebruiken. Deze optie is toegevoegd voor de Microsoft 365 Graph API koppeling.

***
## v5.0.1 - 2023-02-01
Dit is de eerste officiele release van deze versie. 
