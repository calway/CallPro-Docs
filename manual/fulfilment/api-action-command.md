### API Action
De API action is niet direct bedoeld voor fulfilment, maar wordt gebruikt als configuratie voor een query-engine. Een API action moet in een config staan met schedule type API. De config kan alleen worden gestart middels een API call naar de Fulfilment service, en levert uitvoer als json bericht.
Voorbeeld van een API script dat actieve gebruikers oplevert.
```xml
<settings>
    <name>Agentlist</name>
    <description>CallPro Agentlist</description>
    <schedule Type="API"></schedule>
    <query>
        <SQL Collection="agent">
select
TOP %VARIABLE.TOP \SW""?"5"%
  resdefs.resid
, resdefs.name
, resdefs.account
, agent.firstname
, agent.lastname
, agent.address
, agent.email
, resdefs.createddtm as Since
, resdefs.enabled as Active
from AgentDefs agent 
join resdefs on agent.ResID=resdefs.ResID 
where resdefs.resid >= 0
        </SQL>
        <action Type="API">
            <Column Name="resid">%agent.resid%</Column>
            <Column Name="name">%agent.name%</Column>
            <Column Name="account">%agent.account%</Column>
            <Column Name="firstname">%agent.firstname%</Column>
            <Column Name="lastname">%agent.lastname%</Column>
            <Column Name="address">%agent.address%</Column>
            <Column Name="email">%agent.email%</Column>
            <Column Name="since">%agent.since%</Column>
            <Column Name="active">%agent.active%</Column>
        </action>
    </query>
</settings>
```

Deze api kan worden opgeroepen met een Api POST call naar `https://fulfilmentservice.subdomain.callpro.nl/api/Query` met een json payload:

```json
{
    "queryName": "Agentlist",
    "parameters": {
        "top": "10",
    },
    "forceRefesh": true,
    "cacheSeconds": 0
}
```
In de aanroep wordt via `queryName` de naam van deze API opgegeven, in `parameter` kunnen (optioneel) parameters worden meegegeven die als variabelen binnenkomen. `forceRefresh` kan optioneel worden gebruikt om de cache te omzeilen, en `cacheSeconds` geeft aan hoe lang een vorige call, met dezelfde parameters, zal worden gecached, standaard 1800 seconden (30 minuten).
