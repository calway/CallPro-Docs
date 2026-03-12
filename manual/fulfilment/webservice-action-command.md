### Webservice Action
De webservice action is een generieke methode om webservices aan te roepen, en resultaten terug te ontvangen. De syntaxt is:
```xml 
<Action type="webservice" collection="collectie-naam">
    <library>webservice-naam</library>
    <url>base Url voor de webservice</url>
    <method type="GET | POST | PUT | PATCH | DELETE">url fragment met querystring</method>
    <authorization>url | basic auth</authorization>
    <username></username>
    <password></password>
    <header name="Authorization">bearer %variable.token%</header>
    <query_parameternaamn>querystring parameter waarde</query_parameternaam>
    <result fieldName="veldnaam1 in de collectie">json veld of xml path om de waarde op te halen uit de response</result>
    <result fieldName="veldnaam2 in de collectie">...</result>
</Action>
```
In de `collection` attribuut geef je de naam van de collectie die wordt gebruikt voor resultaat velden. `library` is een weergave label. In `url` wordt de base url van de webservice gezet. Dit is soms alleen de DNS naam, maar dit mag ook een stu kvan de endpoint url bevatten.

Met de `<method>` tag wordt aangegeven wat voor api call wordt gedaan. Meestal wordt **GET** of **POST** gebruikt. In de tag wordt een url frgament van he tendpoint geplaatst zonder de BaseUrl. Indien er paramaters zijn, zowel route als querystring parameters kunnen die hier direct in de url-fragment worden gezet.

De `<authorization>`, `<username>` en `<password>` tags zijn deprecated. Gebruik de **basic auth** optie om een username en password autorisatie uit te voeren.  Met de **url** optie wordt de username en password aan de querystring parameters toegevoegd. Dit laatste kan ook door deze gegevens direct in de url-fragment van de `<method>` tag toe te voegen. Gebruik bij voorkeur de `authorization` header met de juiste waardes. 

Ook de `<query_parameternaam>` tags zijn deprecated. Plaats deze direct in de `<method>` tag url-fragment. De `<result>` 


In dit voorbeeld sturen we een request naar AddressPro:
```xml 
<Action type="webservice" collection="address">
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
<Action type="webservice" collection="teams" condition="false">
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
