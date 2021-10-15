# Inhoudsopgave

[Algemeen](#algemeen)

[De Resource Explorer](#de-resource-explorer)

[Control panel](#control-panel)

[Belopdrachtstatussen](#belopdrachtstatussen)

[Scriptdefinitie](#scriptdefinitie)

[Importdefinitie](#importdefinitie)

[Exportdefinitie](#exportdefinitie)

[Zoeken tools](#zoeken-tools)

[Campagne grid](#campagne-grid)

[Systeemconfiguratie](#systeemconfiguratie)

[Algemeen](#algemeen)

[Script-omgeving](#script-omgeving)

[Diagnose](#diagnose)

[Bestandslokaties](#bestandslokaties)

[Systeem scriptvelden](#systeem-scriptvelden)

[Pauze types](#pauze-types)

[Geavanceerd](#geavanceerd)

[Resources](#resources)

[Agent](#agent)

[Call-list](#call-list)

[Calendar](#calendar)

[Seat](#seat)

[Groups](#groups)

[Campaigns](#campaigns)

[Snelkoppelingen](#snelkoppelingen)

[Scriptmodule](#scriptmodule)

[Agenda module](#agenda-module)

[CallProPortal](#callproportal)

[Belangrijke conventies in CallPro](#belangrijke-conventies-in-callpro)

[Hoe biedt CallPro een belopdracht aan](#hoe-biedt-callpro-een-belopdracht-aan)

# Algemeen

CallPro werkt met een aantal termen die door de hele applicatie zijn
doorgevoerd. Ook user-interface standaarden worden hier behandeld.

# De Resource Explorer

De Resource Explorer is de centrale interface voor het beheer van
CallPro. Afhankelijk van de verantwoordelijkheden van de supervisor
kunnen meer of minder onderdelen worden gebruikt.

## Control panel

In het control panel zijn de diverse (systeem) instellingen van CallPro
verzameld.

![](./media/image2.png)

### Belopdrachtstatussen

In CallPro kunnen zeer eenvoudig belopdrachtstatussen worden aangemaakt.
Wij (Calway) adviseren om de belopdrachtstatussen een logische indeling
te geven qua naamgeving en gebruik. Onderstaande lijst is ons voorstel
voor de indeling van belopdrachtstatussen. Deze indeling is functioneel
en maakt o.a. het opstellen van rapportages eenvoudiger doordat
statussen gegroepeerd kunnen worden op basis van de code. Alle standaard
CallPro rapportages zijn gebaseerd op deze indeling.

Alle statussen worden verder op de standaard instellingen gezet van
CallPro en zijn zelf eenvoudig aan te passen als dit gewenst is.

Voor de code van een belopdrachtstatus gebruiken wij een 3-cijferige
codering. Het eerste cijfer geeft een globale indeling van de statussen.

<table>
<thead>
<tr class="header">
<th>Groep</th>
<th>Omschrijving</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td><p><strong>Systeem statussen</strong></p>
<p>Alle statussen uit deze categorie zijn systeem statussen die bij de installatie van CallPro reeds aanwezig zijn, en ook een speciale betekenis hebben. Het betreft hier voornamelijk statussen die te maken hebben met de telefonie, of begrenzingen danwel ontdubbelen etc...</p></td>
</tr>
<tr class="even">
<td>1</td>
<td><p><strong>Niet bereikt</strong></p>
<p>Alle statussen uit deze categorie dienen van het type niet bereikt te zijn en dienen ook functioneel als “Niet bereikt” te worden geïnterpreteerd.</p></td>
</tr>
<tr class="odd">
<td>2</td>
<td><p><strong>Uitval</strong></p>
<p>Alle statussen uit deze categorie dienen van het type verwerkt te zijn en dienen ook functioneel als “Uitval” te worden gezien. Deze status wordt voor de Agent (beller) als een niet negatieve status gezien omdat de Agent er niets aan kan doen.</p></td>
</tr>
<tr class="even">
<td>3</td>
<td><p><strong>Terugbellen</strong></p>
<p>Alle statussen uit deze categorie dienen van het type terugbellen te zijn en dienen ook functioneel als “Terugbellen” gezien te worden. Het is toegestaan om terugbelstatussen bij de positieve categorieën op te nemen als dit functioneel gezien duidelijker is.</p></td>
</tr>
<tr class="odd">
<td>4</td>
<td><p><strong>Geen interesse/Niet positief (telt niet voor agent)</strong></p>
<p>Alle statussen in deze categorie dienen van het type verwerkt te zijn en dienen ook functioneel als “Niet positief” gezien te worden. De status geldt voor de Agent niet als een negatief resultaat.</p></td>
</tr>
<tr class="even">
<td>5</td>
<td><p><strong>Geen interesse/Negatief (telt wel voor agent)</strong></p>
<p>Alle statussen in deze categorie dienen van het type verwerkt te zijn en dienen ook functioneel als “Negatief” gezien te worden. Het resultaat geldt ook als “Negatief” voor de Agent.</p></td>
</tr>
<tr class="odd">
<td>6</td>
<td><p><strong>Positief (niet voor Agent)</strong></p>
<p>Alle statussen in deze categorie gelden als “Positief” belresultaat voor het call center/de opdrachtgever maar gelden niet als “Positief” belresultaat voor de Agent.</p></td>
</tr>
<tr class="even">
<td>7</td>
<td><p><strong>Positief (ook voor Agent)</strong></p>
<p>Alle statussen in deze categorie gelden als “Positief” belresultaat voor zowel het call center/de opdrachtgever als de Agent.</p></td>
</tr>
<tr class="odd">
<td>8</td>
<td>Gereserveerd (telt niet voor Agent)</td>
</tr>
<tr class="even">
<td>9</td>
<td>Gereserveerd (telt wel voor Agent)</td>
</tr>
</tbody>
</table>

Hoewel bij de installatie veel van deze belopdrachtstatussen aanwezig
zullen zijn, zijn alleen de statussen die zijn gemarkeerd als
“Systeemstatus” altijd aanwezig. Hoewel het beter is om zoveel
mogelijk bij de richtlijn te blijven is er geen verplichting om
bijvoorbeeld de 7xx statussen altijd als verwerkt in te richten. Het kan
echter wel gebeuren dat in rapportages dan bepaalde tellingen
anders/verkeerd lopen. Als er echter een duidelijke, goede reden, voor
is is afwijken vanuit de software geen probleem.

<table>
<thead>
<tr class="header">
<th>Groep</th>
<th>Code</th>
<th>Omschrijving</th>
<th>Subgroep</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td><strong>Systeem statussen</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><strong>000</strong></td>
<td>Nieuwe belopdracht</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>010</strong></td>
<td>Bel-me-niet uitsluiting</td>
<td>Systeemstatus. Deze status wordt gezet als de belopdracht op de Bel-me-niet suppressielijst voorkomt</td>
</tr>
<tr class="even">
<td></td>
<td><strong>011</strong></td>
<td>Bel-me-niet verlopen</td>
<td>Systeemstatus. Deze status kan worden gezet als een belopdracht een verlopen bel-me-niet belperiode heeft.</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>012</strong></td>
<td>RVV afmelding</td>
<td>Systeemstatus. Deze status geeft aan dat deze belopdracht via de bel-me-niet IVR is afgemeld voor Recht-van-verzet.</td>
</tr>
<tr class="even">
<td></td>
<td><strong>060</strong></td>
<td>Abandoned call</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>061</strong></td>
<td>Verbinding verbroken tijdens kiezen</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="even">
<td></td>
<td><strong>062</strong></td>
<td>Verbinding geweigerd</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>063</strong></td>
<td>Call failure</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="even">
<td></td>
<td><strong>064</strong></td>
<td>Interupted by CTI layer</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>065</strong></td>
<td>Dailing timeout</td>
<td>Systeemstatus. In de Verwerkt categorie. Ook vaak geassocieerd met Geen gehoor, maar soms een tijdelijk probleem</td>
</tr>
<tr class="even">
<td></td>
<td><strong>066</strong></td>
<td>Transaction incomplete</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>067</strong></td>
<td>Fast Busy</td>
<td>Systeemstatus. In de Niet bereikt categorie</td>
</tr>
<tr class="even">
<td></td>
<td><strong>090</strong></td>
<td>Maximaal aantal belpogingen (Koude belopdracht)</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>091</strong></td>
<td>Maximale belpogingduur (Koude belopdracht)</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td><strong>092</strong></td>
<td>Maximaal aantal belpogingen (Terugbelopdracht)</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>093</strong></td>
<td>Maximale belpogingduur (Terugbelopdracht)</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td><strong>094</strong></td>
<td>Maximaal aantal terugbelpogingen</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>095</strong></td>
<td>Maximale terugbelpogingduur</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td><strong>096</strong></td>
<td>Maximaal aantal belpogingen</td>
<td>Systeem status. Een absoluut maximum aan het aantal belpogingen ongeacht de categorie</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>097</strong></td>
<td>Te vaak dezelfde status achter elkaar</td>
<td>Systeemstatus. Bij een status kan een aantal worden opgegeven. Als dit aantal wordt bereikt wordt deze code gebruikt.</td>
</tr>
<tr class="even">
<td></td>
<td><strong>098</strong></td>
<td>Live contact over ander nummer</td>
<td>Systeemstatus. Geeft aan dat een nieuwe belpoging is gestart voor een ander nummer. De actuele belpoging wordt dan afgecodeerd met dit resultaat. Treedt alleen op als er vaker naar nummers wordt gebeld tijdens de behandeling van 1 belopdracht.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>1</td>
<td><strong>Niet bereikt</strong></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><strong>120</strong></td>
<td>Geen gehoor</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td><strong>130</strong></td>
<td>In gesprek</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>140</strong></td>
<td>Voicemail/antwoordapparaat</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td>150</td>
<td>Niet aanwezig/geen tijd</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>160</td>
<td>DMU afwezig/niet beschikbaar</td>
<td></td>
</tr>
<tr class="even">
<td>2</td>
<td><strong>Uitval</strong></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><strong>200</strong></td>
<td>Informatietoon</td>
<td>Systeemstatus</td>
</tr>
<tr class="even">
<td></td>
<td><strong>201</strong></td>
<td>Fax/Modem</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>205</strong></td>
<td>Ruis</td>
<td>Systeemstatus Antwoordservicemodule</td>
</tr>
<tr class="even">
<td></td>
<td>210</td>
<td>Niet meer telefonisch benaderen (Bel-me-niet)</td>
<td>Zie ook 410 en 510</td>
</tr>
<tr class="odd">
<td></td>
<td>211</td>
<td>Overleden</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>212</td>
<td>Geen bedrijf/failliet</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>220</td>
<td>Uitsluiting door klant</td>
<td>Als de klant na de import adressen aanlevert die niet gebeld moeten/mogen worden kan deze status worden toegekend. Dit gebeurd dan via een update import, of direct via de Resource Explorer</td>
</tr>
<tr class="even">
<td></td>
<td>225</td>
<td>Valt buiten doelgroep</td>
<td>Zie ook 525</td>
</tr>
<tr class="odd">
<td></td>
<td><strong>230</strong></td>
<td>Fout/ongeldig telefoonnummer</td>
<td>Systeemstatus. Deze status wordt gezet bij het importeren als een ongeldig telefoonnummer is gedetecteerd. Ook functioneel te gebruiken om aan te geven dat tijdens het bellen alsnog blijkt dat het nummer niet geldig is.</td>
</tr>
<tr class="even">
<td></td>
<td>231</td>
<td>Dubbel in bestand</td>
<td>Doorgebelde of Agent aangegeven.</td>
</tr>
<tr class="odd">
<td></td>
<td>290</td>
<td>Onbereikbaar in belperiode</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>299</td>
<td>Niet bereikbaar</td>
<td>Functionele status voor slecht bereikbare adressen als geen gebruik wordt gemaakt van de belpogingbegrenzing. Deze status wordt via de Resource Explorer dan handmatig op de belodpracht ingesteld.</td>
</tr>
<tr class="odd">
<td>3</td>
<td><strong>Terugbellen</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><strong>300</strong></td>
<td>Terugbellen</td>
<td>Systeemstatus</td>
</tr>
<tr class="odd">
<td></td>
<td>310</td>
<td>Gerichte terugbelafspraak</td>
<td>Als 300, andere tekst (!)</td>
</tr>
<tr class="even">
<td></td>
<td>320</td>
<td>(zachte) terugbelafspraak</td>
<td>Als 300, willekeurige agent</td>
</tr>
<tr class="odd">
<td></td>
<td>330</td>
<td>Terugbellen op lange termijn</td>
<td>Technisch een “ Verwerkt” status.</td>
</tr>
<tr class="even">
<td>4</td>
<td><strong>Geen interesse/Niet Positief (telt niet voor agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>410</td>
<td>Niet meer telefonisch benaderen (Bel-me-niet)</td>
<td>Zie ook 210 en 510</td>
</tr>
<tr class="even">
<td></td>
<td>431</td>
<td>Weigert gesprek</td>
<td></td>
</tr>
<tr class="odd">
<td>5</td>
<td><strong>Geen interesse/Negatief (telt wel voor agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><strong>500</strong></td>
<td>Negatief</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>501</td>
<td>Geen interesse</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>510</td>
<td>Niet meer telefonisch benaderen (Bel-me-niet)</td>
<td>Zie ook 210 en 410</td>
</tr>
<tr class="odd">
<td></td>
<td>525</td>
<td>Valt buiten doelgroep</td>
<td>Zie ook 225</td>
</tr>
<tr class="even">
<td>6</td>
<td><strong>Positief (niet voor Agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>610</td>
<td>Informatie sturen per post</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>611</td>
<td>Informatie sturen per email</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>612</td>
<td>Informatie sturen per post (+nabellen)</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>613</td>
<td>Informatie sturen per email (+nabellen)</td>
<td></td>
</tr>
<tr class="odd">
<td>7</td>
<td><strong>Positief (ook voor Agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><strong>700</strong></td>
<td>Positief</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><strong>705</strong></td>
<td>Aangenomen</td>
<td>Systeemstatus antwoordservicemodule</td>
</tr>
<tr class="even">
<td></td>
<td><strong>706</strong></td>
<td>Doorverbonden</td>
<td>Systeemstatus Antwoordservicemodule</td>
</tr>
<tr class="odd">
<td></td>
<td>710</td>
<td>Informatie sturen per post</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>711</td>
<td>Informatie sturen per email</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>712</td>
<td>Informatie sturen per post (+nabellen)</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>713</td>
<td>Informatie sturen per email (+nabellen)</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>715</td>
<td>Stuur bevestiging</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><strong>780</strong></td>
<td>Afspraak</td>
<td>Systeemstatus. Een ingeplande adviseur afspraak</td>
</tr>
<tr class="odd">
<td></td>
<td>781</td>
<td>Afspraak (adviseur)</td>
<td>Eigen afspraak door een adviseur ingeboekt via CallProPortal</td>
</tr>
<tr class="even">
<td></td>
<td>782</td>
<td>Afspraak verzet</td>
<td>Een verzetting die via outbound is gedaan. Meestal nabeltrajecten. Alleen een functionele status, het belscript moet dit zelf regelen!</td>
</tr>
<tr class="odd">
<td></td>
<td>783</td>
<td>Afspraak geannuleerd</td>
<td><p>Een annulering die via outbound is gedaan. Meestal nabeltrajecten.</p>
<p>Alleen een functionele status, het belscript moet dit zelf regelen!</p></td>
</tr>
<tr class="even">
<td></td>
<td>785</td>
<td>Afspraak (+nabellen)</td>
<td>Voor CallPro een terugbellen code</td>
</tr>
<tr class="odd">
<td>8</td>
<td><strong>Gereserveerd (niet voor de Agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>9</td>
<td><strong>Gereserveerd (ook voor de Agent)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

### Scriptdefinitie

Een scriptdefinitie beschrijft de scriptvelden, en belopdrachtstatussen
die kunnen worden gebruikt in een belscript of callflow. Een bellijst
wordt aangemaakt op basis van een scriptdefinitie. Bij het aanmaken van
een nieuwe scriptdefinitie kunnen de instellingen van een bestaande
scriptdefinitie worden overgenomen.

![](./media/image3.png)

In de scriptdefinitie wordt alleen de startpagina van het belscript
vastgelegd. Als het belscript op een webserver (http) staat kan deze
niet via de “Bladeren…” knop worden gekozen maar moet de volledige url
worden ingetypt.

![](./media/image4.png)![](./media/image5.png)

In stap3 worden alle velden die in het belscript worden gebruikt, en/of
die moeten worden geimporteerd vastgelegd. Soms worden velden via het
importbestand aangeleverd die later terug moeten worden geleverd aan de
opdrachtgever, maar tijdens het bellen niet van belang zijn. Deze velden
worden dan wel in de scriptdefinitie (en ook de importdefinitie)
opgenomen. De scriptdefinitie bevat ook velden die niet in het
importbestand staan, maar wel nodig zijn in het belscript (gegevens
verrijking). Ook kan het zijn dat er stuurvelden worden opgenomen in de
scriptdefinitie die worden gevuld afhankelijk van de wijze waarop het
belscript/de callflow wordt doorlopen.

Per scriptveld wordt in ieder geval vastgelegd wat de naam, het datatype
en de lengte is. Aanvullend kunnen voor de autoscript omgeving nog een
Vraag, en de weergave van het scriptveld worden vastgelegd. Deze
informatie wordt alleen gebruikt i.c.m. de autoscript functie van
CallPro.

![](./media/image6.png) ![](./media/image7.png)

In de scriptdefinitie wordt aangegeven welke velden een telefoonnummer
bevatten. Dit is belangrijk zodat CallPro de telefonie kan aansturen en
telefoonnummers automatisch kan bellen. Een andere belangrijke
instelling zijn de ontdubbelvelden. Door een of meer velden aan te
vinken kan worden vastgelegd dat alleen belopdrachten mogen worden
geïmporteerd die een unieke waarde bevatten voor deze velden. Meestal
wordt hiervoor het telefoonnummer gebruikt.

![](./media/image8.png) ![](./media/image8.png)

De scriptdefinitie legt ook vast welke belopdrachtstatussen gebruikt
kunnen worden (stap 6). Tijdens het bellen kunnen Agents alleen de hier
geselecteerde belopdrachtstatussen gebruiken om gesprekken af te
coderen.

![](./media/image9.png) ![](./media/image10.png)

![](./media/image11.png)
![](./media/image12.png)

Nu is de scriptdefinitie klaar, en kan een bellijst worden gemaakt
gebaseerd op deze scriptdefinitie.

### Importdefinitie

In CallPro wordt een importdefinitie gebruikt om adressen te importeren
in een bellijst. Op basis van het aangeleverde importbestand, en de
bellijst, wordt met de importdefinitie bepaald welke velden in de
bellijst worden gevuld met de gegevens uit het importbestand. Een
importdefinitie kan worden gemaakt aan het einde van de Bellijst wizard,
of direct vanuit het control panel.

Vanuit de Importdefinitie folder kan met right-click
Nieuwe\\Importdefinitie... een nieuwe importdefinitie worden aangemaakt.

![](./media/image13.png) ![](./media/image14.png)
![](./media/image15.png) ![](./media/image16.png)

Afhankelijk van het gekozen bestandstype moeten verschillende
instellingen worden gedaan. De meest voorkomende bestanden die worden
aangeleverd zijn “CSV (Comma delimited)” of “MS Excel”. Bij de eerste
moet worden gelet op het veldscheidingsteken, en of de velden worden
gemarkeerd met quotes. Ook herkend CallPro dan het telefoonnummer
meestal als numeriek veld, terwijl dit in CallPro een karakter veld is.
Bij Excel bestanden worden vaak het veldtypes (stap 6) op karakter 255
gezet. Ook kan het zijn dat de lijst met Gegevens bronnen verschilt per
computer als zowel de Nederlandstalige Excel als de Engelstalige Excel
binnen het call center wordt gebruikt.

![](./media/image17.png) ![](./media/image18.png)

![](./media/image19.png) ![](./media/image20.png)

Sommige Excel sheets bevatten tabbladen met namen die niet geldig zijn
in CallPro. Als in stap 5 na de selectie van het Excel bestand en het
tabblad ene foutmelding volgt als onderstaande

![](./media/image21.png)

Dan bevat het tabblad in Excel mogelijk tekens die niet geldig zijn.
Tekens die niet altijd werken zijn \*%\!\\/-

In stap 6 worden de velden uit het importbestand (Externe naam)
gekoppeld aan de velden uit de bellijst (Interne naam). Velden die niet
nodig zijn hoeven ook niet te worden geïmporteerd, vul dan geen veld in
bij Interne naam. Velden kunnen alleen gekoppeld worden als het datatype
overeenkomt, en ook de lengte van het Interne veld groter of gelijk aan
de lengte van het Externe veld, dit om gegevensverlies te voorkomen.
Soms herkend CallPro een veld als numeriek (omdat er alleen cijfers in
het veld staan) terwijl die bijvoorbeeld karakter moet zijn. Corrigeer
dan het datatype om het veld te kunnen koppelen.

![](./media/image22.png) ![](./media/image23.png)
![](./media/image24.png)

In stap 7 kan een standaard filter worden ingesteld op de
importdefinitie die bij elke import automatisch wordt ingevuld. In de
meeste gevallen moeten alle records uit het importbestand worden
ingelezen en zal dit leeg blijven. In Stap 8 wordt aangegeven wat er
moet gebeuren met ongeldige telefoonnummers tijdens de import, weigeren
(niet importeren) of importeren met een speciale systeemstatus.

Tot slot krijgt de import definitie in de laatste stap een naam.

### Exportdefinitie

TODO

### Zoeken tools

Voor supervisie staan hier een aantal handige zoek tools zoals de
Belopdracht/Prospect zoeken, Belpogingen zoeken, Afspraken zoeken,
Resources zoeken, Sessies zoeken en bel-me-niet registraties zoeken.

![](./media/image25.png)![](./media/image26.png)
![](./media/image27.png)
![](./media/image28.png)![](./media/image29.png)![](./media/image30.png)

### Campagne grid

Ook het Campagne Grid is een handige tool om agents snel op andere
campagnes in te delen, of om overzicht te houden over de campagnes en
agents die hieraan zijn toegekend.

![](./media/image31.png)![](./media/image32.png)

Via het context-menu kunnen speciale acties worden ingesteld zoals
“alleen terugbellers” of “morgen”. Via dubbelklikken kan snel een
Agent aan of uit worden gezet voor een specifieke campagne.

De speciale opties Vandaag en Morgen stellen de campagne koppeling zo in
dat de Agent alleen vandaag, of morgen actief is voor de betreffende
campagne. Ook kunnen alle koppeling voor 1 campagne, of alle koppeling
van 1 agent in een keer worden ingesteld. Activeer hiervoor het
context-menu op resp. de campagne of de agent naam.

Meerder campagne grid instellingen kunnen als template worden bewaarde.
Bijvoorbeeld om meerdere teams overzichtelijk in hun eigen overzicht te
gebruiken.

## Systeemconfiguratie

#### Algemeen

Hier kunnen enkele losse instellingen worden gedaan zoals het
verversingsinterval voor de Quota. Deze staat standaard op 2 minuten.
Door dit op een langer interval te zetten worden de quota’s minder vaak
herberekend, dit ontlast de SQL server. Het nadeel hiervan is dat de
quota’s meer over de grens heen gaan omdat de controle minder vaak wordt
gedaan.

Standaard geeft CallPro voorrang aan terugbelopdrachten over alle
campagnes waar een Agent op belt. Dus zelfs al een campagne met een
lagere prioriteit (hogere prioriteit waarde) is gekoppeld zal een
terugbeller in die campagne toch voorrang krijgen. Als dit niet gewenst
is, maar puur op Prioriteitsvolgorde gestuurd moet worden dan dient het
vinkje bij deze instelling uitgeschakeld te worden.

De passieve tijdregistratie instelling bepaald of CallPro indien een
Agent enige tijd (instelbaar) niets doet met zijn muis of toetsenbord
een passief sessie record start. CallPro werkt met pauze en aangemelde
sessie records die kunnen worden gebruikt voor een eenvoudige inlog-
uitlog tijdsregistratie. Om misbruik van de wrapup fase te voorkomen kan
deze instelling worden geactiveerd. CallPro markeert de tijd dat een
Agent niets doet dan als “Passief” die apart in de sessie rapportage
zichtbaar wordt.

CallPro is een Nederlands programma en de taal staat dan ook standaard
in het Nederlands. Overschakelen op Engels is ook mogelijk, maar de
derde taal (Frans) is niet vertaald.

Met de instelling serverbelasting kan de impact van een import op de SQL
Server worden beperkt. Zeker als er meer dan 20 Agenten zijn ingelogd is
het verstandig om deze instelling te verlagen. Standaard staat deze op
100%, de maximale importsnelheid. Een lagere waarde resulteert in een
iets lagere importsnelheid. Maar de lopende campagnes hebben er minder
last van.

Wij raden aan om deze instelling voor call center met 20 simultane
gebruikers op 60% te zetten en bij meer dan 60 ingelogde agenten op 20%
als tijdens het bellen ook een import wordt uitgevoerd.

#### Script-omgeving

Deze instelling bepaald de standaard pagina’s voor Pauze en inbound. Op
werkplek (Seat) niveau kunnen deze pagina’s anders worden ingesteld.

![](./media/image33.png)

#### Diagnose 

TODO

#### Bestandslokaties

CallPro plaatst logbestanden in de Windows folder voor tijdelijke
bestanden (zie variabele TEMP). Dit is meestal de folder
C:\\WINDOWS\\TEMP of de Temp folder in de gebruikers profiel folder
c:\\documents and settings\\\<gebruiker\>\\temp.

Door hier een netwerkfolder te gebruiken worden alle logbestanden van
CallPro en alle error informatie bestanden naar die centrale plaats
geschreven. Zorg ervoor dat alle ingelogde gebruikers schrijfrechten
hebben op deze folder anders kunnen de logbestanden niet worden
aangemaakt.

#### Systeem scriptvelden

CallPro heeft weinig kennis van de velden die in bellijsten worden
gebruikt. Om toch bij bijvoorbeeld het zoeken een optie te kunnen geven
om op “Achternaam” te zoeken zijn een aantal systeemvelden aanwezig.
Extra velden kunnen worden toegevoegd die als “Zoekveld” zijn gemarkeerd
en door CallPro dan bij de optie “Zoeken belopdrachten” worden gebruikt.
Als een veld in de bellijst niet aanwezig is wordt het zoekveld grijs.

![](./media/image34.png)
![](./media/image35.png)

#### Pauze types

CallPro houdt de pauzetijd van Agenten bij. Telkens als wordt ingelogd
komt de Agent in pauze. Ook tijdens het bellen kan de Agent aangeven na
het huidige gesprek naar pauze te willen gaan. Met Pauze types kunnen
verschillende soorten pauze worden vastgelegd. Pauze types kunnen worden
gekoppeld aan een campagne zodat ook de pauzetijd aan een campagne kan
worden gerelateerd in (maatwerk) rapportages.

![](./media/image36.png)

Alleen het Pauze type “Pauze” is standaard aanwezig. De keuze optie is
ook alleen zichtbaar als het vinkje bij “Gebruiker kan de volgende
(actieve) pauze types kiezen” is gezet.

Ook wordt hier ingesteld in welk pauze type CallPro begint na het
inloggen, en na het expliciet afmelden van de Agent en na het geforceerd
afmelden door CallPro.

#### Geavanceerd

Dit is een verzameling van specifieke instellingen die hier verder niet
worden behandeld. Pas deze instellingen alleen aan indien hier expliciet
door Calway om wordt gevraagd.

## Resources

De centrale plaats waar agents, call-lists (bellijsten) en Calendars
(agenda’s) worden aangemaakt en beheerd. Voor het overzicht kunnen
sub-folders worden gemaakt om agenten te groeperen per team of
vestiging, bellijsten te groeperen per opdrachtgever of campagne en
Agenda’s per opdrachtgever of regio. De indeling kan volledig op de
eigen werkwijze worden afgestemd.

![](./media/image37.png)

Elke resource heeft een unieke code (ID) die op het eigenschappen scherm
wordt weergegeven. Daarnaast heeft een resource een Naam, een
omschrijving en een type. Ven een resource is te zien wie deze heeft
aangemaakt, en wanneer en door wie deze voor het laatst is gewijzigd.
Een resource kan actief zijn, of inactief waarmee het gebruik ervan kan
worden uitgesloten.

Afhankelijk van het type resource zijn er extra eigenschappen die kunnen
worden vastgelegd.

### Agent

Een Agent resource representeert een gebruiker, of account. Dit kan een
beller (telemarketeer) zijn, of een supervisor, een buitendienst
medewerker, of zelfs een externe klant. Bijna alle activiteiten worden
gekoppeld aan de gebruiker die deze activiteit uitvoert.

Een Agent heeft ook een account en password om mee in te loggen in de
diverse onderdelen van CallPro. Op basis van het account en de daaraan
gekoppeld Rollen wordt bepaald welke onderdelen van CallPro beschikbaar
zijn voor deze gebruiker. Voor een beller kan worden vastgelegd of de
gesprekken die hij/zij doet via de scriptmodule worden opgenomen of niet
(dit werkt alleen als de benodigde telefonie hardware aanwezig is en
geconfigureerd). Daarnaast kan van de Agent nog enige persoonlijke
gegevens worden vastgelegd:

![](./media/image38.png) ![](./media/image39.png)

Deze gegevens worden grotendeels in CallPro verder niet gebruikt en zijn
puur voor de administratieve vastlegging. Andere gegevens zijn alleen
voor bepaalde gebruikers van belang. Voor een buitendienst medewerker
die via CallPro Portal kan inloggen is de “Eigenaar van Agenda’s”
koppeling essentieel om zijn agenda te kunnen bekijken.

### Call-list

Een bellijst is een resource waar een lijst met belopdrachten aan is
gekoppeld. Ook belpogingen zijn gekoppeld aan de bellijst. Een bellijst
wordt gemaakt op basis van een scriptdefinitie en wordt gevuld door
bestanden te importeren met een importdefinitie. Bij het aanmaken van de
bellijst kan worden vastgelegd of de belopdrachten tijdens de import
moeten worden ontdubbeld op ene bepaald veld, of veldcombinatie.

De bellijst heeft diverse extra instellingen zoals de koppeling van
terugbelopdrachten aan de agenten, belpoging begrenzing instellingen en
actieve prioritietscategorieën. Deze instellingen worden deels via de
scriptdefinitie overgenomen, en deels ingesteld tijdens het aanmaken van
de bellijst. Veel van deze instellingen kunnen ook achteraf worden
gewijzigd, maar van sommige kan dat niet. Later in dit handboek gaan we
dieper in op deze instellingen.

![](./media/image40.png) ![](./media/image41.png)
![](./media/image42.png)

Van elke bellijst is te zien hoeveel adressen deze bevat en welke
belopdrachtstatus deze belopdrachten op dit moment hebben. Ook wordt
hier onderscheid gemaakt tussen actieve en inactief belopdrachten.
Inactieve belopdrachten staan wel in de bellijst, maar worden door
CallPro niet aangeboden voor outbound bellen.

![](./media/image43.png) ![](./media/image44.png)

Bij de bellijst worden ook de suppressielijst instellingen bewaard die
worden gebruikt voor bel-me-niet.

### Calendar

De Calendar resource wordt gebruikt voor het inplannen van
bezoekafspraken voor een adviseur of buitendienst medewerker. Voor de
weergave van de agenda kunnen enkele instellingen worden gedaan w.o.
kleurinstellingen. Ook instellingen over het gebruikt zoals de
inboekperiode in de toekomst, en de afspraakduur en reistijdberekening
zijn hier te vinden.

![](./media/image45.png) ![](./media/image46.png)

Voor het inplannen van afspraken zijn in de Agenda “agendablokken”
vastgelegd. Afspraken kunnen alleen worden ingepland op de tijden van
deze agendablokken.

![](./media/image47.png) ![](./media/image48.png)

Ook voor algemene gebeurtenissen is een voorziening. Hiermee kunnen
vaste rayon meetings, vakantie of andere afspraken worden vastgelegd
zodat op deze tijdstippen geen afspraken worden ingepland.

![](./media/image49.png) ![](./media/image50.png)

### Seat

De Seats (werkplek) wordt hoofdzakelijk gebruikt voor telefonie
instellingen. Door de werkplek op inactief te zetten kan worden
voorkomen dat iemand inlogt met de script module om te gaan bellen. Dit
kan bijvoorbeeld worden gebruikt voor stille hoekjes in het callcenter
die niet altijd beschikbaar moeten zijn.

![](./media/image51.png) ![](./media/image52.png)
![](./media/image53.png) ![](./media/image54.png)

## Groups

TODO

## Campaigns

Ook de campagnes hebben hun eigen plaats en ook hier geldt dat de
indeling volledig kan worden afgestemd op de werkwijze van het call
center, of de opdrachtgevers.

![](./media/image55.png)

Campagnes worden gemaakt onder de “Campaigns” folder. Alleen actieve
campagnes worden door CallPro gebruikt. Ook de prioriteit van een
campagne kan hier worden ingesteld.

Op de campagne worden de telefonie (dialer) instellingen gedaan op het
dialer tabblad. Voor outbound wordt de dialing mode gekozen en bij
inbound kan een wachtrij worden gekozen. Ook wordt hier aangegeven of
gespreksopnames moeten worden gemaakt.

![](./media/image56.png)
![](./media/image57.png)![](./media/image58.png)

## Snelkoppelingen

Nu we hebben gekeken naar resources en de campagne folder is het
belangrijk om duidelijk te maken dat resources worden gekoppeld in de
campagne folder via een “koppeling”. Dit verschil is belangrijk en is
ook zichtbaar in de Resource Explorer. Dit zijn koppelingen:

![](./media/image59.png)

En dit zijn (agent) resources:

![](./media/image60.png)

Bij een koppeling opent via right-click “Eigenschappen” het
eigenschappen venster van de koppeling. Om de Resource eigenschappen te
openen van een koppeling moet in het right-click menu worden gekozen
voor de optie “Eigenschappen \<resource type\>”. Als een koppeling wordt
weggegooid blijft de onderliggende resource bestaan en wordt alleen de
koppeling verwijderd in de betreffende folder. Als de onderliggende
resource wordt weggegooid dan worden ook alle koppelingen naar deze
resource weggegooid\! Afhankelijk van het resource type wordt ook alle
bijbehorende informatie verwijderd.

# Scriptmodule

TODO

## Agenda module

TODO

# CallProPortal

Zie de CallproPortal handleiding.

# Belangrijke conventies in CallPro

## Hoe biedt CallPro een belopdracht aan

CallPro doorloopt meerdere fasen bij het ophalen van een nieuwe
belopdracht. Deze stappen beschrijven het gedrag zoals dit standaard
ingesteld staat. Diverse instellingen kunnen deze volgorde beïnvloeden.

1.  Kijk over alle gekoppelde campagnes en actieve bellijsten in deze
    campagnes naar belopdrachten in de terugbellen categorie
    (terugbellen hoog) die moeten worden aangeboden. Biedt de eerste
    belopdracht aan die op basis van prioriteit binnen de terugbellen
    categorie, en terugbeltijd moet worden gebeld.

2.  Kijk over alle gekoppelde campagnes en actieve bellijsten in deze
    campagnes naar belopdrachten in de terugbellen categorie
    (terugbellen laag) die moeten worden aangeboden. Biedt de eerste
    belopdracht aan die op basis van prioriteit binnen de terugbellen
    categorie, en terugbeltijd moet worden gebeld.

3.  Kijk over gekoppelde campagnes en actieve bellijsten in deze
    campagnes op volgorde van campagne prioriteit en daarbinnen bellijst
    prioriteit naar de belopdrachten in de resterende categorieën (niet
    bereikt hoog, systeem en niet bereikt laag). Biedt de eerste
    belopdracht aan die op basis van de prioriteit binnen deze
    categorieën, en terugbeltijd moet worden gebeld.
