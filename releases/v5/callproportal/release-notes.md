# CallProPortal Release Notes
Dit zijn de Release Notes voor CallProPortal. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***

<br/>

***
## v5.0.9 - 2023-06-01
### Fixed
- Een probleem bij specifieke script inrichting plugins met de signalr verbinding opgelost.
- Tevens verwijderd deze versie functionaliteit die al langere tijd als obsolete is aangegeven, w.o. Informatiebord.

***
## v5.0.8 - 2023-05-30
### Fixed
- Een issue met de weergave van velden in de fulfilment validatie door een boorstrap update is opgelost
- Login issue opgelost voor nieuwe 5.0 databases

***
## v5.0.7 - 2023-03-01
## Changed
- Het is nu mogelijk om gebruikers van CallProPortal op gespreksopnames beperkte rechten te geven voor niet alleen bepaalde bellijsten, maar ook binnen bellijsten voor bepaalde gebruikers.

***
## v5.0.6 - 2023-02-01
### Changed
- Gespreksopnames maken gebruik van de html audio control. Hierdoor hoeven opnames niet eerst geconverteerd naar mp3 en zijn er meer afspeel mogelijkheden zoals de afspeelsnelheid.

### Breaking
- `services/ValidateEmail` is verplaatst, de nieuwe locatie is `api/v1/Services/ValidateEmail`
- `services/bmnr.ashx` is verwijderd omdat het bel-me-niet register in Nederland niet meer actief is.
- `Telephony/bmnr` is verwijderd omdat het bel-me-niet register in Nederland niet meer actief is.
- `Telephony/rvv` is verwijderd. Gebruik in de plaats hiervan het ProxyService endpoint `Ivr\MarkEntryAsRVV` Kijk in de ProxyService swagger pagina voor informatie over dit endpoint. **Bij upgrade is ook een wijziging nodig in het Asterisk dialplan**

Onderstaande endpoints zijn interne endpoints die niet in gebruikt zouden moeten zijn bij klanten.

- `services/GetResourcePicture.ashx` is verplaatst nar `Migration/GetResourcePicture`
- `/RecordDownloadHandler.ashx` is verplaatst naar `Migration/GetRecording`
- `RefactorMe_GetGridDataExportToXls.ashx` is verplaatst naar `Migration/GetGridDataExportToXls`
- `/calendar/OutlookHandler.ashx` is verplaatst naar `Migration/GetOutlookVCalendar`

- De bel-me-niet webparts zijn verwijderd. Deze moeten voor of na de upgrade van de betreffende pagina's worden verwijderd.
- De zoeken in bel-me-niet registraties pagina is verwijderd.

- In de callpro database is de tabel 'RegDoNotCall' met alle ivr registratie gegevens verwijderd. Voor klanten met eigen integraties met deze tabel moet dit worden opgeruimd.

- Restanten van de Engage Gamification Module zijn verwijderd. Het gaat om de tabellen 'AchievementDefs`, ``AgentAchievementCycles` en `AgentAchievements`. Voor klanten met eigen integraties met deze tabellen moet dit worden opgeruimd.
