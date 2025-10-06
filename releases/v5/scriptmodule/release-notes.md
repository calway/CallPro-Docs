# Scriptmodule Releases
Dit zijn de Release Notes voor de Scriptmodule. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.23 - 2025-10-06
### Fixed
- In de nieuwe Webview2 (Chomium) engine werd de script pagina scrollbalk naar de top teruggezet bij het klikken op hyperlinks in de pagina. Dit valt het meest op als er eerst naar beneden wordt gescrolled om de entrynote te lezen, en vervolgens op de `bellen` knop wordt gedrukt. De scrollbalk behoud nu zijn positie.

***
## v5.0.22 - 2025-10-01
### Changed
- De Scriptmodule sluit de ingelogde agent sessie af als de computer wordt afgesloten zonder CallPro netjes af te sluiten. Dit voorkomt onnodig crashed sessies als gebruiker de Scriptmodule niet afsluiten voordat ze hun computer afsluiten/uit zetten.

***
## v5.0.21 - 2025-09-04
### Fixed
- Deze versie bevat nog een kleine aanpassing die een potentieel probleem bij inbound calls oplost als heel snel inbound calls achter elkaar komen en het script geen tijd heeft om de inbound wacht pagina te tonen voordat alweer een volgende inbound call wordt geladen. We hebben geen meldingen gehad, maar dit zou potentieel de gegevens van de vorige inbound call kunnen gebruiken voor de nieuwe, wat verwarring kan opleveren als de Agent dit niet direct merkt.

***
## v5.0.20 - 2025-09-02
### Fixed
- Sommige gebruikers melden dat v5.0.19 niet kon worden geinstalleerd en een foutmelding gaf. De melding lijkt te zeggen dat de bestanden corrupt zijn maar hoe kunnen veel andere gebruikers deze versie dan wel installeren. Gelukkig was het probleem te reproduceren op een test computer. Alleen het opnieuw maken van de installer lijkt het probleem op te lossen.
Voor de zekerheid hebben we een nieuw versie nummer gemaakt. Deze versie is identiek aan v5.0.19.

***
## v5.0.19 - 2025-09-01
### Fixed
- Door een fout in de configuratie van de Seq logging konden we voor diagnose alleen Trace logs zien. Met deze fix is dit opgelost en zien we nu alle loglevels weer in de Script client logs. 
- Bij inbound kregen we een melding dat in sommige gevallen als de inbound call direct komt ndat de agent een call afboekt een vreemde popup kwam met alleen de tekst "Failed". Dit is nu afgevangen en veroorzaakt geen App crash meer.

*** 
## v5.0.18 - 2025-08-28
### Fixed
- De verkeerde werkstation naam werd genoemd in de melding die volgt al de Agent al is ingelogd op een andere werkplek.
### Changed
- Optimalisatie van de WebView2 engine waardoor deze stukken sneller is geworden in het uitlezen van de velden.
- Verbetering van de detectie dat een werkplek is gecrashed, of uit is gezet zonder uit te loggen, de Script module netjes af te sluiten.
- Interne wijzigingen om beter een diagnose te kunnen stellen, vooral toevoegen van logging.

***
## v5.0.17 - 2025-05-22
### Changed
- Vanaf deze versie is de Scriptmodule alleen als x64 versie beschikbaar. De afgelopen maanden hebben we gezien dat de x86 versie helemaal niet meer in gebruikt is wat de overstap naar volledig x64 mogelijk maakte.
- In de WebView2 Engine is ingesteld dat Autofill en PasswordAutosave voor scriptvelden uitgeschakeld is na feedback dat in he tscript de browser nu soms aanbied om velden te vulden met eerder gebruikte waarden. Dat is in een belscript zeer onwenselijk en met deze instelling zou dit nu niet meer moetne gebeuren. Het is mogelijk dat reeds bewaarde gegevens nog worden aangeboden!
### Fixed
- In de vorige versie was een fout geslopen waardoor het zoeken van belopdrachten op de systeem scriptvelden zoals achternaam, postcode, plaats etc.. geen resultaten opleverden.

***
## v5.0.16 - 2025-05-21
### Fixed
- Voor WebView2 is een probleem opgelost dat de browser (script pagina) actief bleef terwijl de Scriptmodule afboekt en de volgende belopdracht ophaalt. Dit kon vreemd gedrag opleveren als de Agent opnieuw probeert af te coderen terwijl het oude script nog in beeld is, maar wel al de nieuwe belopdracht is opgehaald. De nieuwe belopdracht wordt dan afgeboekt, terwijl de Agent in beeld nog de oude belopdracht ziet! Nu is het script in de tijd direct na afcoderen tot aan het compleet weergeven van de nieuwe belopdracht disabled.

***
## v5.0.15 - 2025-04-07
### Fixed
- In de vorige update is een fout geslopen waardoor de reistijdcontrole van de agendamodule niet meer werkte en een foutmelding gaf voro elk adres dat werd gecontroleerd.

***
## v5.0.14 - 2025-04-07
### Changed
- De Script module ondersteunt nu zowel x86 als x64 en is hiermee officieel ook 64-bits. Voor sommige acties is nu meer geheugen beschikbaar. Mogelijk zal in de toekomst de x86 (32-bits) versie verdwijnen omdat niemand meer oude computers heeft die alleen 32-bits Windows kunnen draaien.
- Om de overstap naar de nieuwe WebVew2 broweser engine te vereenvoudigen kan de WebView2Enabled variabele nu ook op de Seat groep worden vastgelegd en geldt dan voor alle Seats in en onder deze groep. Door de variabele op de Seats groep te plaatsen zijn alle werkplekken overgestapt. Uitzonderingen kunnen dan nog wordne gemaakt door op lagere Seat groepen, of direct op de Seat een WebView2Enabled variabele te definieren.

***
## v5.0.13 - 2025-03-10
### Changed
- (5.1.0 only) Bij het afcoderen van een Terugbellen status waarbij op de belopdracht een tijdrestrictie (terugbel rooster) staat ingesteld en de gekozen terugbeltijd valt buiten dit rooster dan is in de popup melding die volgt een checkbox toegevoegd om aan te geven dat de terugbeltijd mag worden bijgesteld zodat deze in het terugbel rooster valt. Daarna zal het afcoderen normaal vervolgen.

### Fixed
- In de MSHTML engine zijn de namen van CallPro functies die via `window.external` worden benaderd niet case-sensitive. De nieuwe Webview2 engine is wel case-sensitive waardoor enkele javascript functies niet correct werken doordat de schrijfwijze in de javascript afwijkt bij de source-code van CallPro. Met deze release worden onderstaande fouten opgelost die we hebben gevonden:

	- loAgent.Short**c**uts(i)
	- loAgent.Short**c**utsCount


***
## v5.0.12 - 2025-01-09
### Changed
- Support voor #SCRIPT_SENDDTMF om vanuit het script bijvoorbeeld IVR menu's te navigeren (buiten de softphone om)
- (intern) Diverse code optimalisaties en kleine cosmetische/functionele wijzigingen in generieke controls

***
## v5.0.11 - 2024-11-06
### Changed
- (intern) nieuwe callback schedule optie voor per belopdracht aangeven van tijden waarop de belopdracht aangeboden kan worden. Deze staat gepland voor versie 5.1.0 Dit is alleen in test databases te gebruiken, niet in productie (bij klanten)
- Maximale waarde voor enkele spinner controls voor de tijd opgave bij o.a. belopdrachtstatussen verhoogd van 100 naar 9999 omdat anders bij de eenheid minuten niet ver in de toekomst ingevuld kan worden.

### Fixed
- Variabelen tabblad werd soms niet weergegeven ondanks dat de gebruiker rechten had.
- Reistijdcontrole werkte niet bij alle installaties (klanten) door verschillen in de lokale situatie. Dit is in deze versie opgelost zodat het nu altijd werkt.

***
## v5.0.10 - 2024-07-30
### Changed
- synchronisatie release voor Resource Explorer
- Beta support voor WebView2 migratie van de oude MSHTML engine voor weergave van scripts. Om dit te gebruiken dient een variabele `WebView2Enabled` van type boolean met waarde `true` te worden gezet op de werkplek.

***
## v5.0.9 - 2024-02-28
### Changed
Een extra parameter `BREAKID` in het script commando om pauze te activeren zodat vanuit custom scripting de pauze substatus kan worden meegegeven.

```
#SCRIPT_BREAK?[{SET | CLEAR}][&BREAKID={id}][&NOCONFIRM]
```
Met de optionele parameter `BREAKID` wordt aangegeven welke pauze-substatus gebruikt moet worden. Hiervoor wordt gebruik gemaakt van de unieke ID van de pauze-substatus. Deze parameter heeft alleen effect als de pauze-substatus feature is ingeschakeld. 
> **Let op** Als `NOCONFIRM` optie wordt gebruikt in combinatie met een pauze-substatus waarbij een notitie verplicht is, komt alsnog het dialoogvenster omhoog zodat een notitie kan worden ingevuld!

***
## v5.0.8 - 2023-12-11
### Fixed
- Voor  belscripts waar vanuit javascript code de gespreksopnames worden gestart is een bug gefixt die een javascript error gaf `Deze eigenschap of methode wordt niet ondersteund door dit object loScriptAction.CreateParms()` Onderstaande code leverde de genoemde fout. Er zijn geen aanpassingen nodig, de javascript code is correct.
```javascript
function Recording(action) {
	var loScriptAction = window.external.GetScriptAction();
	var loScriptParams = loScriptAction.CreateParams();
	var lcCommand = "SCRIPT_RECORDING";
	loScriptParams.Add("ACTION", action);	
	var llResult = loScriptAction.ExecCommand(lcCommand, loScriptParams);
	return llResult;
}
```

***
## v5.0.7 - 2023-12-06
### Fixed
- Bij het afcoderen met de `CALLBACKAGENT` parameter is een fout opgelost die de meegegeven resource interpreteerde als Bellijst in plaats van Agent. Hierdoor werkte deze functie niet.
- Bij het gebruik `MOVEENTRY` als de move niet lukte kon daarna niet worden afgecodeerd met een andere status doordat bepaalde settings bleven hangen van de moveentry. Dit is nu opgelost.
- Bij de `SELECTSTAT` commando worden nu ook de `MINCALLBACKEXPR` en `MAXCALLBACKEXPR` toegevoegd die nog ontbraken.

### Changed
- Cosmetische verbeteringen in keuzelijsten met checkbox selectie.

***
## v5.0.6 - 2023-10-17
### Fixed
- Bij het afcoderen via scripting werd de `MOVEENTRY` parameter genegeerd. De correcte werking van deze parameter is hersteld
- Bij het afcoderen via scripting werden alle status parameters  genegeerd en werden de op de status ingestelde instellingen gebruikt. Nu worden weer correct de via scripting ingestelde waarden gebruikt

### Changed
- In de Agendamodule is een calendar maand control toegevoegd voor snellere navigatie door de agenda.

***
## v5.0.5 - 2023-07-18
### Fixed
- In de terugbeltijd expressie berekening die gebruikt wordt voor de status datum berekening, specifiek voor TimeAdd, konden door een fout geen minuten meer gebruikt worden. De syntax `TimeAdd=5m` (5 minuten) werd niet herkend als geldig, maar `TimeAdd=1h` (1 uur) nog steeds wel. Dit was een feature regressie bug die snel kon worden opgelost.


***
## v5.0.4 - 2023-07-17
In deze nieuwe versie is het dialer popup venster modeless gemaakt. Hierdoor kun je terwijl de dialer het nummer belt, maar er nog niet is opgenomen, toch al door het script scrollen en navigeren. Je kunt uiteraard **niet** afcoderen of andere systeemacties uitvoeren.
Voor scripts die langer zijn dan een scherm hoog is biedt dit meer vrijheid om alvast alles door te nemen. Ook scripts met meerdere tabbladen, of meerdere pagina's.

***
## v5.0.3 - 2023-03-01
Gebruikers op Windows 10 hadden veel problemen met automatische updates en installatie. Deze versie werkt alleen met het nieuwe developer certificaat en op zowel Windows 10 als Windows 11. Verwijder eerst voorgaande versies en installeer dan deze nieuwe versie.

*** 
## v5.0.2 - 2023-02-01
Door het verlopen van het developer certificaat werkten automatische updates niet meer. Deze versie gebruikt het nieuwe certificaat en ondersteunt op Windows 11 ook upgrade van het oude certificaat.

***
## v5.0.1 - 2022-02-01
Dit is de eerste officiele versie van deze client. Met deze versie gebruiken we https://installer.callpro.nl voor de installatie (voor Windows 10/11)

***
## v5.0.0 - unreleased
