# Inhoudsopgave

[Algemeen](#algemeen)

[De Resource Explorer](#de-resource-explorer)

[Control panel](#control-panel)

* [Belopdrachtstatussen](./controlpanel-belopdrachtstatussen.md#belopdrachtstatussen)

* [Scriptdefinities](./controlpanel-scriptdefinities.md#scriptdefinities)

* [Importdefinities](./controlpanel-importdefinities.md#importdefinities)

* [Exportdefinities](#exportdefinities)

* [Zoeken tools](#zoeken-tools)

* [Campagne grid](#campagne-grid)

* [Systeemconfiguratie](#systeemconfiguratie)

[Algemeen](#algemeen)

[Script-omgeving](#script-omgeving)

[Diagnose](#diagnose)

[Bestandslokaties](#bestandslokaties)

[Systeem scriptvelden](#systeem-scriptvelden)

[Pauze types](#pauze-types)

[Geavanceerd](#geavanceerd)

[Resources](#resources)

* [Agent](#agent)

* [Call-list](#call-list)

* [Calendar](#calendar)

* [Seat](#seat)

* [Groups](#groups)

* [Campaigns](#campaigns)

* [Snelkoppelingen](#snelkoppelingen)

[Scriptmodule](#scriptmodule)

[Agenda module](#agenda-module)

[CallProPortal](#callproportal)

[Belangrijke conventies in CallPro](#belangrijke-conventies-in-callpro)

[Hoe biedt CallPro een belopdracht aan](#hoe-biedt-callpro-een-belopdracht-aan)

# Algemeen

CallPro werkt met een aantal termen die door de hele applicatie zijn
doorgevoerd. Ook user-interface standaarden worden hier behandeld.


# Scriptmodule

TODO

## Agenda module

TODO

# CallProPortal

Zie de CallproPortal handleiding.

# Belangrijke conventies in CallPro

## Hoe biedt CallPro een belopdracht aan

CallPro doorloopt meerdere fasen bij het ophalen van een nieuwe
belopdracht. Deze stappen beschrijven het gedrag zoals dit standaard
ingesteld staat. Diverse instellingen kunnen deze volgorde beïnvloeden.

1.  Kijk over alle gekoppelde campagnes en actieve bellijsten in deze
    campagnes naar belopdrachten in de terugbellen categorie
    (terugbellen hoog) die moeten worden aangeboden. Biedt de eerste
    belopdracht aan die op basis van prioriteit binnen de terugbellen
    categorie, en terugbeltijd moet worden gebeld.

2.  Kijk over alle gekoppelde campagnes en actieve bellijsten in deze
    campagnes naar belopdrachten in de terugbellen categorie
    (terugbellen laag) die moeten worden aangeboden. Biedt de eerste
    belopdracht aan die op basis van prioriteit binnen de terugbellen
    categorie, en terugbeltijd moet worden gebeld.

3.  Kijk over gekoppelde campagnes en actieve bellijsten in deze
    campagnes op volgorde van campagne prioriteit en daarbinnen bellijst
    prioriteit naar de belopdrachten in de resterende categorieën (niet
    bereikt hoog, systeem en niet bereikt laag). Biedt de eerste
    belopdracht aan die op basis van de prioriteit binnen deze
    categorieën, en terugbeltijd moet worden gebeld.
