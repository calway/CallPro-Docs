# Mailserver installeingen voor Microsoft Graph API
## Registreer een applicatie in Microsoft Entra ID (voorheen AzureAd)
De klant moet in zijn/haar Microsoft 365 omgeving in Azure Active Directory een applicatie aanmaken voor de Agenda synchronisatie.

1. Ga naar de Entra portaal (entra.microsoft.com) en log in met een administrator account die Applicatie registraties kan aanmaken.

1. Selecteer **Applications** en dan de sub-optie **App registrations**

1. Selecteer **New registration**, en vul de volgende waarden in:

    * Vul bij **Name** als waarde: `CallPro Fulfilment`
    * Vul bij **Supported account types** een waarde die voor dit bedrijf acceptabel is. Vaak is de Single Tenant optie voldoende.
    * Vul als platform `public client/native (mobile & desktop)`
    * Vul als Redirect URI de waarde: `https://login.microsoftonline.com/common/oauth2/nativeclient`

1. Kies **Register** om de Applicatie te maken. 
1. Ga nu in de app registratie naar **Certificates & secrets**
    * Druk hier op ** New Client secret**
    * Geef als naam iets herkenbaars, zoals de naam van het call center, en de huidige datum, ie. "calway-2024-04-02"
    * Kies bij Expires de langst mogelijke periode, op dit moment is dat 24 maanden.
    * Vergeet geen herinnering in je agenda te zetten om na 23 maanden een nieuw secret te maken en die aan het call center door te geven anders stop de synchronisatie na 24 maanden!
    * Vergeet niet om de client secret (de waarde zichtbaar in de **Value** kolom) te kopieren en vast te leggen, dit wordt eenmalig afgebeeld!

## Configureer app-only authenticatie
Vervolg nu de volgende stappen om een app-only registratie af te ronden.


* Ga naar **API permissions** in de **Manage** sectie van het navigatie menu.
* Druk op **Add a permission**, kies dan **Microsoft Graph**
* Zoek naar `SMTP.Send` bij de **Delegated permissions** om de  het mogelijk te maken om emails te sturen.
* Zoek ook naar `User.Read` bij de **Delegated permissions** en ken dit recht ook toe.
* Zoek naar `mailbox` permissions bij de **Application permissions** en selecteer `MailboxSettings.Read`
* Kies **Add Permissions** om alle gekozen permissions toe te voegen, je komt nu terug in het vorige scherm.
* Selecteer nu **Grant admin consent for organisatienaam** en accepteer de consent dialoog.


Geef nu de **Application (client) ID**, de **Directory (Tenant) ID** en de zojuist gemaakte **Client Secret** door aan het call center. Geef ook de email adressen van de mailboxen die gesynchroniseert moeten worden.
> **Let op!** De Client Secret heeft een beperkte houdbaarheid en dient minimaal elke 24 maanden te worden vernieuwt, en aangeleverd aan het call center.