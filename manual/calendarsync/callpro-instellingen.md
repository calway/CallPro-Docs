# CallPro CalendarSync instellingen
Bij de Agenda in CallPro kunnen de volgende instellingen worden gezet die de synchronisatie van afspraken beinvloeden. Deze instellingen worden gedaan door variabelen in CallPro op de Agenda toe te voegen met de volgende namen.

## calendarsync.Subject
Dit is de onderwerp regel van de afspraak die in de externe agenda wordt gezet. Hier kan een vaste waarde worden gebruikt, maar ook zijn diverse fulfilment velden beschikbaar. Gebruik hiervoor een variabele van het type `Karakter`. In de meeste gevallen wordt in de subject regel gebruik gemaakt van gegevens van de belodpracht.
>Bijvoorbeeld: "Dakmeting bij `%SCRIPT.COMP_NAME%` voor CalwaySolar panelen".

## calendarsync.Location
Dit is de location regel van de afspraak die in de externe agenda wordt gezet. Hier kan een vaste waarde worden gebruikt, maar ook zijn diverse fulfilment velden beschikbaar. Gebruik hiervoor een variabele van het type `Karakter`. Hier wordt meestal gebruik gemaakt van de adresgegevens.
>Bijvoorbeeld: `%SCRIPT.ADDR_STREET% %SCRIPT.ADDR_NUMBER%%SCRIPT.ADDR_NUMBEREX%  %SCRIPT.ADDR_ZIP% %SCRIPT.ADDR_CITY%`

## calendarsync.Body
Dit is de body tekst van de afsrpaak die in de externe agenda wordt gezet. Gebruik hiervoor een variable van het type `memo` zodat een complete email template kan worden ingevoegd. Het wordt aangeraden om hiervoor een html template te gebruiken.

## calendarsync.IsOnlineMeeting
> **Deze instellingen werken alleen bij gebruik van de Microsoft 365 Graph API koppeling voor de synchronisatie met de Microsoft 365 Tenant.**

Hiermee kan worden aangegeven dat het om een online (Teams) vergadering gaat. Exchange voegt dan automatisch ene Teams link toe in de body. Als dit voor alle afspraken geldt die gemaakt worden dan kan hde variabel van het type `Boolean` en kan de waarde aangevinkt (TRUE) of niet (FALSE) zijn om aan te geven dat het resp. een Online vergadering is of niet.
Het is ook mogelijk om een variabele van het type 'Karakter' te gebruiken zodat een fulfilment expressie kan worden gebruikt die op basis van een scriptveld dynamisch bepaald of het een Online vergadering moet worden of niet. Stel er is een scriptveld `AFSPRAAK_TYPE` is die de mogelijke waarden `ONLINE`, `OPLOCATIE`, `ONSKANTOOR` kan hebben.
>Bijvoorbeeld `%SCRIPT.AFSPRAAK_TYPE \IF"ONLINE"?TRUE:FALSE%` 


## calendarsync.RequiredAttendees
> **Deze instellingen werken alleen bij gebruik van de Microsoft 365 Graph API koppeling voor de synchronisatie met de Microsoft 365 Tenant.**

Dit is de persoon (zijn de personen) die nodig zijn voor deze afsrpaak. Meestal is dit de persoon die ook gebeld is. Het kan ook zijn dat er meerdere personen nodig zijn, die kunnen dan als , of ; gescheiden lijst van personen worden meegegeven. Deze lijst is vrijwel altijd uniek per belodpracht. Gebruik een variabele van het type `Karakter`. De verwijzing is vrijwel altijd naar een scriptveld van de belopdracht. Stel er is een scriptveld `NAME_EMAIL` die het email adres bevat van de persoon die we hebben gebeld.
>Bijvoorbeeld: `%SCRIPT.NAME_EMAIL%` 

Deze mensen krijgen een Exchange uitnodiging per email. Hou er rekening mee dat de ontvanger de uitnodiging kan weigeren, dit gaat wel terug naar de Agenda, maar wordt niet verwerkt in CallPro.

## calendarsync.OptionalAttendees
> **Deze instellingen werken alleen bij gebruik van de Microsoft 365 Graph API koppeling voor de synchronisatie met de Microsoft 365 Tenant.**

Dit is de persoon (zijn de personen) die optioneel aanwezig zullen zijn voor deze afsrpaak. Het kan ook zijn dat er meerdere personen worden uitgenodigd, die worden dan als , of ; gescheiden lijst van personen meegegeven. Deze lijst is vrijwel altijd uniek per belopdracht. Gebruik een variabele van het type `Karakter`. De verwijzing is vrijwel altijd naar een scriptveld van de belopdracht. Stel er is een scriptveld `NAME_EMAIL` die het email adres bevat van de persoon die we hebben gebeld.
>Bijvoorbeeld: `%SCRIPT.NAME_EMAIL%`

Deze mensen krijgen een Exchange uitnodiging per email. Hou er rekening mee dat de ontvanger de uitnodiging kan weigeren, dit gaat wel terug naar de Agenda, maar wordt niet verwerkt in CallPro.