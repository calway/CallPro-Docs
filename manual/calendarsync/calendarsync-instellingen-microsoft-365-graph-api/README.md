# Calendarsync instellingen Office 365 Graph API

Om gebruik te maken van nieuwe mogelijkheden zoals Online Teams meetings maken moet gebruik worden gemaakt van een Microsoft Graph API. De CallPro CalendarSync module heeft vanaf v5.0.0 ondersteuning voor deze nieuwe manier van werken met Microsoft 365. Volg de onderstaande stappen om een App registratie te maken die kan worden gebruikt met de CallPro.


## Registreer een applicatie in AzureAd
De klant moet in zijn/haar Microsoft 365 omgeving in Azure Active Directory een applicatie aanmaken voor de Agenda synchronisatie.

1. Ga naar de Azure portal en log in met een administrator account die Applicatie registraties kan aanmaken.

2. Selecteer nu links in het menu **Azure Active Directory**, en selecteer **App registrations** in de **Manage** sectie

3. Selecteer **New registration**, en vul de volgende waarden in:

    * Vul bij **Name** als waarde: `CallPro CalendarSync`
    * Vul bij **Supported account types** een waarde die voor dit bedrijf acceptabel is. Vaak is de Single Tenant optie voldoende.
    * Vul als **Redirect URI** de waarde: `https://login.microsoftonline.com/common/oauth2/nativeclient`

4. Kies **Register** om de Applicatie te maken. 

## Configureer app-only authenticatie
Vervolg nu de volgende stappen om een app-only registratie af te ronden.


* Ga naar **API permissions** in de **Manage** sectie van het navigatie menu.
* Druk op **Add a permission**, kies dan **Microsoft Graph** , **Application permissions**
* Zoek naar `calendar` permissions, selecteer `Calendars.ReadWrite` om toegang tot de calendars te geven.
* Zoek naar `mailbox` permissions, selecteer `MailboxSettings.Read`
* Indien via de Graph API ook emails gestuurd gaan worden selecteer dan aanvullend `SMTP.Send` en `User.Read` als delegated permission.
* Kies **Add Permissions** om alle gekozen permissions toe te voegen, je komt nu terug in het vorige scherm.
* Selecteer nu **Grant admin consent for organisatienaam** en accepteer de consent dialoog.
* Ga nu naar **Certificates & Secrets** in het navigatie menu in de **Manage** sectie
* Selecteer **New client secret**, geef dit een duidelijke omschrijving, kies de levensduur zo lang mogelijk tenzij er bedrijfspolicies zijn die korte secrets eisen. Dit is de periode dat dit secret door de CallPro CalendarSync van het call center gebruikt kan worden. Hoe korter hoe vaker dit moet worden bijgewerkt door zowel Bedrijf als call center.
* Noteer de **Value** deze is later niet meer oproepbaar dus vergeet dit niet.


Geef nu de **Application (client) ID**, de **Directory (Tenant) ID** en de zojuist gemaakte **Client Secret** door aan het call center. Geef ook de email adressen van de mailboxen die gesynchroniseert moeten worden.
