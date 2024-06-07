### SQL Action
```xml
<Action Type="SQL">
    <SQL>querystring</SQL>
    <ConnectionString>connectionstring</ConnectionString>
</Action>
```
Deze actie kan bijvoorbeeld gebruikt worden om update en/of insert queries uit te voeren. De ConnectionString is optioneel, en kan wijzen naar een andere ODBC
databron. Als ConnectionString niet is vermeld wordt de standaard connectie
gebruikt.
