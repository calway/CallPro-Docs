### FTP Action
```xml
<Action Type="FTP">
    <Sourcepath recursive="true">c:\data\sample\output*</Sourcepath>
    <Sourcefiles>*.pdf</Sourcefiles>
    <Destinationpath>/upload/</Destinationpath>
    <Destinationfile>kopie.pdf</Destinationfile>
    <Protocol>FTP</Protocol>
    <Hostname>connect.calway.net</Hostname>
    <Username>callpro</Username>
    <Password>123</Password>
    <Passive>YES</Passive>
</Action>
```
Deze actie kan worden gebruikt om bestanden die met de mergetool zijn gegenereerd, maar ook andere bestanden te ftp’en naar een andere locatie. Als protocol kan gebruik worden gemaakt van ftp of sftp. Voor sftp is een optionele extra tag <fingerprint> nodig.
Zie http://winscp.net/eng/docs/faq_script_hostkey voor meer informatie over de
fingerprint. Passive is standaard false, met de Passive tag kan deze op YES worden gezet. Voor passive ftp in plaats van active. Secure ftp (TLS/SSL) wordt ondersteund door FTPS te gebruiken als Protocol.

| Tag | Omschrijving |
| - | - |
| Sourcepath | Optioneel. Dit is het pad waarin gezocht wordt naar bestanden die gekopieerd moeten worden. Er kan gebruik gemaakt worden van een wildcard. Standaard wordt er recursief gezocht, dus ook subfolders die aan de wildcard voldoen worden gebruikt voor de ftp. Zonder wildcard worden er niet gezocht, en is dit “slechts" een statisch pad. Vergeet niet af te sluiten met een \ omdat anders de laatste map de wildcard wordt! |
| Sourcefiles | Zonder wildcard resulteert dit in 1 file, met wildcard wordt gezocht naar voorkomens van bestanden die aan de wildcard voldoen. Sourcefile  mag een pad bevatten als er geen sourcepath meegegeven is! |
| Destinationpath | Rootfolder voor de ftp actie. GEEN wildcards! |
| Destinationfile | Optioneel, uitvoer bestandnaam, GEEN wildcards!. Kan alleen gebruikt worden wanneer er slechts een sourcefile is. De file wordt nml. telkens overschreven als er meerdere sourcefiles zijn. |
| Protocol | <ul><li>ftp (basic)</li><li>sftp, simple ftp. Fingerprint tag verplicht. De fingerprint krijg je bij de eerste ftp-poging. Neem deze dan op in de fingerprint tag.</li><li>ftps, secure ftp</li> |
