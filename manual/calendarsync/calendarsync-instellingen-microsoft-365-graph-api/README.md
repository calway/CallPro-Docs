# Calendarsync instellingen Office 365 Graph API

Om gebruik te maken van nieuwe mogelijkheden zoals Online Teams meetings maken moet gebruik worden gemaakt van een Microsoft Graph API. De CallPro CalendarSync module heeft ondersteuning voor deze manier van werken met Microsoft 365. Volg de onderstaande stappen om een App registratie te maken die kan worden gebruikt met de CallPro.


## Registreer een applicatie in Microsoft Entra ID (voorheen AzureAd)
De klant moet in zijn/haar Microsoft 365 omgeving in Azure Active Directory een applicatie aanmaken voor de Agenda synchronisatie.

1. Ga naar de Entra portaal (entra.microsoft.com) en log in met een administrator account die Applicatie registraties kan aanmaken.

1. Selecteer **Beheren** en dan de sub-optie **App-registraties**

1. Selecteer **Nieuwe registratie**, en vul de volgende waarden in:

    * Vul bij **Naam** als waarde: `CallPro CalendarSync`
    * Vul bij **Ondersteunde accounttypen** een waarde die voor dit bedrijf acceptabel is. Vaak is de `Alleen een tenant - NAAM-VAN-DE-TENANT` optie voldoende.
    * Vul bij **Omleidings-URI (optioneel)** als platform `Openbare client/systeemeigen (mobiel en desktop)`
    * Vul in het veld erachter adres de waarde: `https://login.microsoftonline.com/common/oauth2/nativeclient`

1. Kies **Registreren** om de Applicatie te maken. 
1. Ga nu in de app registratie naar **Certificaten en geheimen**
    * Druk hier op **Nieuw clientgeheim**
    * Geef als beschrijving iets herkenbaars, zoals de naam van het call center, en de huidige datum, ie. `callpro-2025-02-10`
    * Kies bij **Verloop op** de langst mogelijke periode, op dit moment is dat 24 maanden.
    * Vergeet geen herinnering in je agenda te zetten om na 23 maanden een nieuwe secret te maken en die aan het call center door te geven anders stop de synchronisatie na 24 maanden!
    * Vergeet niet om de client secret (de code zichtbaar in de **Waarde** kolom) te kopieren en vast te leggen, dit wordt eenmalig afgebeeld!

## Configureer API-machtigingen
Vervolg nu de volgende stappen om de registratie af te ronden.


* Ga naar **API-machtigingen** in de **Beheren** sectie van het navigatie menu.
* Druk op **Een machtiging toevoegen**, kies dan `Microsoft Graph` en daarna in het volgende scherm, `Toepassingsmachtigingen`
* Vul in het zoekvenster `calendar` in om te zoeken, selecteer de machtiging `Calendars.ReadWrite` om toegang tot de calendars te geven.
* Zoek dan naar `mailbox`, selecteer `MailboxSettings.Read`
* Indien via de Graph API ook emails gestuurd gaan worden zoek dan naar `Mail.Send` en selecteer die machtiging `Mail.Send`.
* Kies **Machtigingen toevoegen** om alle gekozen machtigingen toe te voegen, je komt nu terug in het vorige scherm en ziet de machtigingen die je zojuist hebt gekozen.
* Er is nog 1 machtiging nodig. Kies nu nogmaals voor **Een machtiging toevoegen**, kies dan `Microsoft Graph` en daarna in het volgende scherm, `Gedelegeerde machtigingen`
* Zoek nu naar `User.Read`, en selecteer deze machtiging `User.Read`
* Kies **Machtigingen toevoegen** om deze machtiging toe te voegen, je komt nu terug in het vorige scherm en ziet nu alle tot nu toe toegevoegde machtigingen.
* Selecteer nu **Beheerderstoestemming verlenen voor NAAM-VAN-DE-TENANT** en accepteer de consent dialoog. Dit kun je alleen doen als je een administrator bent!

##### Enterprise restricties (optioneel)
Bovenstaande instellingen configureren algemene toegang tot agenda's. Indien er bedrijfsrichtlijnen zijn over striktere toegang tot agenda's kan middels deze [link](https://learn.microsoft.com/en-us/graph/auth-limit-mailbox-access) aanvullende restricties worden gezet door middel van `ApplicationAccessPolicies`. Hiermee kan de toegang verder worden beperkt tot specifieke agenda's.

## Terugleveren
Verzamel deze gegevens en geef ze door aan het call center.
* Op de **Overzicht** pagina staan de `Toepassings-id (client-id)`, en de `Map-id (tenant-id)` 
* De eerder gemaakte `Client Secret Waarde`
* De email adressen van de mailboxen die gesynchroniseert moeten worden.

> **Let op!** De Client Secret heeft een beperkte houdbaarheid en dient maximaal elke 24 maanden te worden vernieuwt, en aangeleverd aan het call center.

