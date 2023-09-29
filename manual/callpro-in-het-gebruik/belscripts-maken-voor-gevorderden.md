# Belscripts maken voor gevorderden

Een belscript in CallPro kan ook met behulp van HTML worden gemaakt. De
gehele look-and-feel is dan vrij in te vullen met behulp van standaard
html pagina’s, of ASP.NET of php. Deze manier van belscripts maken biedt
meer vrijheid, maar vergt ook meer tijd en werk om een compleet
belscript te maken.

In situaties waar met meerdere pagina’s in het belscript gewerkt gaat
worden, of complexe beslissingsbomen (callflows) in het belscript
verwerkt moeten worden, of selectief belopdrachtstatussen beschikbaar
worden gemaakt per situatie (plek in het belscript) is het handmatig
opbouwen van het belscript de beste methode.

De scriptdefinitie wijst dan enkel naar de startpagina.

TODO Verder uitwerken.

# Script systeemacties

In het belscript kunnen diverse commando’s worden gebruikt om functies
van CallPro op te roepen via een hyperlink of vanuit javascript.

Bij het gebruik van de hyperlink methode wordt de systeemactie in het
href attribuut van de hyperlink gebruikt \<a
href="**{systeemactie}**"\>{label}\</a\>. Een andere methode is om
vanuit javascript een document.location="**{systeemactie}**" uit te
voeren.

In deze paragraaf worden deze systeemacties behandeld die telkens als
URL in een hyperlink worden gebruikt.

### Terugbellenscherm

Met deze systeemactie wordt het terugbellen scherm geactiveerd. De Agent
is vrij om een van de terugbel belopdrachtstatussen te kiezen uit de
keuzelijst.
```
#SCRIPT_SELECTSTAT?STATCAT=CALLBACK
```
### Verwerkscherm

Met deze systeemactie wordt het verwerk scherm geactiveerd. De agent is
vrij om een van de verwerkt belopdrachtstatussen te kiezen uit de
keuzelijst.
```
#SCRIPT_SELECTSTAT?STATCAT=PROCESS
```
### Niet-bereikt scherm

Met deze systeemactie wordt het Niet bereikt scherm geactiveerd. De
agent is vrij om een van de Niet bereikt belopdrachtstatussen te kiezen
uit de keuzelijst.
```
#SCRIPT_SELECTSTAT?STATCAT=NOREACH
```
### Belopdracht afcoderen

Activeert afhankelijk van de categorie van de StatCode-parameter het
terugbellenscherm, het verwerkscherm of het niet-bereiktscherm. In het
betreffende scherm is de belopdrachtstatus geselecteerd en kan niet
gewijzigd worden.

```
#SCRIPT_SELECTSTAT?STATCODE={status-code}[&AUTOSELECT][&CALLBACKEXPR={callback-expr}][&CALLBACKAGENT={agent-pad}][&PRIORITY={number}][&MOVEENTRY={bellijst-pad}][&CHANGENOTE={ON | OFF}][&CHANGETELNR={ ON | OFF}]
```

Een aantal parameters is optioneel. Deze parameters bepalen enkele extra
instellingen bij de status.

| Optionele paramater | Betekenis en gebruik                                                                                                                                                                                                            |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| &AUTOSELECT        | Door deze parameter op te nemen wordt de weergave van het popupvenster onderdrukt en wordt direct afgecodeerd.                                                                                                                  |
| &CALLBACKEXPR      | Met deze parameter kan de standaard terugbeltijd die voor de betreffende belopdrachtstatus geldt worden aangepast.                                                                                                              |
| &CALLBACKAGENT     | Met deze parameter kan de standaard ingestelde (terugbel-)agent worden aangepast. Vul hier het volledige pad naar de Agent resource in.                                                                                         |
| &PRIORITY          | Met deze parameter kan de standaard prioriteit van de betreffende belopdrachtstatus worden aangepast. De prioriteit moet wel liggen binnen de range die voor het type status (niet bereikt, terugbellen of verwerkt) geldig is. |
| &MOVEENTRY         | Met deze parameter kan de belopdracht tijdens het afcoderen fysiek worden verplaatst naar een andere bellijst. De bellijst moet compatibel zijn qua velden en belopdrachtstatus met de bellijst waar de belopdracht uit komt.   |
| &CHANGENOTE        | Geeft aan of de Agent in het CallPro popupvenster het notitieveld mag bewerken.                                                                                                                                                 |
| &CHANGETELNR       | Geeft aan of de Agent in het CallPro popupvenster het ingestelde telefoonummerveld dat wordt gebruikt voor het terugbellen mag wijzigen.                                                                                        |

### Starten windows applicatie

Met deze systeemactie kan een externe windows applicatie worden geopend.
Geef het complete pad op naar de .EXE of .BAT/.CMD van het programma
gestart moet worden.
```
#SCRIPT_WINEXEC?FILE={bestandsnaam}
```
### Herstellen/annuleren wijzigingen

Met deze systeemactie kunnen de veldwaarden in de actuele belscript
pagina worden teruggezet naar de waarden zoals ze waren toen de pagina
werd geladen. Let op! Dit geldt alleen voor de velden die op deze
pagina staan.
```
#SCRIPT_RESTOREINPUT
```
### Aanmelden

Met deze systeemactie kan de agent zich aanmelden. Hij zal direct de
eerstvolgende belopdracht ontvangen. De AUTOSELECT-parameter zorgt
ervoor dat het dialoogvenster dat normaal wel wordt getoond niet wordt
getoond. Zonder AUTOSELECT wordt de meegegeven keuze (als die er is) als
standaardkeuze gebruikt.
```
#SCRIPT_SUBSCRIBE?[DIALMODE={OUTBOUND | INBOUND | CALLBLENDING}[&AUTOSELECT]
```
### Pauze

Met deze systeemactie kan de agent aangeven dat hij na het huidige
gesprek naar de pauze-stand wil overgaan. CallPro zorgt ervoor dat de
agent na beëindiging van het huidige gesprek door een afcodeer
systeemactie automatisch overgaat in de pauze-stand.

Indien de NOCONFIRM-parameter wordt meegegeven wordt er overgegaan in de
pauze-stand zonder tussenkomst van een bevestigingscherm met de vraag
"wilt u na het beëindigen van het gesprek overgaan in de pauzestand?".
De andere twee parameters SET en CLEAR zorgen respectievelijk voor het
instellen en het opheffen van het pauze-verzoek.
```
#SCRIPT_BREAK?[{SET | CLEAR}][&NOCONFIRM]
```
### Uitloggen

Met deze systeemactie kan de agent aangeven dat hij na het huidige
gesprek wil uitloggen. CallPro zorgt ervoor dat de agent na beëindiging
van het gesprek uitlogt. Indien de NOCONFIRM-parameter wordt meegegeven
wordt er uitgelogd zonder tussenkomst van een bevestigingsscherm met de
vraag "wilt u na het beëindigen van het gesprek uitloggen?". De andere
twee parameters SET en CLEAR zorgen respectievelijk voor het instellen
en het opheffen van het uitlog-verzoek.
```
#SCRIPT_LOGOUT?[{SET | CLEAR}][&NOCONFIRM]
```
### Telefoonnummer kiezen

Met deze actie wordt het 1<sup>e</sup> telefoonnummer van de belopdracht
gekozen. Deze actie wordt vooral gebruikt bij preview dialing, maar kan
ook worden gebruikt om een tweede, alternatief nummer, te bellen. Met de
optionele parameter TELNR kan een willekeurig telefoonnummer ingesteld
worden.
```
#SCRIPT_DIAL?[TELNR={telefoonnummer}][&AUTOSELECTSTAT={TRUE | FALSE}]
```
### Beëindig gesprek

Met deze systeemactie wordt een actief gesprek beëindigd, de
telefoonlijn wordt opgehangen.
```
#SCRIPT_HANGUP
```
### Doorschakelen naar Bel-me-niet IVR

Indien de bel-me-niet module beschikbaar is in de licentie wordt met
deze systeemactie een actief gesprek doorgezet naar de IVR voor een
bel-me-niet registratie. De agent komt hiermee in wrapup.
```
#SCRIPT_REGDONOTCALL
```
### Dialing configuratie

Met deze actie wordt het Dialing Configuratiescherm opgeroepen.
```
#SCRIPT_DIALOPTIONS
```
### Verander wachtwoord

Met deze systeemactie kan de agent zijn wachtwoord wijzigen.
```
#SCRIPT_CHANGEPASSWORD
```
### Nieuwe belopdracht

Met deze systeemactie kan een nieuwe belopdracht worden toegevoegd aan
een aan de agent gekoppelde bellijst. Deze actie is alleen beschikbaar
voor *inbound* campagnes. Nadat de agent
een campagne en bellijst heeft geselecteerd wordt het
Belopdracht-eigenschappenscherm geopend en kunnen de gegevens van de
nieuwe belopdracht worden ingevoerd.
```
#SCRIPT_NEWENTRY
```
### Zoek belopdracht

Met deze menuoptie wordt het Belopdracht/Prospect Zoeken-applet geopend.
Deze actie is alleen beschikbaar voor *inbound* campagnes.
```
#SCRIPT_SEARCHENTRY
```
### Terug navigeren

Bestaat het script uit meerdere pagina's dan kan deze actie worden
gebruikt om een stap terug te doen naar de vorige pagina.
```
#SCRIPT_BACK
```
### Vooruit navigeren

Als gebruik is gemaakt van de Terug-knop kan deze knop worden gebruikt
om weer naar voren te stappen in het script. De knop kan alleen worden
gebruikt om de stappen die terug zijn genomen ongedaan te maken en is
niet bedoeld om door het script te bladeren.
```
#SCRIPT_FORWARD
```
### Belopdracht eigenschappen

Met deze actie wordt het belopdracht-eigenschappenscherm opgeroepen.
```
#SCRIPT_PROPERTYENTRY
```
### Oproep agendamodule

Met deze systeemactie wordt de agendamodule gestart. Met de parameter
CALENDAR kan de standaard weergegeven agenda bepaald worden (CALENDAR
dient de naam van de agenda te bevatten). Met de parameter DISABLESWITCH
kan in de agenda voorkomen worden dat de gebruiker tussen meerdere
agenda's kan schakelen.
```
#SCRIPT_CALLMODULE?MODULE=CALENDAR.APP[&CALENDAR={calendar}][&DISABLESWITCH]
```
### Volgende belopdracht

Met deze systeemactie kan in de outbound-mode de eerstvolgende aan te
bieden belopdracht worden bepaald. De optie PROMPT toont een
info-messagebox na uitvoeren van de actie. De optie CLEAR annuleert de
eventueel ingestelde belopdracht.

Bij herhaaldelijk instellen van belopdrachten wordt de laatste impliciet
geannuleerd. Bij uitloggen na instellen van een belopdracht wordt de
belopdracht automatisch vrijgegeven. De belopdracht mag niet al in
gebruik (vergrendeld) zijn bij de aanvraag.
```
#SCRIPT_NEXTENTRY?{ENTRYID={entryid}&CAMPAIGNID={campaignid} | CLEAR}[&PROMPT]
```
### Call blending; overschakelen op andere dial mode

De agent zal door deze systeemactie afhankelijk van de context naar
inbound of outbound switchen. Het commando werkt analoog aan een
Pauze-verzoek; het verzoek zal ingewilligd worden indien het systeem
daar toe in staat is.
```
#SCRIPT_SWITCHDIALMODE?[{SET | CLEAR}][&NOCONFIRM][CAMPAIGNID={campaignid&NEWENTRY]
```
Met de optie `CAMPAIGNID={campaignid}&NEWENTRY` schakelt CallPro voor de
volgende call over naar de genoemde campagne en begint een nieuwe blanco
belopdracht.

### Work modus van agent; het plaatsen van een agent in een work modus

Hiermee kan een agent in een bepaalde work modus gezet worden. Een agent
die inbound aan het bellen is, kan zichzelf via deze scriptactie
(tijdelijk) afmelden bij de dialer waardoor hij geen gesprekken meer
ontvangt.
```
#SCRIPT_SETAGENT?MODE={READY | NOT_READY}
```
### Cancel belopdracht; de belopdracht wordt beëindigd zonder te bewaren

Hiermee een agent een belopdracht beëindigen zonder te bewaren. Deze
systeemactie werkt alleen in inbound campagnes.
```
#SCRIPT_CANCELENTRY
```
### Speciale hyperlink anchors

Met deze speciale anchors kan binnen de pagina worden gesprongen waarbij
bepaald gedrag kan worden onderdrukt.
```
#<name>&SCRIPT_OPTION={NODATA | NOSAVE | NORESTORE}
```
### Opnemen gesprek

Met deze systeemactie kan de opname van het gesprek worden gestuurd.
```
#SCRIPT_RECORDING?ACTION={START | STOP | RESUME | PAUSE | TOGGLE}
```
### Gesprek direct doorschakelen (blind transfer)

Met deze systeemactie wordt een actief gesprek (live call) direct
doorgeschakeld naar het opgegeven nummer. De agent schakelt hierdoor
naar de wrapup fase.
```
#SCRIPT_TRANSFER?TYPE=BLIND&CONTEXT=dialer-transfer&TARGET={telefoonnummer}
```
Een alternatieve variant hierop is:
```
#SCRIPT_TRANSFER?TYPE=BLINDEARLYMEDIA&CONTEXT=dialer-transfer&TARGET={telefoonnummer}
```
Deze variant schakelt het audiokanaal aal door voordat de target heeft
opgenomen. Dit is vooral bruikbaar als er doorgeschakeld wordt naar
nummers die geen "answer" geven maar wel al audio afspelen zodat
gebruikt bij 0800 en 09xx nummers.

### Gesprek met ruggespraak doorverbinden (attended transfer) 

Met deze systeemactie wordt het doorverbinden van een actief gesprek
(live call) met ruggespraak gestart. Het actieve gesprek wordt
geparkeerd. Deze variant is bedoeld als de Agent uit meerdere nummers
kan kiezen en niet direct het eerste nummer geprobeerd moet worden maar
de agent nog tijd nodig heeft om het juiste nummer te vinden/kiezen.
```
#SCRIPT_TRANSFER?TYPE=ATTENDEDPREVIEW&CONTEXT=dialer-transfer
```
Met deze systeemactie wordt het doorverbinden van een actief gesprek
(live call) met ruggespraak gestart en wordt direct het nummer gebeld
waarmee doorverbonden gaat worden na ruggespraak.
```
#SCRIPT_TRANSFER?TYPE=ATTENDED&CONTEXT=dialer-transfer&TARGET={telefoonnummer}
```
### Doorverbinden met ruggespraak annuleren

Met deze systeemactie wordt een actieve doorverbind actie geannuleerd en
krijgt de agent de beller weer aan de lijn.
```
#SCRIPT_TRANSFER?TYPE=ABORT
```
Met deze systeemactie wordt een actieve doorverbind doel (gesprek)
beëindigt maar blijft de attended transfer actief. Hiermee kan de agent
een nieuwe attended transfer target bellen (met TYPE=ATTENDED) en blijft
het gesprek dat doorgeschakeld moet worden in de wacht staan.
```
#SCRIPT_TRANSFER?TYPE=SOFTABORT
```
### Doorverbinden met ruggespraak voltooien

Met deze systeemactie wordt een actieve doorverbind actie afgerond. De
Agent komt hierdoor in wrapupfase en de beller is doorverbonden met de
externe/andere partij.
```
#SCRIPT_TRANSFER?TYPE=COMPLETE
```
### Doorverbinden wissel gesprekken

Met deze systeemactie kan tijdens een actieve doorverbind actie met
ruggespraak worden gewisseld tussen de beller en de externe/andere
partij voor ruggespraak.
```
#SCRIPT_TRANSFER?TYPE=SWITCHPARTIES
```
### Verstuur DTMF-tonen

Met deze systeemactie kunnen DTMF tonen worden gestuurd die nodig zijn
om in een gesprek door een IVR de navigeren. Dit werkt alleen met G711
codec.
```
#SCRIPT_SENDDTMF?DIGITS={digits}
```
### Zet een gesprek on hold

Met deze systeemactie kan een actief gesprek (live call) on hold worden
gezet zodat de beller niet hoort wat de agent zegt.
```
#SCRIPT_HOLD?{ON | OFF | TOGGLE}
```
# Belscript (querystring) parameters

Bij het laden van het belscript wordt aan de eerste pagina een aantal
parameters in de url meegegeven. Deze parameters kunnen worden gebruikt
in dynamische ASP.NET of php pagina’s om op te slaan, en later te
gebruiken om extra informatie rechtstreeks uit de CallPro database te
lezen.

### Belscript startpagina

Bij het oproepen van de startpagina van het belscript worden de volgende
parameters meegegeven.

| Parameter  | Inhoud                                                                                                |
| ---------- | ----------------------------------------------------------------------------------------------------- |
| AGENTID    | De unieke ID van de Agent die is ingelogd op de werkplek                                              |
| CLENTRYID  | De unieke ID van de belopdracht die wordt geopend                                                     |
| CAMPAIGNID | De unieke ID van de campagne waar de belopdracht in wordt geopend                                     |
| RAWTELNR   | Het 1<sup>e</sup> telefoonnummer van de belopdracht die wordt geopend in RAW formaat (+31 0507070720) |
| CALLLISTID | De unieke ID van de bellijst waar de belopdracht uit komt                                             |
| DIALMODE   | De dialmode: 1 = Outbound, 5 = inbound                                                                |
| LANGUAGE   | De taal die staat ingesteld op de werkplek: nl                                                        |

### Pauze pagina

Bij het oproepen van de pauze pagina die geldt voor de belplek (of
globaal) worden de volgende parameters meegegeven.

| Parameter | Inhoud                                                   |
| --------- | -------------------------------------------------------- |
| AGENTID   | De unieke ID van de Agent die is ingelogd op de werkplek |
| LANGUAGE  | De taal die staat ingesteld op de werkplek: nl           |

### Inbound pagina

Bij het oproepen van de inbound (wacht) pagina die in de inbound modues
word tafgebeeld tussen gesprekken tijdens het wachten worden de volgende
parameters meegegeven.

| Parameter | Inhoud                                                   |
| --------- | -------------------------------------------------------- |
| AGENTID   | De unieke ID van de Agent die is ingelogd op de werkplek |
| LANGUAGE  | De taal die staat ingesteld op de werkplek: nl           |
