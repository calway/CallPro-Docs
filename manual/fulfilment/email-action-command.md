### Email action
```xml
<Action Type="eMail">
    <System>SMTP|Exchange|exchange_ews_basic_auth|m365_graph_api</System>
    <MailServer [Domain="maildomain"] [DefaultTimeOutSeconds="0"]
        [Username="username"]
        [Password="password"]
        [Userdomain="userdomain"] 
        [applicationid]="ApplicationId"
        [tenantid]= "tenantId"
        [clientsecret] = "clientSecret" >
        [smtpserver,only for SMTP mail actions]
    </MailServer>
    <ReadReceipt>YES|NO</ReadReceipt>
    <From Name="friendlyname">van</From>
    <Onbehalfof Name="friendlyname">van</Onbehalfof>
    <Recipient Type="TO|CC|BCC" Name="friendlyname">emailadres</Recipient>
    <Subject>onderwerpregel</Subject>
    <Header Name="headertag">van</Header>
    <Body Merge="YES|NO" InnerSource="BLOB|FILE"
        BodyType="HTML|PLAIN">emailbodytext</Body>
    <Attachment [cid="content-Id"] [type="FILE|TEXT|BLOB"]
        [OutputFile="attachmentfilename"] [Seperator="+" PathPrefix="path only">
        attachmentfile
    </Attachment>
</Action>
```
#### System en MailServer
Het mail system dat gebruikt kan worden voor het versturen van email.
Standaard worden de gegevens overgenomen van de globale MailServer instellingen uit de settings sectie. Wanneer de MailServer tag wordt opgenomen overschrijft dit de globale instellingen voor deze actie.

Voor informatie over het configureren van deze settings voor het versturen van email namens een extern (klant/opdrachtgever) domein zie: [Configuratie van een extern domein](./mailserver-external-domain-settings.md)

##### SMTP
Hiermee wordt de mail verstuurd via een smtp server. De `MailServer` tag die volgt geeft dan het server adres aan en in de parameters `Username`, `Password` voor het inloggen met basic authentication. Anonymous authentication kan gebruikt worden, maar wordt sterk afgeraden.
##### exchange_ews_basic_auth of Exchange
Dit is een Exchange webservice koppeling die gebruik maakt van basic authentication. De naam `Exchange` is behouden voor backward compatibility. Gebruik in de `MailServer` tag het server adres en in de parameters `Username`, `Password`, en optioneel `Userdomain` de naam van Active Directory.

> Vanaf 1-10-2022 kan dit **niet** meer gebruikt worden met Microsoft/Office 365 omdat Microsoft Basic Authentication vanaf die datum heeft uitgeschakelt. Sinds 2018 geeft Microsoft al aan dat de webservices obsolete zijn en niet verder worden doorontwikkeld. Het wordt geadviseerd om over te stappen op de Microsoft Graph API.
De exchange webservice koppeling kan nog steeds gebruikt worden voor on-premise Exchange servers of mail servers die compatible zijn met de Exchange WebServices.

##### m365_graph_api
Hierbij wordt gebruik gemaakt van de Microsoft Graph API. De `MailServer` tag heeft geen inhoud maar wel de parameters `applicationid`, `tenantid` en `clientsecret`. Maak in Azure Portal een App registration die deze gegevens oplevert. 
#### ReadReciept
Geeft aan of de verzender van de email een lees bevestiging wilt ontvangen.
#### From
Het From adres voor de email. Als parameter kan ook een `Name` worden opgegeven die als friendlyname wordt gebruikt.
#### OnbehalfOf
Indien gezet wordt dit gebruikt om een `onbehalf of` in te stellen. Ook bij deze tag kan een parameter `Name` worden gebruikt die als friendlyname wordt gebruikt. 
#### Recipient
De recipient tag mag vaker voorkomen binnen de email actie. 
Er dient minimaal 1 TO recipient te zijn. Meerdere recipients kunnen zowel in aparte recipient tags, als binnen een recipient tag als , of ; gescheiden lijst worden opgegeven. Bij de recipient kan ook een friendlyname worden meegegeven in de `Name` parameter.

#### Subject
De onderwerp regel van de email
#### Header
#### Body
De email body tekst
#### Attachment
De Attachment tag mag vaker voorkomen binnen de email actie. De attachment file mag ook een wildcard naam zijn in plaats van 1 specifieke filename.

De content-Id is optioneel bij een attachment, en zorgt ervoor dat een afbeelding in de mailbody wordt weergegeven wanneer daar een img tag staat met dezelfde content-Id Bijvoorbeeld: `<IMG SRC=cid:<content-id> />`

Voor attachment is File de default, dus de attachment moet een bestaande file zijn.
Wanneer blob of text worden gebruikt komt de inhoud van de attachment uit een database veld (collection). Alles ook mogelijk icm de Content-ID
De emailbodytext mag zowel een ascii tekst bestand zijn als een HTML bestand (Source=FILE) of een blob (Source=BLOB). Wanneer de optionele Merge tag NO is wordt dit bestand niet gemerged, de default hiervoor is echter YES.
