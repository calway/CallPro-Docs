# Autoscript Release Notes
Dit zijn de Release Notes voor het Autoscript. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v4/release-notes.md) te vinden.

<br/>

***

<br/>

## v4.3.2.119 - 2021-10-08

### Changed
- metroui/leaderboard gebruikt nu campagne doelstelling parameters. De oude maatwerk `score.conversion` en `score.type` variabelen zijn niet meer nodig op de campagne.

***
## v4.3.2.118 - 2021-05-15
### Changed
- changed all references to goCallPro to use window.external in Javascript

***
## v4.3.2.117 - 2020-11-11
### Fixed
- Fixed breaking change in pagina's met pullmenu na update metroui naar laatste v3 versie

### Added
- Toevoeging van GetBirthDays endpoint in services voor ene lijst met agents die binnenkort jarig zijn.
- Added $scope scriptfields to the Script controller for future angular features

### Changed
- overrides.css grotendeels teruggedraaid naar default metroui gedrag voor meer wit ruimte om velden
- Leaderboard Agent en Campaignname velden van 50 naar 128 tekens zoals in Callpro ook bijgesteld
- Changed dateformat from dd/mm/yyyy to dd-mm-yyyy

***
## v4.3.2.116 - unreleased
***
## v4.3.2.115 - unreleased
***
## v4.3.2.114 - unreleased
***
## v4.3.2.113 - 2020-03-09
### Changed
- Kleine aanpassing van de LastResultAgent API zodat deze breder inzetbaar wordt.

***
## v4.3.2.112 - 2020-03-06
### Changed
- Fix voor weergave van Informatiebord info die op dezeflde plek als SCRIPT.HEADER werd weergegeven maar door de recente aanapssing van de sticky toolbar achter deze toolbar kwam te staan. Nu staat het weer keurig onder de toolbar binnen de script ruimte.

***
## v4.3.2.111 - 2020-02-26
### Changed
- Toevoegen extra fulfilment velden AGENT.PARENTID zodat we deze kunnen meegeven als "team" aanduiding bij API oproepen. Ook ENTRY.TELNR en ENTRY.NOTES werden toegevoegd.

***
## v4.3.2.110 - 2020-02-20
### Fixed
- CKEditor voorlopig teruggezet omdat meerdere gebruikers scripts hadden die dit nodig hebben en er anders veel scriptdefinities handmatig moetne worden bijgewerkt. Nieuwe planning is om dit vanaf v4.3.3 te verwijderen.
- Nieuwe pauze pagina weergave die de Informatiebord informatie regels als aparte tabbladen opneemt voor betere weergave.

***
## v4.3.2.109 - 2020-02-18
### Fixed
- Checkbox, dropdown en radio controls die geeen opties hadden gaven een foutmelding. Hoewel zo'n control zinloos is in het script omdat je niks kunt kiezen zou dit geen foutmelding moeten geven. 

***
## v4.3.2.108 - 2019-10-30
### Fixed
- Toolbar is nu fixed-top zodat als je in het script naar beneden scrollt de toolbar zichtbaar blijft. Zeker handig nu we CUSTOMTILE's kunnen weergeven met informatie, maar ook voor het ophangen van een gesprek.

***
## v4.3.2.107 - 2019-05-28
### Added
- `CUSTOMTILE1` en `CUSTOMTILE2` variabelen op script (SCRIPT), pauze(BREAK) en inbound(INBOUND) pagina's om ook in de Tile in de toolbar af te beelden.

***
## v4.3.2.105 - 2019-04-12
### Added
- QueueInfo api toegevoegd voor gebruik in de pauze, inbound en script pagina.
- Extra support voor `INBOUND.INFO` en `BREAK.INFO` om op beide pagina's direct onder de toolbar extra onderdelen zoals KPI tiles toe te voegen.

***
## v4.3.2.104 - 2019-04-10
### Fixed
- Probleem bij een inbound call met een script waar een Combobox control wordt afgebeeld. Doordat er geen "belopdracht" is maar wel wordt verondersteld ontstond een `null pointer reference`

***
## v4.3.2.102 - 2019-04-03
### Fixed
- Probleem met weer de combobox control en het toevoegen van meerdere items in een interne `Dictionary` wat resulteerde in een duplicate key exception bij het toevoegen van de tweede key.

***
## v4.3.2.101 - unrelease

***
## v4.3.2.100 - 2019-04-01
Vanaf deze versie krijgt het autoscript ook een versienummer met 4 segmenten.
### Fixed
- Probleem met de select2 dropdown control opgelost waarbij waarden die in case verschillen niet werde nherkend wat weer problemen gaf met angular waardoro bij het opslaan een te lange waarde in het veld werd gezet. "? string:M ?" voor een geslacht veld waar de waarde M in stond terwijl in de dropdown control m/v kleine letters werd gebruikt. Dit zou nu moeten zijn opgelost.
### Changed
- De ckeditor.js verwijderd uit de standaard scripts die worden geladen. Deze editor is erg groot/zwaar en om de laad tijd te optimaliseren wordt dit niet meer standaard geladen. De versie 4 zit nog wel in autoscript maar zal in de toekomst ook wordne verwijderd. Om ckeditor te gebruiken kan een referentie naar de cdn van dit product worden opgenomen. Meer informatie hierover is te vinden op de website van [CKEditor](https://ckeditor.com/ckeditor-4/download/)
- autoscript opties veld is nu in json formaat. Voorheen was dit een losse string, maar met deze versie proberen we de opmaak te formliseren. Voorlopig is het enige veld dat we herkennen `DisplayFormat` dat voorheen direct in het opties veld kon worden gezet.

```
{ 
    "Version": "1.0",
    "DisplayFormat": "<formaat>"
}
```

### Added
- Twee extra variabelen SCRIPT.TOOLBAR.CUSTOMTILE1 en SCRIPT.TOOLBAR.CUSTOMTILE2 die gebruikt worden om extra custom tiles in de toolbar af te beelden. CUSTOMTILE1 komt rechts van de CallHistory tile en CUSTOMTILE2 komt links van de Break tile. Hoewel het mogelijk is om elke html opmaak hier in te voegen moeten alleen "tiles" worden gebruikt om te voorkomen dat de toolbar opmaak in de war raakt. 

***
## v4.3.2 - 2019-03-12
### Added
- Ondersteuning voor select2 dropdown weer teruggebracht

***
## v4.3.2 - 2019-03-01
### Added
- Ondersteuning voor STATUS.COLLAPSE bij de belopdrachtstatus weergave toegevoegd via een variabele. Aaneengesloten statussen worden als Dropdown control weergegeven.
- ondersteuning voor mergetool-syntax op nog meer plaatsen tijdens het renderen van het script zodat HTML custom weergaves nog meer profiteren van de Callpro instellingen.
### Fixed
- Probleem opgelost met de `readonly` instelling op controls die niet meer werkte.
- select2 dropdown support teruggedraaid vanwege een issue met de weergave van de initiele waarde.
- Weergave van 12 kolom layout bijgesteld. Voorheen werd genormaliseerd naar 12 kolommen wat het onmogelijk maakte om niet de hele breedte van een regel te gebruiken. Nu worden de kolom breedtes altijd 1-op-1 overgenomen.

***
## v4.3.2 - 2018-11-22
### Changed
- Upgrade naar angular 1.6.6
- Meer database resultaat caching om de snelheid van de pagina te vergroten.
- Tijdens opbouwen van autoscript zijn nu de mergetool collecties zoals %SCRIPT.veld% en %ENTRY.veld%, %STATUS.veld%, %CAMPAIGN.veld% en %AGENT.veld% beschikbaar voor meer mogelijkhedn met customHTML control opbouw.
- url aanpassing

| oud | nieuw |
|---|---|
| script | MetroUI/script |
| break | MetroUI/break |
| inbound | MetroUI/inbound |
| antwoordservice/ | MetroUI/answeringservice |
| services/Leaderboard | MetroUI/leaderboard |

### Fixed
- Bel-me-niet button werd al getoond als een adverteerder was gezet. Nu wordt de module licentie gecheckt voor weergave.
- BREAK.DisableCampaignSelection werkt nu zoals bedoeld. Eerst wordt gekeken op de campagne, daarna op de Campaigns root.
- Placeholder ondersteuning teruggedraaid. Veel gebruikers vonden dit niet overzichtelijk.
- In de pauze pagina worden achter de campagne als groene tag het aantal terugbellers dat nu gebeld kan worden voor de ingelogde gebruiker getoond.
- Website icon bij @R(Url) optie gefixt.
- Fix voor calender control om de gekoze n datum weer leeg te maken.

***
## v4.3.1 - 2018-02-16
### Fixed
- Leaderboard.TeamColor werd niet altijd correct toegepast op het leaderboard.

***
## v4.30 - 2017-10-25
### Changed
- url aanpassing

| oud | nieuw |
|---|---|
| script.aspx | script |
| breakpauze.aspx | break |
| inbound.aspx | inbound |
| antwoordservice/default.aspx | antwoordservice/index |
| services/Leaderboard.aspx | services/leaderboard |
| services/weektargets.aspx | services/weektargets |
| services/wallboard.aspx | services/wallboard |
| services/slideshow.aspx | services/slideshow |

***
## v4.30 - 2017-05-02
### Added
- Support voor SMALL toolbar buttons.

***
## v4.30 - 2017-04-20
### Fixed
- Checkbox control render issue waardoor elke optie werd aangevinkt als er een optie werd aangevinkt door de ingebouwde angular support.
- Dropdownlist control render issue waarbij de waarde 'undefined' werd bewaard door de ingebouwd  angular support.
