### PDF action
```xml
<Action Type="PDF" Engine="EO|essentialobjects" EmbedFonts="YES|NO">
    <InputFile Source="BLOB|FILE"
        Location="header|footer|content">inputtemplate</InputFile>
    <OutputFile>outputfile</OutputFile>
    <Margins>l;r;t;b;h;f</Margins>
    <Page>DEF|w;h</Page>
</Action>
```
M.b.v. van deze actie van van een html template een pdf bestand worden gemaakt. Dit bestand kan vervolgens worden gebruikt als email bijlage. Voor de actie is een licentie nodig op de pdf engine. Voor de pdf-engine is EO de standaard. De `Margins` instellingen zijn optioneel. De parameters voor de margins zijn als volgt (puntkomma gescheiden):

| | | 
| - | - |
| l | Linker marge |
| r | rechter marge |
| t | bovenkant marge |
| b | onderkant marge |
| optioneel:||
| h | positie van de header vanaf de bovenkant van het papier |
| f | positie van de footer vanaf de bovenkant van het papier |

Alle settings moeten in cm of in inch. De parameter bestaat dus uit 4 of 6 cijfers, allemaal gevolgd door of cm of inch. Uiteraard moet alles of in inch, of in cm, dus geen mix!
Bijvoorbeeld (default settings):
```xml
<Margins>2.0cm;2.0cm;2.0cm;2.0cm;1.0cm;27.0cm</Margins>
``` 
Een pagina kan worden opgemaakt met drie afzonderlijke html delen, de header, de
footer en de content(body). Header en Footer zijn (evenals margins) optioneel.
Daarnaast kan nog de pagina size worden opgegeven. Deze staat standaard op A4. De parameter bestaat uit een voor gedefinieerde paginagrootte zoals A4, A3, Letter etc., of uit een breedte en hoogte in cm of inch. Bijvoorbeeld: 21.0cm;29.7cm

![page-size](page-size.png)
