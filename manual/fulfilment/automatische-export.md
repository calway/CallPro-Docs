# Automatische export van belopdrachten
CallPro beschikt over een automatsiche export via de fulfilment module. Deze export wordt als volgt ingericht:

## Maak een exportdefinitie
Voor het exporteren is een een exportdefinitie nodig. Maak voor deze export een definitie met alleen de velden die gedeeld gaan worden met de opdrachtgever. Meestal wil je hier de **status**, **status datum** en een subset van de scriptvelden opnemen.

Vervolgens koppel een exportfilter die bepaald welke belopdrachten worden geexporteert. Zonder filter worden elke keer *alle* belopdrachten uit de bellijst(en) geexporteerd. 
Het is beter om bijvoorbeeld een filter te gebruiken die alleen de gewijzigde belopdrachten exporteert. De periode kan worden afgestemd op de periodiciteit van de batch, ie. `DAILY`, `WEEKLY` of `MONTHLY`. Optioneel kan ook nog extra worden gefiltert door bijvoorbeeld alleen bepaalde statussen in de export op te nemen. Denk hierbij aan een filter die alleen de **Afspraak** of **Informatie sturen** statussen exporteert.

## Automatische export per campagne
Om automatisch periodiek de belopdrachten Door op de campagne folder naar het tabblad variabelen te gaan 
* Stel de variable `EXPORT.AUTO` in op de waarde `DAILY`, `WEEKLY` of `MONTHLY`
* Refereer met `EXPORT.EXPORTID` naar de unieke Id van de export definitie die gebruikt moet worden voor de export.
* Vul bij `EXPORT.TO` het email adres in van de ontvanger van het export bestand.
* Maak een variabele `EXPORT.BODY` met de email template die wordt gebruikt voor de email.
* Als er geen variabele `EXPORT.SUBJECT` is gedefinieerd dan wordt het onderwerp van de email '[\<naam exportdefinitie\>] Excel export voor \<datum van de export\>'. 
* Optioneel kan ook een `EXPORT.CC` en `EXPORT.BCC` worden gebruikt.
* Optioneel kan een alternatief from adres owrden opgegeven met `EXPORT.FROM` maar dit moet wel binnen het eigen email-domein vallen.
