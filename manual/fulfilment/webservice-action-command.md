### Webservice Action
De webservice action is een generieke methode om webservices aan te roepen, en resultaten terug te ontvangen. Bijvoorbeeld:
```xml 
<Action Type="webservice" Collection="address">
    <library>addresspro</library>
    <url>https://addresspro.net</url>
    <authorization>url | basic auth</authorization>
    <username></username>
    <password></password>
    <header name="Authorization">apikey %Variable.AddressProToken%</header>
    <method type="GET">api/Address/GetAddressRecord</method>
    <postcode>9727DL</postcode>
    <huisnummer>15E</huisnummer>
    <result fieldName="addr_city">data[0].woonplaats</result>
    <result fieldName="addr_street">data[0].straat</result>
</Action>
```
Dit is een voorbeeld van een webservice die op basis van een postcode en huisnummer de straat en woonplaats oplevert. Het resultaat komt in de mergecollection terecht met de namen ADDRESS.ADDR_CITY en ADDRESS.ADDR_STREET

Voorbeeld Microsoft Teams:
```xml
<Action Type="webservice" Collection="teams" Condition="false">
    <library>teams</library>
    <url>https://outlook.office.com/webhook/zzzzzz-yyyy-43a1-xxxxggggggggggggggggg-a95d-4eb3-8eb9-9f84226449ec/</url>
    <method type="POST">IncomingWebhook/xxxxxxxxxxxxxxf/85bbbbb-5aaaa-41ce8a52-b437f5f50a44</method>
    <header name="contenttype">application/json</header>
    <header name="accept">application/json</header>
    <payload>
    {"title": "Fulfilment %SYS.DATE%", "text" : "some text to
        post", "themeColor": "EA4300"}
    </payload>
</Action>
```
Bovenstaande webservice call zou een nieuwe post plaats in een Teams channel.
