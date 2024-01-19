# Calendarsync instellingen Microsoft 365 OAuth Flow
> Sinds 1-10-2022 is dit het alternatief op de Basic authentication die is uitgeschakeld. Wij adviseren klanten om over te gaan op de [Microsoft Graph API](../calendarsync-instellingen-microsoft-365-graph-api/README.md)

Om gebruik te kunnen blijven van de CallPro CalendarSync module adviseren wij klanten uiterlijk na de migratie naar CallPro 5.0 met klanten af te stemmen over de nieuwe instellingen die nodig zijn.

> Een technische beschrijving staat op: https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/how-to-authenticate-an-ews-application-by-using-oauth#register-your-application


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


* Ga naar **Manifest** in de **Manage** sectie van het navigatie menu.    
* Zoek de `requiredResourceAccess` property in het manifest op en voeg het volgende toe binnen de vierkante haken ([])

```json
{
"resourceAppId": "00000002-0000-0ff1-ce00-000000000000",
"resourceAccess": [
    {
        "id": "dc890d15-9560-4a4c-9b7f-a736ec74ec40",
        "type": "Role"
    }
]
}
```
* Druk op **Save**
* Check nu bij **API Permissions** in de Manage sectie dat de `full_access_as_app` recht is toegekend.
Als bij de klant security policies actief zijn die het niet toestaan om `full_access` rechten toe te kennen dan dienen beperkte rechten voor de "Office 365 Exchange Online" te worden gegeven die voldoende zijn om Agenda's te synchroniseren.
* Selecteer nu **Grant admin consent for org** en accepteer de consent dialoog.
* Ga nu naar **Certificates & Secrets** in het navigatie menu in de **Manage** sectie
* Selecteer **New client secret**, geef dit een duidelijke omschrijving, kies de levensduur zo lang mogelijk tenzij er bedrijfspolicies zijn die korte secrets eisen. Dit is de periode dat dit secret door de CallPro CalendarSync van het call center gebruikt kan worden. Hoe korter hoe vaker dit moet worden bijgewerkt door zowel Bedrijf als call center.
* Noteer de **Value** deze is later niet meer oproepbaar dus vergeet dit niet.


Geef nu de **Application (client) ID**, de **Directory (Tenant) ID** en de zojuist gemaakte **Client Secret** door aan het call center. Geef ook de email adressen van de mailboxen die gesynchroniseert moeten worden.
