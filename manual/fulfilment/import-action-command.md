### Import Action
Deze actie importeert een bestand (Excel) naar een bellijst in CallPro op dezelfde manier als in CallPro.
```xml
<Action Type="Import">
    <CallListID>id</CallListID>
    <ImportID>id</ImportID>
    <Filter>filterconditie(sql)</Filter>
    <InputFile Type="Excel"
        sheet="sheetname">filename</InputFile>
</Action>
```
Deze actie importeert de file `filename` vanuit een Excel of tekstbestand. Voor Excel is `sheet` optioneel, standaard wordt de eerste sheet gebruikt.
