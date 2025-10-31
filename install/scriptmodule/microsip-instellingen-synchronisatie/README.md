# Microsip instellingen synchronisatie

## Scriptmodule vanaf v5.0.10
Dit werkt alleen als een recente versie van de scriptmodule en Resource Explorer beschikbaar zijn, en als de database versie minimaal 5.0.0 heeft.

1. Installeer de Scriptmodule via [installer.callpro.nl](https://installer.callpro.nl)
1. Ga in de Resource Explorer naar de Seat, en dan het tabblad Telefonie. De instelling is beschikbaar voor de AgentDial dialer. Zorg dat het vinkje bij `Softphone automatisch configureren` aan staat.

    ![Seat eigenschappen](media/seat-settings.png)
Alternatief kan dit ook in de Scriptmodule in het `Extra` menu `Dialing Configuratie` en dan de button `Configureren...` worden gedaan.

1. Controleer vervolgens ook dat in het `Control panel` bij `Dialing Configuratie` op het tabblad `Geavanceerd` de Microsip instellingen template is gevuld. Pas deze template alleen aan als je weet wat je doet. De standaard template is:

    ```
    [Settings]
    accountId=1
    bringToFrontOnIncoming=1
    crashReport=0
    enableLog=0
    updatesInterval=never
    DND=0
    denyIncoming=
    autoRecording=0
    localDTMF=0

    [Account1]
    label=CallPro[%SEAT.EXTENSION%]
    username=%SEAT.EXTENSION%
    authID=%SEAT.EXTENSION%
    password=%SEAT.EXTENSION%
    displayName=%SEAT.EXTENSION%
    server=%ASTERISK.HOSTNAME \SW"","%DIALING.ASTERISKIP%"%
    domain=%ASTERISK.HOSTNAME \SW"","%DIALING.ASTERISKIP%"%
    ```

## Geavanceerde microsip instellingen
### Schakel bepaalde knoppen in microsip uit
De gebruiker kan in de sessie terwijl microsip actief is deze settings wel weer aan zetten en gebruiken, maar initieel staan ze uit.

```ini
DND=0
denyIncoming=
forwarding =
forwardingNumber =
forwardingDelay =20
autoRecording=0
disableMessaging=1
```

De eerste twee regels zorgen ervoor dat Do-Not-Disturb standaard uit staat, en er geen knop zichtbaar is in microsip om dit aan/uit te zetten.

De volgende 3 regels zorgen ervoor dat er geen call-forwarding optie zichtbaar en actief is.

Met `autoRecording=0` wordt voorkome ndat Agents lokaal opnames maken van gesprekken en `disableMessaging` zorgt er voor dat de chat functie van microsip uit staat. Zelfs als deze aan wordt gezet werkt chat niet omdat wij dit **niet** configureren in de Asterisk.

### Configureer auto-answer
Als agents vaak vergeten om hun toestel te beantwoorden kan microsip worden ingesteld om automatisch te antwoorden als Callpro het toestel belt. Voeg hiervoor de volgende regel toe in de `[Settings]` deel van de configuratie.

```ini
autoAnswer=all
```

