### Merge action
De merge actie is de meest voorkomende actie die wordt gebruik om uitvoer te genereren. Deze actie neeemt een input template en genereert output in een bestand.
```xml
<Action Type="Merge">
    <Input source="BLOB|FILE">inputtemplate</Input>
    <Output Append="yes|no"
        EOL="windows|unix|<characters>"
        Encoding="<encoding>">outputfile</Output>
</Action>
```
De input template kan uit de database komen, of uit een bestand. Voor bestanden worden enkele typen herkend zoals Word (extensie .docx) of Excel (extensie .xlsx) of tekstbestanden.

#### Word
Voor het gebruik van Word als merge template dient de `source=file` te worden gebruikt en moet het bestand de .docx extensie hebben (en uiteraard een Microsoft Word bestand zijn). Van ieder record wordt een input template gemerged.

#### Excel
Om Excel als input template te gebruiken voor een merge dient dit bestand aan enkele voorwaarden te voldoen.

1. Het bestand moet een Excel bestand zijn met extensie .xlsx
2. Het Excel bestand moet minimaal 1 worksheet bevatten.
3. Regel 1 in het Excelbestand bevat de header regel en regel 2 in het excel bestand bevat de detail regel.
4. Indien per export record meerdere Excel rijen geschreven moeten worden dan moet een named region (CTRL-F3) gemaakt worden`header`en een named region `detail` die de betreffende onderdelen bevatten. Zo kan data over meerdere rijen worden verdeeld.

```xml
<Action Type="Merge">
    <Input Sheet="belopdrachten">inputtemplate.xlsx</Input>
    <Output Sheet="%SYS.DATE%">output-%SYS.DATE%.xlsx</Output>
    <MergeCopy>infosheet</MergeCopy>
    <Copy>pivotsheet</Copy>
    <Copy>grafieksheet</Copy>
</Action>
```
Standaard gedragsregels bij Excel merges:
1. Wanneer er meerdere sheets in de input Excel staan worden deze standaard
gekopieerd naar de output Excel als het output bestand nog niet bestaat.
2. Als binnen de actie 1 of meer `<MergeCopy>` of `<Copy>` tags worden gevonden dan worden alleen de sheets vermeld in deze tags overgenomen van de input Excel naar de output Excel en ook alleen bij aanmaken van de output Excel.
3. Een `<Copy>` tag kopieert de bronsheet naar de output Excel.
4. Een `<MergeCopy>` tag kopieert de bronsheet ook naar de output Excel maar voert ook een merge uit op eventuele merge-expressies op deze sheet.
5. De output sheet wordt altijd aangemaakt als die nog niet bestaat in de output
Excel.
6. Als in de output Excel een sheet reeds bestaat worden regels toegevoegd aan
de reeds aanwezige regels in de betreffende sheet.

#### Tekstbestand
Het resultaat van de input template wordt geschreven naar de outputfile. Met de attribuut `append=yes` kan worden bepaald of een bestaand bestand wordt uitgebreidt, of overschreven. 

De optionele `Encoding` attribuut geeft aan welke encoding wordt gebruikt om het output bestand te maken en te schrijven. Mogelijke encodings zijn:
* utf-8 - Windows default
* utf-7 - Only use for legacy, this encoding is less secure
* utf-16 - also known as unicode
* utf-16BE - Bigendian Unicode
* unicode - Windows default unicode encoding
* utf-32
* us-ascii

> Let op: Wanneer een input template meerdere keren gemerged moet worden gebruik dan source="file" bij de `<input>` tag. Zonder deze toevoeging wordt het inputbestand “slechts" 1x gemergd.
