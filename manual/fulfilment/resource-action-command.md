### Resource Action
```xml
<Action Type="Resource" Collection="collectionname"
    Report="True|False">
    <ResourceType>EXPORTDEF|ENTRY|…</ResourceType>
    <ResourceID>id</ResourceID>
</Action>
```
Dit actie werkt alleen i.c.m. CallPro, en zal een CallPro resource type proberen te laden.
De ResourceID is verplicht, evenals een geldig ResourceType. De volgende
Resourcetypen worden ondersteund:

| ResourceType | |
| - | - |
| ENTRY | Extra: Alle scriptvelden zijn dan beschikbaar via de collectie |
| EXPORTDEF | Extra: EXTERNAL, INTERNAL en TEMPLATE zijn beschikbaar External is een gescheiden lijst met de externe veldnamen. Internal is een gescheiden lijst met de interne veldnamen Template is een gescheiden lijst met interne veldnamen inclusief de collecties (CALLIST of CLENTRIES) Filter expressie voor de export
| CALLLIST ||
| CALENDAR ||
| APPOINTMENT ||
| SCRIPTDEF ||
| CAMPAIGN ||

Naast enkele extra velden zijn alle standaard properties en resvariables beschikbaar van het resourcetype.
