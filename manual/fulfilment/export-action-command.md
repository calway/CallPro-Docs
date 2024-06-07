### Export Action
```xml
<Action Type="Export">
    <CallListID>id</CallListID>
    <ExportID>id</ExportID>
    <Filter>filterconditie(sql)</Filter>
    <OutputFile Type="Excel|Text"
        Sheet="sheetname">filename</OutputFile>
</Action>
```
Deze actie maakt een export zoals CallPro dat ook doet. De keuze is een export naar excel of naar een text bestand. Voor exports naar Excel moet de filename extensie ".xlsx" zijn!
