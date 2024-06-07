### SMS Action
```xml
<Action Type="SMS" gateway="speakup|spryng|spryng-v1|messagebird" [spryngroute="business|..."]>
    <Username>username</Username>
    <Password>password</Password>
    <Originator>CALLPRO</Originator>
    <Recipients>31612345678</Recipients>
    <Message>SMS bericht %SCRIPT.NAME_LAST%</Message>
</Action>
```
Verstuurd een sms bericht (message) naar recipient(s). Recipients mag 1 zijn, maar ook meerdere komma gescheiden mobiele nummers. Standaard wordt verstuurd via Speakup, maar ook spryng (Simple API), spryng-v1 of messagebird kan worden gekozen als SMS gateway.
Voor spryng en spryng-v1 is er een extra optie om de route te kiezen, de standaard is '*business*'. Kijk bij de betreffende gateway provider hoe en welke account/password combinatie moet worden meegegeven.
