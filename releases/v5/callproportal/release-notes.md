# CallProPortal Release Notes
Dit zijn de Release Notes voor CallProPortal. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

***
## v5.0.29 - 2024-03-18
### Fixed
Een bug in de google authorization proces zorgde ervoor dat bepaalde gebruikers zich niet konden aanmelden. Dit probleem is nu opgelost. Dit probleem deed zich alleen voor bij specifieke registratie gegevens en werd bij slechts 1 CallPro klant gemeld. Omdat dit een erg storend probleem is die het synchroniseren van agenda's belemmerde is deze bugfix versneld uitgerold.

***
## v5.0.28 - 2024-03-14
### Fixed
* Als de Fulfilment validatie in twee Browser vensters open was  erd bij het opslaan een van de twee overschreven met de andere! Met deze update is het probleem met het gebruik van meerdere vensters opgelost.

***
## v5.0.27 - 2024-02-28
Ondersteuning voor keuzelijsten in het script waarvan de data uit een json of een externe url komt. Met CallPro 5.0 is deze toevoeging gedaan, maar met name de Fulfilment validatie kon deze gegevens nog niet correct weergeven. Er worden twee soorten json data ondersteunt.
```json
[
    {
        "id": "Unieke id",
        "text": "Weergave label"
    },
    ...
]
```

Het tweede formaat is hetzelfde formaat dat de <a href="https://select2.org/data-sources/formats" target="_blank">Select2 jQuery</a> html control gebruikt:
```json
{
    "results": [
        {
        "id": "Unieke id",
        "text": "Weergave label"
        },
        ...
    ]
}
```

***
## v5.0.26 - 2024-02-07
Fix voor queuemonitoring die geen wachtrijen meer weergaven. Met deze update werkt het weer. 

***
## v5.0.21-25 - 2024-01-20-2024-01-29
Diverse updates vanwege Google App verificatie eisen. 

***
## v5.0.20 - 2024-01-19
De Fulfilmentvalidatie module is versneld door de lijst met te controleren belopdrachten nu te delen over alle ingelogde gebruikers. Zo kan er ook als meerdere mensen fiatteren, elkaars fiatteren meteen oppakken. Wel blijven opletten dat je niet beide dezelfde controleert!

***
## v5.0.19 - 2024-01-19
Het Google App verificatie process vroeg om extra informatie op ene pagina die in de App wordt genoemd met uitleg over de Agenda synchronisatie. In deze update wordt zo'n pagina toegevoegd, hopelijk is het nu goed!

***
## v5.0.18 - 2024-01-18
Extra zoeken optie voor gespreksopnames. Er kan nu naar tekst gezocht worden in het notitieveld van de belopdracht, en de AI gesprekstranscriptie als die is gemaakt.

***
## v5.0.17 - 2024-01-12
In deze versie is een aanpassing doorgevoerd voor de Agenda synchronisatie autorisatie. Er zat een bug in dit onderdeel waardoor Google calendars niet konden worden geregistreert voor synchronisatie. Vanaf deze versie icm Calendarsync v5.0.4 werkt dit nu wel.

***
## v5.0.16 - 2023-12-20
Fulfilment validatie is soms erg traag. In deze versie is hier een  verbetering in aangebracht. Door de manier waarop deze module werkt blijft het een traag onderdeel.

***
## v5.0.15 - 2023-08-08
Uitbreiding gespreksopname weergave met richting van het gesprek (inbound of outbound). Voor campagnes die zowel inbound als outbound worden gebruikt is het nuttig om te kunnen zien op het gesprek en de opname is ontstaan uit een inbound of outbound call.

In de draaitabel voor belresultaten webpart zijn extra kolommen toegevoegd. Tevens is voor het opslaan van templates de mogelijkheid toegevoegd om ook de sorteervolgorde van de kolom en rij velden vast te leggen.

***
## v5.0.12 - 2023-07-04
Dit is een non-breaking database wijziging die nodig is om nog niet aangekondigde functionaliteit te kunnen gebruiken. In deze versie is ondersteuning toegevoegd voor de weergave van de `Alpha` gesprekstranscriptie en AI analyse. Deze functionaliteit is nog in een erg vroeg stadium en de exacte invulling ligt nog niet vast. 
> Voor gebruikers die deze functionaliteit in dit vroege stadium al willen inzetten, neem contact op met j.bennink@calway.nl. 

### Changed
- Gespreksopname audiospeler is uitgebreidt met weergave van een gesprekstranscriptie, een gesprekssamenvatting, en enkele per scriptdefinitei instelbare vraag- en antwoorden.
- De fulfilment validatie is aangepast om ook de nieuwe audio speler te gebruiken.

***
## v5.0.10 - 2023-06-01
### Fixed
 - Kleine code changes en optimalisaties
 - Consolidatie release

***
## v5.0.9 - 2023-05-30
### Fixed
- Een probleem bij specifieke script inrichting plugins met de signalr verbinding opgelost.
- Tevens verwijderd deze versie functionaliteit die al langere tijd als obsolete is aangegeven, w.o. Informatiebord.

***
## v5.0.8 - 2023-05-30
### Fixed
- Een issue met de weergave van velden in de fulfilment validatie door een bootstrap update is opgelost
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
