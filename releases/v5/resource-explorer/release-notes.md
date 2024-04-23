# Resource Explorer Releases
Dit zijn de Release Notes voor de Resource Explorer. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

## v5.0.10 - 2024-04-23
### Fix
- Bij het kopieren van scriptvelden tussen verschillende scriptdefinities werden bestaande bellisjten die zijn gebaseerd op de scriptdefinitie die het nieuwe veld ontving **niet** bijgewerkt. Het probleem treedt alleen op bij het kopieren van velden tussen verschillende scriptdefintiies via het clipboard!

### Change
- **v5.0 database only**: Op de seat kan worden aangegeven dat de auto-provisioning wel/niet moet worden uitgevoerd. Voor deze update erd altijd auto-provisioning gebruikt, en werd Microsip vervolgens automatisch opgestart. 
- **v5.0 database only**: Op de seat kan nu worden aangegeven dat bij het afsluiten van de Scriptmodule ook Microsip wordt afgesloten. Deze optie is alleen zichtbaar voor CallPro installaties die **database versie 5** hebben, en werkt ook alleen icm een Scriptmodule v5.0.10


***
## v5.0.9 - 2024-02-28
### Fix
- Bij het bewerken van variabelen van type Memo (er wordt dan een RichtEditbox gebruikt) gaat er iets fout als tekst wordt ingevoerd die foutief herkend wordt als hyperlink. Deze hyperlink detectie gaat de eerste keer goed, maar eenmaal herkende hyperlinks (die geen hyperlink zijn) worden soms verkeerd omgezet in platte tekst wat resultaat in `< >` om de hyperlink. Dit trad op in javascript code in de variabele die hierdoor niet meer correct werkte.
- Bij het exporteren van bellijsten naar Excel op een Onedrive locatie volgde soms ene foutmelding tijdens het exporteren doordat Onedrive het upload en CallPro geen exclusieve toegang kan krijgen. De melding is vervangen door een Herhaal optie zodat het openen van het exportbestand herhaald kan worden, wat meestal direct werkt, tenzij het uploaden naar Onedrive heel traag gaat, maar dan kan het meerdere keren geprobeert worden totdat het lukt. Een alternatieve optie is om de Onedrive synchronisatie tijdelijk te pauzeren.


***
## v5.0.8 - 2023-12-06
### Fix
- In de rapportage werd bij het gebruik van de "Export naar Excel" optie cijfer kolommen niet gezien als cijfers, maar als tekst. Dit is opgelost. Een resterend probleem is dat tijdsduur kolommen nog steeds als tekst worden gezien en in Excel niet worden herkend als een tijdsduur. Als je de cell bewerkt herkend Excel de *handmatige* invoer wel als tijdsduur. We hebben hier nog geen oplossing voor kunenn vinden anders dan dat je als gebruiker `F2` en `Enter` moet uitvoeren op de cell.

### Change
- Cosmetische verbeteringen in keuzelijsten met checkbox selectie.
- Er is een sneltoets toegevoegd `Ctrl-Shift+C` om het volledige pad van de huidige resource in het clipboard te zetten.


***
## v5.0.7 - 2023-10-18
### Fixed
- In de standaard zoekvelden was per abuis het filteren met `%` verwijderd waardoor er niet meer kon worden gezocht op bijvoorbeeld bedrijfsnaam bevat "bakker" door in het bedrijfsnaamveld "%bakker" te gebruiken. Voor alle duidelijkheid, met `%` geef je aan dat het niet uit maakt wat er voor staat, maar dat ergens "bakker" in de bedrijfsnaam moet staan. CallPro voegt standaard al een `%` achter de gebruiker-invoer toe (zodat je altijd zoekt op een `begint met`)

    Daarnaast kan ook een `_` worden gebruik om aan te geven dat hier elk willekeurig karakter kan staan of `[]` met tussen deze haken een 1- of meer tekens zoals `9[5678]` om aan te geven dat gezocht moet worden op postcodes die beginnen met "95, 96, 97 of 98". Deze reeks kan nog eenvoudiger als `9[5-8]` worden geschreven.


***
## v5.0.6 - 2023-10-17
### Fixed
- Extra applicatie icoon in Start menu voor Campagne Grid en Suppressielijsten import.

### Change
- In de Agendamodule is een calendar maand control toegevoegd voor snellere navigatie door de agenda.

***
## v5.0.5 - 2023-07-18
### Changed
- De icons in de toolbar zijn nu uniform van afmeting. Dit ziet er een stuk beter uit

### Fixed
- In de terugbeltijd expressie berekening die gebruikt wordt voor de status datum berekening, specifiek voor TimeAdd, konden door een fout geen minuten meer gebruikt worden. De syntax `TimeAdd=5m` (5 minuten) werd niet herkend als geldig, maar `TimeAdd=1h` (1 uur) nog steeds wel. Dit was een feature regressie bug die snel kon worden opgelost.

***
## v5.0.4 - 2023-07-17
In deze versie is een begin gemaakt met de mogelijkheid om meerdere eigenschappen vensters tegelijkertijd open te kunnen hebben, veel CallPro vensters zijn "modal" wat betekent dat als dit venster open is, geen enkel ander programma venster kan worden gebruikt tot dit venster is gesloten. Voor diverse gebruik scenario's is het handig als je meerdere vensters naast elkaar open kunt hebben, en kunt gebruiken.

***
## v5.0.3 - 2023-03-01
Gebruikers op Windows 10 hadden veel problemen met automatische updates en installatie. Deze versie werkt alleen met het nieuwe developer certificaat en op zowel Windows 10 als Windows 11. Verwijder eerst voorgaande versies en installeer dan deze nieuwe versie.

***
## v5.0.2 - 2023-02-01
Door het verlopen van het developer certificaat werkten automatische updates niet meer. Deze versie gebruikt het nieuwe certificaat en ondersteunt op Windows 11 ook upgrade van het oude certificaat.

***
## v5.0.1 - 2022-02-01
Dit is de eerste officiele versie van deze client. Met deze versie gebruiken we https://installer.callpro.nl voor de installatie (voor Windows 10/11)


***
## v5.0.0 - unreleased
