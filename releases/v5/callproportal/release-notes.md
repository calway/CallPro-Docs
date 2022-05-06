# CallProPortal Release Notes
Dit zijn de Release Notes voor CallProPortal. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***

<br/>

## v5.0.0 - unreleased
***
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

