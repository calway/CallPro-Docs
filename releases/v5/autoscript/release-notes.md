# Autoscript Release Notes
Dit zijn de Release Notes voor het Autoscript. Release Notes voor de overige onderdelen van CallPro zijn [hier](/releases/v5/release-notes) te vinden.

<br/>

***
## v5.0.6 - 2025-01-08
### Changed
* Mogelijkheid om met de `@F(Email)` optie een email adres te controleren op geldigheid. Dit is alleen een invoer geldigheid, niet perse een bestaand email adres!
* Diverse buttons voorzien van een `tabindex="-"` zodat deze elementen worden genegeerd als je met <kbd>TAB</kbd> door de velden loopt.

***
## v5.0.5 - 2024-09-23
Op het leaderboard wordt nu optioneel de resterende beltijd voor vandaag getoond. Hiervoor dient op de `Campaigns` folder een variabale `Leaderboard..TargetAgentTimePerDay` van type Karakter die het aantal uren weergeeft dat gebeld moet worden. Een getal geeft het aantal dagen aan, dus `10` geeft aan 10x24 uur. Alternatief kan ook `14:00` worden gebruikt om aan te gaven dat erde doelstelling 14 uur is.

***
## v5.0.4 - 2024-09-19
Rebuild vanwege sommige klanten die een oude SQL Server gebruiken die geen tls1.2 of tls1.3 support heeft. 

***
## v5.0.3 - 2024-07-04
In deze versie is de `@F(Url)` feature aangepast zodat het juiste venster kan worden geopend als gebruik wordt gemaakt van de -- op dit moment -- experimentele implementatie van de WebView2 browser engine.

En veel interne library updates die functioneel geen verschil maken.

***
## v5.0.2 - 2023-12-08
Alleen interne updates

***
## v5.0.1 - 2023-02-01
Dit is de eerste officiele release van deze versie. Door de vertragingen is het autoscript ook compatible gemaakt met eerdere CallPro versies w.o. 4.3.2 en 4.3.1