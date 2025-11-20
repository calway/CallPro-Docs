### Belopdrachtstatussen

In CallPro kunnen zeer eenvoudig belopdrachtstatussen worden aangemaakt.

[TODO standaard instellingen]

Per belopdracht kan ook een terugbel rooster worden ingesteld via de belopdrachtstatus, maar ook los van de belopdrachtstatus kan deze worden aangepast. Zie [uitgebreide terugbel roosters](belopdrachtstatus-terugbel-rooster-v510.md)

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

