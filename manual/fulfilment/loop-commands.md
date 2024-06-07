## Queries en loops
Loop commando's itereren over een lijst met item. Het `Query` loop commando itereert over de records van de query die wordt uitgevoerd.

### Query loop
Een Query levert zoals gezegd een recordset op. Dit is een lijst met data uit de database. Deze data is te refereren door gebruik te maken van een collectie naam en de veldnamen. Een collectienaam wordt als attribuut meegeven aan de SQL tag (zie verder). Dit bepaald de naam van de recordset. Een collectie heeft daarna 1 of meer velden, ook wel kolommen genoemd. Deze zijn te refereren door de kolomnaam uit de query. Bijvoorbeeld:

```xml
<Query Condition="yes|no|expression">
    <SQL Collection="collectionname">select * from table</SQL>
    [one or more Actions; <Action>]
    [one or more Queries; <Query>]
</Query>

```
Bij een query kan een optionele vlag condition worden gezet (staat standaard op true). Wanneer deze vlag op **yes** staat dan wordt de query uitgevoerd, anders niet.

Binnen een query kunnen weer 1 of meerdere (sub)query’s worden gedefinieerd. Deze moeten voldoen aan dezelfde voorwaarden.

> Let op: Als een query geen resultaat oplevert bestaat de collectie niet!. Echter als de query op het zelfde niveau staat als vervolg acties of query’s worden deze wel uitgevoerd. Het resultaat van een query is altijd true, ook al levert het geen records op.

### Repeat loop
In plaats van een query kan ook een repeat blok worden gemaakt. Een repeatblok ziet er als volgt uit:
```xml
<Repeat>
    <Counter Collection="dummy">10</Counter>
    [one or more Actions; <Action>]
    [one or more Queries; <Query>]
</Repeat>
```
Binnen de repeat kunnen net als bij een Query actions worden gedefinieerd. Het voorbeeld blok zal alle geneste acties 10x uitvoeren. De variabele %dummy.recordnr% bevat het huidige iteratie nummer en is zero-based.
Naast een teller kan ook een opsomming worden meegeven die komma gescheiden is.
Bijvoorbeeld: `<Counter Collection="set">a,b,c,10</Counter>`
De volgende merge velden worden dan gemaakt:
%set.recordnr% en %set.value% met de waarden 0,"a" |1,"b" | 2,"c" en 3,"10"

### Excel loop
Een excel loop is vergelijkbaar met een Query loop. De data komt echter uit een excel sheet.
```xml
<Excel>
    <FileName Collection="excelrows" sheet="sheet1"></FileName>
    [one or more Actions; <Action>]
    [one or more Queries; <Query>]
</Excel>
```
Sheet bepaald de naam van de sheet met daarin de data.
