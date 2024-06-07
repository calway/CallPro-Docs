# Het configuratiebestand
Een fulfilmentservice configuratiebestand heeft een XML opmaak en ziet er als volgt uit:

```xml
<settings>
    <name>korte naam van de fulfilment</name>
    <description>Omschrijving van de fulfilment</description>
    <system>true | false</system>
    <schedule>
        <cron>
            <expression>* * * * *</expression>
            [...]
        </cron>
    </schedule>
    <errors>
        <email From="[from adres]">[email adres]</email>
    </errors>
    <regionalsettings>
        <language>nl-NL</language>
        <decimalseparator>.</decimalseparator>
        <thousandsseparator>,</thousandsseparator>
        <currencysymbol>€</currencysymbol>
    </regionalsettings>
    <cryptokey>[cryptokey]</cryptokey>
    <connectionstring>database connectionstring</connectionstring>
    <mailserver [Domain="maildomain"] 
        [DefaultTimeOutSeconds="300"]
        [Username="username"]
        [Password="password"]
        [Userdomain="userdomain"]
    >
        [smtpserver,only for SMTP mail actions]
    </mailserver>
    <loglevel>level</loglevel>
    <workingdirectory>c:\data\fulfilment\...</workingdirectory>
    <variables>
        <VariabeleName1>waarde1<VariabeleName1>
        <VariabeleName2>waarde2<VariabeleName2>
    </variables>
    <query>
        [Queries en actions]
    </query>
</settings>
```

## Algemene instellingen
Elke config heeft een `Name` die een korte identificatie geeft van de fulfilment. In de `Description` kan een langere uitleg worden gegeven van het process. Met `system` kan worden aangegeven dat deze filfilment niet kan worden verwijderd of gewijzigd.

## Schedule
Met deze optie kunnen taken gescheduled worden in de Fulfilment service i.p.v. handmatige executie.
Aan een config kunnen meerdere schedules worden toegevoegd.

```xml
<schedule>
    <cron>
        <expression>5,20,40,55 * * * *</expression>
    </cron>
</schedule>
```

Voor de exacte syntax van deze cron regels kijk op [Crontab Guru](https://crontab.guru) waar je eenvoudig een schedule kunt maken.

## Error mail notificatie
Een logfile wordt altijd aangemaakt. Deze logfile kan optioneel worden gemaild naar een email adres dat hier wordt ingesteld. De logfile wordt alleen verstuurd wanneer er logmeldingen zijn van het type error.
```xml
<Errors>
    <Email From="[from adres]">[email adres waar de log file naar to gemailt wordt]</Email>
</Errors>
```

> **DEPRECATED**: In versies van de mergetool voor 5.0.0 was de syntax anders. Bij migratie dient deze instelling aangepast te worden omdat de oude syntax bij de opvolgende versie **niet** meer ondersteunt wordt. De oude syntax was:

```xml
<ErrorsMailTo>[email adres waar de log file naar to gemailt wordt]</ErrorsMailTo>
```

## Regional settings

## CryptoKey
Deze optionele parameter kan worden gebruik om data te encrypten voor bijvoorbeeld vertrouwelijke oproepen naar de CallPro portal die in een email meegestuurd worden.
De cryptokey kan in iedere action overschreven worden door een actionbased
cryptokey. Deze wordt echter na de action weer gereset naar de default.

## Connectionstring
Dit is de database connectie naar de CallPro database. Deze tag is optioneel en hoeft alleen te worden ingevuld als een andere database dan de Callpro database gebruikt dient te worden. Een connectie string ziet er als volgt uit:

``` 
data source=<servername>;initial catalog=<databasename>;Application Name=CallPro Fulfilment; user id=<db-user>;password=<db-password>;persist security info=False;TrustServerCertificates=true
```
* `servername` is de naam van de sql server machine
* `databasename` is de naam van de database op de eerder genoemde server
* `db-user` is een geldige gebruiker op de server met toegang tot de database
* `db-password` is het password van de gebruiker

In deze connectie string kan optioneel een `querytimeout=30;` attribuut worden meegegeven (default waarde 30) die bepaald hoe lang een query mag duren vorodat deze is afgerond. Ook kan een connection timeout `connect timeout=60;` worden ingesteld die aangeeft hoe lang het verbinden met de database/server mag duren. Met name als gewerkt wordt met remote servers kan het nodig zijn deze waarden te verhogen. Voor lokaal gebruik zijn de defaults voldoende. 
> Let op: Wanneer de connectionstring naar een andere database wijst dan de CallPro database kan er geen gebruik worden gemaakt van resource acties.

> **DEPRECATED**: In versies van de mergetool voor 5.0.0 was de tag anders. Bij migratie dient deze instelling aangepast te worden omdat de oude syntax bij de opvolgende versie **niet** meer ondersteunt wordt. De oude syntax was:

```xml
<ConnectString>database connectionstring</ConnectString>
```

## MailServer
De mailserver tag is optioneel en hoeft alleen te worden gebruikt als een andere mailserver dan de standaard mailserver gebruikt dient te worden voor het versturen van mail in deze .config.

Voor SMTP servers staat de servernaam of ip-adres ingevuld als waarde. Voor Exchange zijn de attributen zoals domein, username etc verplicht. Indien er gebruik van SSL gemaakt moet worden geeft dan direct na de URL de ssl-poort op, bijvoorbeeld:
```
smtp.office365.com:587
```
Als de mailserver setting ontbreekt in de config wordt de setting uit de applicatie configuratie gebruikt.

## Loglevel
Loglevel bepaald hoeveel informatie de Mergetool naar een logbestand schrijft. Mogelijke loglevels zijn:
| LogLevel | Omschrijving |
| - | - |
| trace | Alles |
| debug | Alleen debuginfo en hoger |
| info, information | Alleen interessante informatie en hoger |
| warn,  warning | Alleen waarschuwingen en hoger |
| error | Alleen errors en hoger |
| fatal, critical | Alleen fatal errors |

Wanneer de loglevel in de config ontbreekt wordt de loglevel uit de applicatie configuratie gehaald.

Optioneel kan een ReferenceID worden meegegeven aan iedere logregel. Dit kan
worden aangezet door een expressie op te nemen als Tag attribuut, bijvoorbeeld:
```xml
<SQL Collection="SQL" ReferenceID="e:%SQL.ENTRYID%">
```
Dit zal een logregel opleveren waarbij de logmelding vooraf wordt gegaan door `e:<entryid>`

## Working directory

## Variables

## Querie of Loop
Na alle configuratie heeft elke config een `query` of `repeat` commando als de basis van alle executie. Binnen deze `root-node` kunnen meerdere `query` en `action` commando's worden gebruikt.