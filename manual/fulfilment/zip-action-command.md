### ZIP Action
```xml
<Action Type="ZIP">
    <Sourcefile>filename1</Sourcefile>
    <Sourcefile>filename2</Sourcefile>
    <Destinationfile Overwrite="YES|NO" Append="YES|NO">filename2</Destinationfile>
    <Password>wachtwoord(optioneel)</Password>
</Action>
```
Deze actie kan worden gebruikt om één of meerdere Sourcefiles te bundelen in één zip bestand. Optioneel kan het zipbestand van een wachtwoord worden voorzien. Alle sourcefiles worden dan met AES256 bits encryptie versleuteld. De actie is herhaalbaar wanneer append = true worden gebruikt. Er worden dan SourceFiles toegevoegd aan het zip bestand. Gebdruik dan wel telkens hetzelfde wachtwoord om problemen met het uitpakken te voorkomen. Overwrite = true maakt telkens een nieuw zipbestand.
