# Calendarsync instellingen voor Google Calendar API
Om Google calendars te synchroniseren is een google account nodig. Log in met deze account op https://cloud.google.com de Google Cloud Console voor ontwikkelaar.
Gebruik de link op de welkom pagina om een nieuw project te maken.

![](./media/google-console-welkom.png)

De lijst met projecten verschijnt, kiees hier "New project"

![](./media/google-project-list.png)

Geef het nieuwe project een naam `CallPro Agenda synchronisatie` zodat deze herkenbaar is.

![](./media/google-new-project.png)

Je komt terug op de welkom pagina waar nu het project is geselecteerd. Voeg nu de `Google Calendar API` toe door bij Quick Access te kiezen voor `APIs & Services`. Het is mogelijk dat de API al in de lijst met beschikbare api's staat, ander gebruikt de button `+ ENABLE APIS AND SERVICES` om deze toe te voegen. Ander klik op de API, en dan klik op het vervolg scherm op `CREDENTIALS`

![](./media/google-calendar-api.png)

Voeg een oAuth 2.0 CLient ID toe met de button `+ CREATE CREDENTIALS` en kies in de popup voor Oauth Client ID.
Kies bij Application type voro ` Desktop App` en geeft opnieuw een naam. 

Als dit de eerste keer is dan komt er een melding om eerst een Consent screen te configureren.
![](./media/google-consent-screen.png)

![](media/google-consent-screen-user-type.png)
![](media/google-consent-screen-app-info.png)
![](media/google-consent-screen-app-domain.png)
![](media/google-consent-screen-developer.png)

Druk op `SAVE AND CONTINUE`

Voeg nu de benodigde scopes toe, dit zijn de rechten die nodig zijn om afspraken te kunnen lezen en schreven in de Google Calendar.

![](media/google-consent-screen-scopes.png)

Gebruik de `ADD OR REMOVE SCOPES` knop om de volgende scopes toe te voegen.

![](media/google-consent-screen-scopes-needed.png)

Kies nu voor een Test App waarbij elke agenda die benaderd moet worden (tot maximaal 100) in de lijst met Test users moet worden opgegeven. 

![](media/google-consent-screen-test-users.png)

Of kies ervoor om de App te publishen nadat deze wizard is voltooid. 

![](media/google-app-production.png)

Hiervoor moetn wel dieverse extra acties worden voltooid en volgt een validatie door Google.

Nadat he tconsent screen is geconfigureerd keer terug naar de Credentials en kies opnieuw voor `+ CREATE CREDENTIALS` en kies `OAuth Client ID`

![](./media/google-create-oauth-credential.png)

Nu verschijnen de `Client ID` en `Client secret` die aan Calway gegeven moetne wordne voor installatie in de Calendar Sync Service. Op dit moment kan de gebruiker dit niet zelf doen!

![](./media/google-oauth-client-created.png)


# CallPro Agenda instelling
Voor elke agenda die gesynchroniseert moet worden stel de Synchronisatie methode in op `Google calendar` en vul het email adres in bij `Gebruikersnaam`. Laat het `wachtwoord` veld leeg. Het systeeem stuurt nu een email naar het opgegeven email adres waar deze gebruiker een link heeft die geklikt moet worden om de configuratie te voltooien.

![](media/ResourceExplorer-agenda-sync-settings.png)


![](./media/callpro-email.png)

Indien de klant op de link in die email klikt volgt een Google authenticatie en wordt een token teruggegeven die wordt bewaard in CallPro voor de synchronisatie.

De gebruiker die op de link klikt komt op een pagina die vervolgens de Google Login oproept.

![](media/google-connect-1.png)

Afhankelijk of er meerdere accounts zijn worden deze getoodn. Kies het account dat gesynchroniseert gaat worden met CallPro.

![](media/google-connect-2.png)

Afhankelijk of de App in productie is wordt een vervolg scherm getoond (dit is een Test App) Kies voor `Continue` 

Het is ook mogelijk als de gebruiker **niet** als Test user is opgevoerd dat deze melding komt.

![](media/google-connect-3.png)


![](media/google-connect-4.png)

Nu wordt gevraagd om de rechten die nodig zijn voor het synchoniseren van de Agenda. De klant moet hier `Select all` kiezen.



![](media/google-connect-6.png)

Nu is de Agenda synchronisatie correct ingesteld voor deze klant.