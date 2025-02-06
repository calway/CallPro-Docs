## Scriptdefinitie instellingen

Met behulp van enkele variabelen die kunnen worden gedefinieerd bij de
campagne, of de scriptdefinitie kan het gedrag van het autoscript worden
beïnvloed. Hoewel elke schrijfwijze met hoofd- en kleine letters werkt
raden wij aan om de schrijfwijze uit deze handleiding aan te houden.

<table>
<thead>
<tr class="header">
<th>Variabele</th>
<th>Type</th>
<th>Betekenis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SCRIPT.TITLE</td>
<td>Memo</td>
<td><strong>(Alleen voor intern gebruik)</strong></td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR</td>
<td>Bool</td>
<td><strong>True</strong>/False Bepaald of de toolbar in het autoscript wordt weergegeven.</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.LOGO</td>
<td>Bool</td>
<td><strong>True</strong>/False Moet de Logo Tile worden afgebeeld.</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.LOGO.WIDE</td>
<td>Bool</td>
<td><strong>True</strong>/False Geeft aan of de Logo tile groot moet zijn.</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.CALLHISTORY</td>
<td>Bool</td>
<td><strong>True</strong>/False Moet de Callhistory Tile worden afgebeeld</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.CUSTOMTILE1</td>
<td>Memo</td>
<td><strong>(Expert)</strong> Met deze variabele is het mogelijk om rechts van de Callhistory tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord.</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.DIAL</td>
<td>Bool</td>
<td><strong>True</strong>/False Moet de Dial Tile worden afgebeeld.</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.DIAL.SMALL</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de Dial knop klein moet zijn</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.DIAL.AUTOSELECTSTAT</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de Dial knop in de toolbar bij automatisch bellen CTI resultaten automatisch afcodeert of alleen een melding geeft.<br />
Alle overige bellen knoppen in het script laten alleen zien wat het resultaat is maar coderen de belopdracht niet af. Op deze manier kunnen meerdere bekende nummers geprobeerd worden.</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.HANGUP</td>
<td>Bool</td>
<td><strong>True</strong>/False Moet de Hangup Tile worden afgebeeld</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.HANGUP.SMALL</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de Hangup knop klein moet zijn</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.INBOUND</td>
<td>Bool</td>
<td><strong>True</strong>/False Deze variabele bepaald of bij inbound/call blending campagnes de tiles voor zoeken, nieuw en annulerenvan een belopdracht worden getoond.</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.CALLPARK</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de Parkeren knop zichtbaar is. Met deze knop kan een actief gesprek worden geparkeerd zodat de klant je niet hoort. De klant krijgt music on hold.</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.CALLPARK.SMALL</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geef de parkeren knop weer als kleine tile</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.CALLTRANSFER</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de doorschakelen knoppen zichtbaar moeten zijn</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.CALLTRANSFER.SMALL</td>
<td>Boolt</td>
<td>True/<strong>False</strong> Geef de doorschakelen knoppen weer met kleine tiles</td>
</tr>
<tr class="odd">
<td>SCRIPT.TOOLBAR.CUSTOMTILE2</td>
<td>Memo</td>
<td><strong>(Expert)</strong> Met deze variabele is het mogelijk om links van de Break tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord.</td>
</tr>
<tr class="even">
<td>SCRIPT.TOOLBAR.BREAK.SMALL</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of de Break tile klein moet zijn.</td>
</tr>
<tr class="odd">
<td>SCRIPT.AGENTMOOD</td>
<td>Bool</td>
<td>True/<strong>False</strong> Geeft aan of voor het afcoderen altijd een AgentMood moet worden gekozen door de agent</td>
</tr>
<tr class="even">
<td>SCRIPT.HEADER</td>
<td>Memo</td>
<td><p>De inhoud van deze variabele wordt direct aan het begin van de pagina geplaatst, voor de opmaak. Als eerste wordt bij de campagne gekeken, daarna bij de scriptdefinitie.</p>
<p><strong>V4.3.3:</strong> Als deze variabele niet is gedefinieerd op de resource dan wordt in de folder hiërarchie omhoog gezocht naar een variabele met deze naam.</p>
<p>Deze variabele is vooral bedoeld om de Custom_ValdiationCheck() functie in de pagina te zetten die wordt opgeroepen als onderdeel van het afcoderen. Hiermee kunnen extra validaties worden uitgevoerd voor bepaalde statussen die het afcoderen afbreken.</p></td>
</tr>
<tr class="odd">
<td>SCRIPT.INFO</td>
<td>Memo</td>
<td><p>De inhoud van deze variabele wordt binnen het hoofd script blok geplaatst, direct onder de toolbar, maar rechts van de statussen. Als eerste wordt bij de campagne gekeken, daarna bij de scriptdefinitie.</p>
<p><strong>V4.3.3:</strong> Als deze variabele niet is gedefinieerd op de resource dan wordt in de folder hiërarchie omhoog gezocht naar een variabele met deze naam.</p>
<p>Voor informatieve inhoud is het beter om gebruik te maken van het Informatiebord en daar aan te geven, “weergeven in belscript”.</p>
<p>Voor speciale maatwerk wensen kijk bij de sectie “Geavanceerde opmaak met het autoscript”.</p></td>
</tr>
<tr class="even">
<td>SCRIPT.CAMPAIGNNOTES</td>
<td>Bool</td>
<td>True/<strong>False</strong> Bepaald of de campagne notities in het belscript boven de scriptvelden als accordion worden weergegeven.</td>
</tr>
<tr class="odd">
<td>SCRIPT.BODY</td>
<td>Memo</td>
<td><strong>(Alleen voor intern gebruik)</strong> De HTML opmaak code die hier wordt geplaatst komt in de plaats van de gegenereerde lijst met scriptvelden.</td>
</tr>
<tr class="even">
<td>SCRIPT.NOTES</td>
<td>Memo</td>
<td><strong>(Alleen voor intern gebruik)</strong> De HTML opmaak code die hier wordt geplaatst komt in de plaats van de weergave van Notitie en opmerkingen.</td>
</tr>
<tr class="odd">
<td>SCRIPT.NOTES.LOCATION</td>
<td>Karakter</td>
<td>TOP/<strong>BOTTOM</strong> Met deze waarde wordt bepaald waar het Notitie &amp; Opmerkingen blok wordt geplaatst.</td>
</tr>
<tr class="even">
<td>SCRIPT.NOTES.CALLHISTORY</td>
<td>Bool</td>
<td><strong>True</strong>/False Moet de belhistorie worden afgebeeld onderaan de pagina</td>
</tr>
<tr class="odd">
<td>SCRIPT.STATUS</td>
<td>Memo</td>
<td><strong>(Alleen voor intern gebruik)</strong> Met deze variabele kan het complete status block worden vervangen met een eigen html opmaak voor de weergave van statussen.</td>
</tr>
<tr class="even">
<td>SCRIPT.FOOTER</td>
<td>Memo</td>
<td>De inhoud van deze variabele wordt direct boven de pagina footer afgebeeld (in het blauwe deel) over de gehele breedte van het scherm.</td>
</tr>
<tr class="odd">
<td>FEATURE.CSS</td>
<td>Memo</td>
<td><strong>(Alleen voor intern gebruik)</strong> Deze variabele voegt extra css features toe die nog niet standaard door CallPro worden ondersteunt. In de toekomst komt hiervoor misschien een optie in de scriptdefinitie.<br />
Hier kunnen CSS opmaak codes worden geplaatst die bestaande opmaak overschrijven, of extra opmaak die in eigen html/css wordt gebruikt.</td>
</tr>
<tr class="even">
<td>ANTWOORDSERVICE.CONTACT.MULTISELECT</td>
<td>Bool</td>
<td><p>True/<strong>False</strong> Met deze optie wordt aangegeven of het mogelijk is om in de contact lijst meerdere contactpersonen aan te vinken of slechts 1 die op de hoogte wordt gesteld van de notitie.</p>
<p><strong>Alleen in het antwoordservice script!</strong></p></td>
</tr>
</tbody>
</table>

## Extra autoscript instellingen

Er zijn ook enkele instellingen die met het autoscript mogelijk zijn die
betrekking hebben op andere onderdelen zoals de pauze pagina.

### Globale campagne instellingen

Instellingen die op de “Campaigns” root-folder kunnen worden gezet als
globale instellingen.

| Variabele                      | Type     | Betekenis                                                                                                                                                                                                                                                      |
| ------------------------------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BREAK.ShowHighscoreTile        | Bool     | True/**False** Geeft aan of de Highscore tile moet worden weergegeven.                                                                                                                                                                                         |
| BREAK.Highscore.Period         | Karakter | Vul hier DAY | WEEK | MONTH in om aan te geven dat de HighScore tile berekening over de betreffende periode moet lopen.                                                                                                                                        |
| BREAK.ShowScoreTiles           | Bool     | True/**False** Bepaald of de ScoreTiles worden weergegeven.                                                                                                                                                                                                    |
| BREAK.ScoreTiles.Category      | Karakter | Bepaald welke Belopdrachtstatuscategorie die wordt gebruikt als Score resultaat.                                                                                                                                                                               |
| BREAK.ShowLeaderboard          | Bool     | True/**False** Bepaald of het middelste tab “leaderboard” van de Engage Gamification wordt weergegeven.                                                                                                                                                        |
| BREAK.DisableCampaignSelection | Bool     | True/**False** Bepaald of agenten in het pauzescherm de campagne toekenning zelf kunnen aanpassen. Standaard staat dit aan, maar door deze variabele op True te zetten wordt het uitgeschakeld. Op Campagne niveau kan deze instelling worden aangepast.       |
| BREAK.MaxBreakHoursPerDay      | Decimal  | Het maximale aantal pauze minuten per dag voor agenten. Alleen pauze types die als agent werktijd worden geteld. Als dit aantal wordt overschreden wordt de Pauze tile rood                                                                                    |
| BREAK .INFO                     | Memo     | Hier kan extra informatie op de pauze pagina worden gezet in het rechter pagina deel.                                                                                                                                                                          |
| BREAK.TOOLBAR.CUSTOMTILE1      | Memo     | **(Expert)** Met deze variabele is het mogelijk om op de pauze pagina rechts van de Logo tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord.   |
| BREAK.TOOLBAR.CUSTOMTILE2      | Memo     | **(Expert)** Met deze variabele is het mogelijk om op de pauze pagina links van de Break tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord.   |
| INBOUND .INFO                   | Memo     | Hier kan extra informatie op de inbound pagina worden gezet in het rechter pagina deel.                                                                                                                                                                        |
| INBOUND.TOOLBAR.CUSTOMTILE1    | Memo     | **(Expert)** Met deze variabele is het mogelijk om op de inbound pagina rechts van de Logo tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord. |
| INBOUND.TOOLBAR.CUSTOMTILE2    | Memo     | **(Expert)** Met deze variabele is het mogelijk om op de inbound pagina links van de Break tile extra tiles in te voegen met eigen custom gedrag. Er is geen beperking op wat hier ingevoegd kan worden dus let op dat de toolbar opmaak niet wordt verstoord. |

### Agentgroup instellingen

Instellingen die op een Agent group folder kunnen worden ingesteld.

| Variabele                | Type     | Betekenis                                                                                                                                                                          |
| ------------------------ | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Leaderboard.TeamColor    | Karakter | Een kleur MetroUI kleur class code die gebruikt wordt als achtergrond kleur voor de Agent tiles op het leaderboard (http://autoscript/MetroUI/leaderboard)                         |
| Weektargets.ScorePerHour | Numeriek | Weektargets is een optionele pagina met 4 tiles met informatie. Hiermee wordt de te behalen conversie voor de weektargets Tile ingesteld. (http://autoscript/services/weektargets) |

### Campagne instellingen

Instellingen op de Campagne folders van individuele projecten.

Bij de instellingen staat \<Score\> voor de waarde die is ingesteld bij
Break.ScoreTiles.Category

<table>
<thead>
<tr class="header">
<th>Variabele</th>
<th>Type</th>
<th>Betekenis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;Score&gt;.Type</td>
<td>Karakter</td>
<td><p>Geeft aan op welke manier de ScoreTile moet worden berekend.</p>
<p>Mogelijke waarden:</p>
<p>C – Conversie</p>
<p>U – Uren</p>
<p>S – Score</p></td>
</tr>
<tr class="even">
<td>&lt;Score&gt;.Conversion</td>
<td>Numeriek</td>
<td>De conversie als score/uur die moet worden gehaald voor de campagne</td>
</tr>
<tr class="odd">
<td>&lt;Score&gt;.Value</td>
<td>Numeriek</td>
<td>Wordt gebruikt bij type U en S om vast te leggen wat het absolute aantal uren of score resp. dat moet worden gehaald.</td>
</tr>
<tr class="even">
<td>&lt;Score&gt;.Price</td>
<td>Numeriek</td>
<td><p>De prijs per score (omzet) die wordt gehaald.</p>
<p>Deze parameter wordt op dit moment nog niet gebruikt!</p></td>
</tr>
<tr class="odd">
<td>BREAK.DisableCampaignSelection</td>
<td>Bool</td>
<td>True/<strong>False</strong> Bepaald of agenten in het pauzescherm de campagne toekenning zelf kunnen aanpassen. Standaard staat dit aan, maar door deze variabele op True te zetten wordt het uitgeschakeld.</td>
</tr>
</tbody>
</table>

Voor campagnes met sub-projecten kunnen de \<Score\> instellingen ook op
de bovenliggende campagne-folder worden ingesteld. Dit heeft de
betekenis dat de instellingen gelden voor alle direct er onder liggende
(1-niveau) campagnes.

### Status instellingen

Voor de belopdrachtstatus is een speciale autoscript optie beschikbaar

| Variabele       | Type | Betekenis                                                                                                                                                                                                     |
| --------------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| STATUS.COLLAPSE | Bool | True/**False** Met deze variabele kan worden aangegeven dat deze status in een dropdown control moet worden weergegeven. Opvolgende statussen die allemaal deze instelling hebben komen in dezelfde dropdown. |
