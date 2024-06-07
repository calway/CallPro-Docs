### FileCopy Action
```xml
<Action Type="FILECOPY">
    <Sourcefile>filename1</Sourcefile>
    <Destinationfile Overwrite="YES|NO" Compress="YES|NO">filename2</Destinationfile>
</Action>
```
Deze actie kan worden gebruikt om een file te kopiëren. Als de destinationfile al bestaat en overwrite = YES dan wordt de file overschreven door eerst de oude te verwijderen. De compress optie kan optioneel meegegeven worden om het uitvoerbestand de gzippen.
