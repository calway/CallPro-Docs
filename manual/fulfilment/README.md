# Fulfilment handleiding
De Mergetool is een krachtige tool waarmee allerhande fulfilment acties of andere nabewerkingsacties kunnen worden geautomatiseerd. Mogelijkheden van de tool zijn het automatisch e-mailen, brieven maken, wijzigingen doorvoeren in de database, communiceren met externe bronnen (webservices & API’s).

De Mergetool is eenvoudig in gebruik, maar vergt wel enige kennis voor het inrichten van de juiste acties. Vereiste voorkennis voor succesvol gebruik zijn:

# Inhoud

[Het configuratiebestand](./configuration.md)

[Loops en Actions](./loops-actions.md)

[Loops](./loop-commands.md)

[Actions](./action-commands.md)

* [Api](./api-action-command.md)
* [Email](./email-action-command.md)
* [Export](./export-action-command.md)
* [FileCopy](./filecopy-action-command.md)
* [Ftp](./ftp-action-command.md)
* [Import](./import-action-command.md)
* [Merge](./merge-action-command.md)
* [Pdf](./pdf-action-command.md)
* [Resource](./resource-action-command.md)
* [Set](./set-action-command.md)
* [Sms](./sms-action-command.md)
* [Sql](./sql-action-command.md)
* [Tag](./tag-action-command.md)
* [Url](./url-action-command.md)
* [Webservice](./webservice-action-command.md)
* [Zip](./zip-action-command.md)








## Systeemvelden
De fulfilmentservice kent een aantal systeemvelden die beschikbaar zijn in de collectie `SYS`, `ENVIRONMENT` en `VARIABLE`. Onder `SYS` staan enkele systeemvelden, en `ENVIRONMENT` bevat alle environment variabelen op de server. Onder `VARIABLE` worden gebruiker instellingen vastgelegd uit de config sectie `variables`. Onderstaande is een voorbeeld van de standaard inhoud.

<table><tr><td valign=top>SYS</td><td valign=top>VERSION</td><td valign=top><b>5.03</b></td></tr><tr><td valign=top>SYS</td><td valign=top>VERSIONMAJOR</td><td valign=top><b>5</b></td></tr><tr><td valign=top>SYS</td><td valign=top>VERSIONMINOR</td><td valign=top><b>0</b></td></tr><tr><td valign=top>SYS</td><td valign=top>VERSIONPATCH</td><td valign=top><b>3</b></td></tr><tr><td valign=top>SYS</td><td valign=top>VENDOR</td><td valign=top><b>Calway Nederland b.v.</b></td></tr><tr><td valign=top>SYS</td><td valign=top>VENDORURL</td><td valign=top><b>https://www.calway.nl</b></td></tr><tr><td valign=top>SYS</td><td valign=top>DATETIME</td><td valign=top><b>08-12-2020 15:31:45</b></td></tr><tr><td valign=top>SYS</td><td valign=top>DATE</td><td valign=top><b>08-12-2020</b></td></tr><tr><td valign=top>SYS</td><td valign=top>TIME</td><td valign=top><b>15:31:45</b></td></tr><tr><td valign=top>SYS</td><td valign=top>FILLER</td><td valign=top><b></b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>COMMANDLINE</td><td valign=top><b>Mergetool  -Eval</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>CURRENTDIRECTORY</td><td valign=top><b>C:\data\app\mergetool</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>MACHINENAME</td><td valign=top><b>JOHAN</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>OSVERSION</td><td valign=top><b>Microsoft Windows NT 6.2.9200.0</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>USERDOMAINNAME</td><td valign=top><b>AzureAD</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>USERNAME</td><td valign=top><b>JohanBennink</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>DOTNETVERSION</td><td valign=top><b>4.0.30319.42000</b></td></tr><tr><td valign=top>ENVIRONMENT</td><td valign=top>INTERACTIVE</td><td valign=top><b>True</b></td></tr></table>

## Format opties
Bij ieder veld kunnen format specifiers worden meegegeven die bepalen hoe de
uiteindelijke waarde opgebouwd/weergegeven gaat worden. Er kunnen 0 of meer format specifiers bij 1 veld worden meegegeven. Bijvoorbeeld:

`%SCRIPT.CONTRACTDATE \DTddMMyyyy \ALC#12%`

Geeft als de huidige datum **01-04-2005** is als resultaat:

`##01042005##`


<table>
<tr>
<th>Code</th>
<th>Betekenis</th>
</tr>
<tr>
<td>AL</td>
<td>
Alignment van de tekst.
[L|C|M|R]<character><width>
<br/>L=links uitlijnen
<br/>C of M=centreren
<br/>R=rechts uitlijnen
<br/>Character is het uitlijn tekens. Bijvoorbeeld een spatie ‘ ‘
<br/>Width is de lengte van het veld.
<br/>\ALR 10 geeft een rechts uitgelijn veld van 10 posities waarbij het uitlijnteken een spatie is.
</td>
</tr>
<tr>
<td>CC</td>
<td>
Hoofdletter/kleineletter conversie
<br/>0|1|2|3|4
<br/>0=De eerste letter wordt een hoofdletter, de rest klein.
<br/>1=Iedere eerste letter (na spatie of -) wordt een hoofdletter.
<br/>2=Alles hoofdletters
<br/>3=Alles kleine letters
<br/>4=Initialen, resultaat is een lijst met letters en punten.
</td>
</tr>
<tr>
<td>CO</td>
<td>Zelfde als de IF, maar dan met een “bevat" vergelijking i.p.v. gelijk-aan
</td>
</tr>
<tr>
<td>CU</td>
<td>Change the current culture (restore afterwards to original culture).
\CU"nl-NL" or \CU"fr-FR"
</td>
</tr>
<tr>
<td>DT</td>
<td>
Specificeer een datum/tijd formaat. Er kan gebruik worden gemaakt van
de volgende combinaties (volledige lijst op <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings" target="_blank">docs.microsoft.com</a>:<br/>
<br/>dddd, MMMM dd yyyy :Thursday, August 17 2015
<br/>ddd, MMM d "'"yy :Thu, Aug 17 '15
<br/>dddd, MMMM dd :Thursday, August 17
<br/>M/yy :8/15
<br/>dd-MM-yy :17-08-15
<br/>ddMMyyyy :17082015
<br/>dd-MM-yyyy HH:mm : 17-08-2015 09:15
</td>
</tr>
<tr>
<td>FL</td>
<td>Floatingpoint format function
\FL "<format>"
Format is een C# format specifier voor floating points zoals beschreven op <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings" target="_blank">docs.microsoft.com</a>:<br/>
<br/>f2: 2 decimalen 12.34
<br/>f1: 1 decimaal 12.3
<br/>p2: 2 decimale percentage 12.34 %
<br/>c2: 2 decimale bedragen &euro; 12.34
</td>
</tr>
<tr>
<td>FS</td>
<td>Filename safe. Vervangt illegale karakters in de filename door een _ zodat
de filenaam geldig is.
</td>
</tr>
<tr>
<td>IF</td>
<td>If then else constructie
\IF “condition"?"then-value":"else-value"
Condition, then-value en else-value mogen zowel constante teksten zijn,
als velden.
Bijvoorbeeld: %R.COUNTRY% \IF "NL"?"%R.ZIP R.CITY%":"%R.CITY
R.ZIP%"
</td>
</tr>
<tr>
<td>JS</td>
<td>Json safe
Maakt een string veilig voor gebruik in een json string. Dit vervangt alle:
<ul>
<li> " door '</li>
<li> crlf, cr, lf door spatie</li>
<li> tab door spatie</li>
<li> \ door \\</li>
</ul> 
</td>
</tr>
<tr>
<td>LS</td>
<td>Line safe
Vervang alle CR en LF door een spatie.
</td>
</tr>
<tr>
<td>PS</td>
<td>Filename+path safe. Vervangt illegale karakters door een _ in een volledig
file+path naam.
</td>
</tr>
<tr>
<td>QS</td>
<td>Quote save. Vervangt enkele quotes door dubbele.
Het quote karakter moet mee worden gegeven als parameter
Bijvoorbeeld: \QS’
</td>
</tr>
<tr>
<td>RE</td>
<td>Replace commando
Vervang een zoektekst voor een vervangtekst, bijvoorbeeld:
%CL.ENTRYNOTE \RE"\r\n","< BR/ >"
Vervangt alle [CR][LF] door < BR />
</td>
</tr>
<tr>
<td>SD</td>
<td>
Switch commando, gelijk aan SW maar nu is de laatste optie een default waarde.
Kommagescheiden lijst. Werkt als volgt:
"a","1","b","2","c","3","","-1"
Als de veldwaarde a is wordt een 1 weergegeven
Als de veldwaarde b is wordt een 2 weergegeven
Als de veldwaarde c is wordt een 3 weergegeven
Als geen enkele waarde matcht, dan wordt de laatste waarde -1 weergegeven. De match waarde moet hiervoor "" zijn.

Binnen de " " mogen ook weer velden worden gebruikt.
Als de veldwaarde niet voorkomt wordt er niets vervangen.
</td>
</tr>
<tr>
<td>SU</td>
<td>Substring constructie
Hello world \SU6,5 haalt een substring op beginnend op
positie 2
(zero based!) met lengte 4. Dus dit levert <b>world</b> op
</td>
</tr>
<tr>
<td>SW</td>
<td>
Switch commando (ook wel case of decode genoemd)
Kommagescheiden lijst. Werkt als volgt:
"a","1","b","2","c","3"
Als de veldwaarde a is wordt een 1 weergegeven
Als de veldwaarde b is wordt een 2 weergegeven
Als de veldwaarde c is wordt een 3 weergegeven

Binnen de " " mogen ook weer velden worden gebruikt.
Als de veldwaarde niet voorkomt wordt er niets vervangen.
</td>
</tr>
<tr>
<td>TF</td>
<td>Formateer het telefoonnummer.
<br/>Gebruik:
<br/>F - Netnummer – abonneenummer (050-5275525)
<br/>N - alleen netnummer (050)
<br/>A - alleen abonnenummer (5275525)
<br/>Dit herkent alleen Nederlandse en Belgische netnummers.
</td>
</tr>
<tr>
<td>TR</td>
<td>Spaties links en/of rechts worden verwijderd.
<br/>L|R|A
<br/>L - verwijder spaties voor de tekst
<br/>R - verwijder spaties na de tekst
<br/>A – L en R (default)
</td>
</tr>
<tr>
<td>UL</td>
<td>URL Encode the input string</td>
</tr>
<tr>
<td>XX</td>
<td>Encrypt de waarde m.b.v. de actieve cryptokey</td>
</tr>
</table>