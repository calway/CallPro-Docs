# Scriptmodule Releases
Dit zijn de Release Notes voor de Scriptmodule. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.11 - 2024-11-06
### Change
- (intern) nieuwe callback schedule optie voor per belopdracht aangeven van tijden waarop de belopdracht aangeboden kan worden. Deze staat gepland voor versie 5.1.0 Dit is alleen in test databases te gebruiken, niet in productie (bij klanten)
- Maximale waarde voor enkele spinner controls voor de tijd opgave bij o.a. belopdrahctstatussen verhoogd van 100 naar 9999 omdat anders bij de eenheid minuten niet ver in de teokomst ingevuld kan worden.

### Fixed
- Variabelen tabblad werd soms niet weergegeven ondanks dat de gebruiker rechten had.
- Reistijdcontrole werkte niet bij alle installaties (klanten) door verschillen in de lokale situatie. Dit is in deze versie opgelost zodat het nu altijd werkt.

***
## v5.0.10 - 2024-07-30
### Change
- synchronisatie release voor Resource Explorer
- Beta support voor WebView2 migratie van de oude MSHTML engine voor weergave van scripts. Om dit te gebruiken dient een variabele `WebView2Enabled` van type boolean met waarde `true` te worden gezet op de werkplek.

***
## v5.0.9 - 2024-02-28
### Change
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

### Change
- Cosmetische verbeteringen in keuzelijsten met checkbox selectie.

***
## v5.0.6 - 2023-10-17
### Fixed
- Bij het afcoderen via scripting werd de `MOVEENTRY` parameter genegeerd. De correcte werking van deze parameter is hersteld
- Bij het afcoderen via scripting werden alle status parameters  genegeerd en werden de op de status ingestelde instellingen gebruikt. Nu worden weer correct de via scripting ingestelde waarden gebruikt

### Change
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
