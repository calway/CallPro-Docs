## Acties
Een `actie` is een onderdeel van een `query`, en zal voor ieder record uit de query loop worden uitgevoerd. Als voor een record een actie niet uitgevoerd kan worden omdat bijvoorbeeld een template niet bestaat dan worden alle volgende acties overgeslagen voor dit record, en springt het programma door naar het volgende record uit de recordset van de bovenliggende (omvattende query). Er zijn verschillende soorten acties:

```xml
<action Type="Merge | Email | SQL | Pdf | Tag | FileCopy | Webservice | FTP | Resource | Set | SMS">
    ...
</action>
```

De verschillende soorten actie tags worden in de komende paragrafen verder behandeld. 

### Action hierarchie
Het resultaat van een actie gaat mee naar een vervolg actie als deze binnen dezelfde loop/query zit (zelfde niveau). In dit voorbeeld heeft Actie A geen effect op Actie B of C.
```xml
<Query>
    <SQL></SQL>
    <Query>
        <SQL></SQL>
        <Action A>
        </Action A>
    </Query>
    <Query>
        <SQL></SQL>
        <Action B>
        </Action B>
    </Query>
</Query>
<Action C>
</Action C>

```

### OnSuccess en OnFailure
Met een `OnSuccess` en `OnFailure` tag kunnen vervolg acties conditioneel worden uitgevoerd. Als de omvattende actie met success is uitgevoerd, dan worden de acties binnen de `OnSuccess` tag uitgevoerd. Als de omvattende actie een fout oplevert, dan worden de `OnFailure` acties uitgevoerd. Op deze manier kan zowel conditionele acties worden ingericht, als ook foutafhandeling.
> **DEPRECATED** In versies van de mergetool voor 5.0.0 was de tag OnSuccesful maar deze wordt vanaf 5.0.0 vervangen door OnSuccess. Bij migratie dient deze instelling aangepast te worden omdat de oude syntax bij de opvolgende versie **niet** meer ondersteunt wordt.

Wat je ook kan doen als je bepaalde acties wilt laten afhangen van het resultaat van de buitenste is dit:
```xml
<Query>
<SQL></SQL>
    <Query>
        <SQL></SQL>
    </Query>
    <Query>
        <SQL></SQL>
    </Query>
    <Action A>
        <OnSuccess>
            <Action C>
            </Action C>
        </OnSuccess>
    </Action A>
    <Action B>
        <OnSuccess>
            <Action C>
            </Action C>
        </OnSuccess>
        <OnFailure>
            <Action D>
            </Action D>
        </OnFailure>
    </Action B>
</Query>
```
Bij een `OnFailure` worden er een tweetal tags toegevoegd aan de mergefield collection:
DEBUG.ACTION en DEBUG.LASTERROR

Als gebruik wordt gemaakt van `OnFailure` dan geldt niet meer het standaard gedrag dat opvolgende acties **niet** meer worden uitgevoerd als de huidige actie een error geeft. Nadat een `OnFailure` is uitgevoerd vervolgd de uitvoer met de volgende actie alsof er geen fout is opgetreden. Dit beinvloed dus wel de controlflow.

### Conditional attribuut
Dat wil zeggen dat een actie alleen wordt uitgevoerd als aan een bepaalde voorwaarde (condition) wordt voldaan.
```xml
<Action Type="eMail" Condition="%VARIABLE.TESTVALUE% = 1">

</Action>
```

In dit voorbeeld wordt de eMail actie alleen uitgevoerd wanneer VARIABLE.TESTVALUE evalueert naar 1. In de condition kan gebruikt worden gemaakt van de volgende operators: =, <>, <, >, <=, >= en ><. De variabelen worden geanalyseerd en geëvalueerd op types: string, integer, decimaal of datum.
De laatste operator >< werkt al een “in" statement, bijvoorbeeld:
3 >< (1,2,3,4,5) zal true opleveren.



Voor string waarden is het verstandig om '' om de waarde te plaatsen. Zo test de onderstaande conditie dat het `NAME_EMAIL` scriptveld gevuld is.
```xml
<Action Type="eMail" Condition="'%SCRIPT.NAME_EMAIL%' > ''">

</Action>
```

### Cryptokey attribuut
In de header van iedere action kan een optionele cryptokey worden meegegeven. Deze wordt gebruikt in de `\xx` switch om een mergestring te encrypten. De crytpo key die zo wordt ingesteld geldt alleen voor alle acties en queries binnen deze action. Bijvoorbeeld:
```xml
<Action Type="eMail" cryptokey="%VARIABLE.CRYPTOKEY%">
…
</Action>
```
