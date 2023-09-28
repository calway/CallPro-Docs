# CalendarSync Service Release Notes
Dit zijn de Release Notes voor het CalendarSync Service. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>


***
## v5.0.2 - 2023-09-28

### Added
- Toevoegen van het synchroniseren van herhalende afspraken die in Exchange worden gemaakt. Voor versie 5.0.2 werden deze herhalende afspraken uit Exchange **niet** naar CallPro gesynchroniseert doordat de EWS API gegevens niet compatibel waren met CallPro. De Microsoft 365 Graph API geeft deze gegevens veel beter terug waardoor het nu mogelijk is geworden om deze synchronisatie voor de Microsoft 365 Graph API koppeling toe te voegen.
- Toevoegen van een optie om CallPro afspraken direct als Teams meeting aan te maken voor de Microsoft 365 Graph API koppeling. Op agenda nivuea kan een variabele `calendarsync.IsOnlineMeeting` worden gemaakt die op `TRUE` wordt gezet om aan te geven dat een Teams meeting gemaakt moet owrden. Hierbij kan ook gebruik worden gemaakt van scriptvelden zoals `%SCRIPT.AFSPRAAK_TYPE \IF"ONLINE"?TRUE:FALSE%` 
- Toevoegen van de mogelijkheid om bij de afspraak meteen de prospect/lead/klant uit te nodigen door deze als `RequiredAttendee` of `OptionalAttendee` vast te leggen bij de afspraak. Hiervoor wordt het email adres van de prospect/lead uit de belopdracht gebruikt. Dit kan wordne ingesteld door de `calendarsync.RequiredAttendees` en/of `calendarsync.OptionalAttendees` variabele bij de Agenda in Callpro vast te leggen. Bijvoorbeeld als `%SCRIPT.NAME_EMAIL%` om het email adres van de contactpersoon te gebruiken. Deze optie is toegevoegd voor de Microsoft 365 Graph API koppeling.

***
## v5.0.1 - 2023-02-01
Dit is de eerste officiele release van deze versie. 
