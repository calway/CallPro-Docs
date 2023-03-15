## XML kennis
De Mergetool wordt bestuurd door een configuratiebestand met een XML structuur. Dit standaard fileformaat gebruiken wij een geformaliseerde configuratie af te dwingen.

De basis voor XML zijn tags en waarden, bijvoorbeeld:
```xml
<Naam>Ron</Naam>
```
Hierin is `<Naam>` de starttag, en `</Naam>` de eind-tag. Daartussen is dan de waarde te vinden, in dit geval Ron. Tags in de Mergtool zijn **niet**  hoofdlettergevoelig.

XML bestaat uit een geneste structuur. Dit houdt in dat Tags genest zijn binnen andere Tags. Bijvoorbeeld:
```xml
<Persoon>
<Voornaam>Ron</Voornaam>
<Achternaam>Heller</Achternaam>
</Persoon>
```
Naast Tags en waarden zijn er nog **attributen**. Deze zeggen al iets over de waarde. Bijvoorbeeld:
```xml
<Persoon geslacht="Man">
<Voornaam>Ron</Voornaam>
<Achternaam>Heller</Achternaam>
</Persoon>
```
Hierin is `geslacht` het attribuut met de waarde Man. 

Met deze basis kennis van XML kunnen MergeTool configfiles gemaakt en bewerkt worden qua structuur. Verderop in deze handleiding worden de tags en attributen besproken die de Mergetool gebruikt.

## SQL Kennis
SQL (Structured Query Language) is een programmeertaal om tegen een database te praten. Meestal bedoeld om informatie op te vragen uit de database, maar ook om wijzigingen aan te brengen in de database.

Belangrijk voor de Mergetool is het opvragen van informatie uit de database. Hiervoor bestaat het sql-statement SELECT

Deze werkt als volgt:
```
SELECT kolommen FROM tabel WHERE filter
```
Dus: KIES kolommen UIT TABEL tabel DIE VOLDOEN AAN filter

Bijvoorbeeld:
```
SELECT name_first, name_last FROM callpro._r1212 WHERE name_gender = ‘Male’
```
Dit zal een lijst opleveren met voor- en achternamen van alle mannen uit de tabel met naam `callpro._r1212`, (een bellijst).

Belangrijk is te weten welke kolommen je beschikbaar hebt in een tabel, en welke je nodig hebt. Daarnaast moet je enige kennis hebben van het CallPro datamodel om de juiste query’s te formuleren.
SQL kennis is breed te vinden op internet met veel voorbeelden en uitleg. In deze handleiding gaan we niet verder in op SQL kennis, maar verwijzen we naar andere documentatie.

## CallPro Datamodel
Het CallPro datamodel is niet erg moeilijk te begrijpen. Voor de mergetool zijn een aantal dingen belangrijk. Dit zijn gegevens die vaak zullen worden opgevraagd. We gaan daarom kort in op deze gegevens, en laten de rest van het datamodel buiten beschouwing in deze handleiding.
Alles in CallPro heet Resource. Een bellijst is een resource, een agent is een resource, maar ook een agenda is een resource. Alle definities van Resources staan in de tabel met de naam ResDefs. Belangrijke kolommen zijn dan:
| kolom | Omschrijving |
| - | - |
| ResID | Dit is een unieke numerieke identificatie van de resource, een getal tussen 0 en 2 miljard. |
| Name | Dit is de (korte) naam van de resource |
| ResType | Dit is het type van de resource, dus agent, bellijst of agenda. |

Een bellijst heeft naast een definitie ook inhoud. Deze is te vinden in twee tabellen, namelijk `CLENTRIES` en `_R<ResID>`. Samen vormen deze de inhoud van de bellijst. Hierin staan alle systeem kolommen in de tabel `CLENTRIES`, en alle gebruikerskolommen in de tabel `_R<ResID>`
Op basis van de kolom CLENTRYID zijn de gegevens uit beide tabellen bij elkaar te vinden omdat de CLENTRYID een unieke waarde is voor een belopdracht of adres.
Bijvoorbeeld:
```
SELECT script.*, entry.telnr 
FROM callpro._R212 script 
INNER JOIN clentries entry ON script.clentryid = entry.cleentryid 
WHERE script.name_gender = `Male`
```
Deze query levert alle kolommen uit bellijst 212 gefilter op “mannen“ aangevuld met het telefoonnummer.
