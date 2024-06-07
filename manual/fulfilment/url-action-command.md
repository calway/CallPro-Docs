### URL Action
```xml
<Action Type="URL" Collection="collectionname">
<URL>tagstring1</URL>
<optioneleparameters>waarde</optioneleparameters>
</Action>
```
De URL wordt opgeroepen, en het resultaat (html pagina) wordt in de collection opgenomen met de naam collectionname.DATA. Ook wordt een collectionname.STATUSCODE en collectionname.REASONPHRASE terug gegeven voor de Action. Optionele parameters worden geurlencode toegevoegd aan de URL voordat deze wordt opgeroepen.
