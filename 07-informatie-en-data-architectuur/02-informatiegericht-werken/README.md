# Informatiegericht werken

Volgens de visie wordt de informatiearchitectuur niet primair opgebouwd
vanuit applicaties of processen, maar vanuit de werkelijkheid die
gemeenten administreren. Personen, organisaties, producten, zaken,
besluiten, objecten en andere bedrijfsobjecten worden als
bedrijfsobjecten gemodelleerd die op zichzelf een domein vormen, en
vervolgens via gestandaardiseerde services beschikbaar gesteld aan
BusinessServices, MijnServices en andere toepassingen. Dit volgt het
principe:

> **[Principe: Informatiegericht
> werken](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-informatiegericht-werken):** Informatie vormt het
> verbindende element tussen dienstverlening, processen, applicaties en
> organisatie. Gegevens worden onafhankelijk van individuele processen
> en applicaties beheerd, zodat zij meervoudig kunnen worden gebruikt
> voor uitvoering, dienstverlening en besluitvorming.

Hierin zijn de volgende begrippen relevant:

- **Informatie** is de betekenis die mensen aan gegevens geven binnen
  een bepaalde context. Om deze betekenis eenduidig vast te leggen,
  wordt gebruikgemaakt van begrippen, definities en informatiemodellen.
  Hierbij vormt het datamodel
  ([MIM](https://docs.geostandaarden.nl/mim/mim/)) de richtlijn voor het
  vastleggen van de structuur van gegevens, terwijl het begrippenkader
  ([NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/)) de betekenis
  van deze gegevens vastlegt.

- **Data (gegevens)** is de concrete vastlegging van waarnemingen of
  beweringen over objecten. Binnen het Platform Dienstverlening betreft
  dit de opslag, het beheer en de uitwisseling van gegevens via
  registraties en gestandaardiseerde dataservices. Gegevens vormen de
  basis waaruit informatie kan worden afgeleid.

**Applicaties** zijn softwarecomponenten die gegevens verwerken en
functionaliteit aanbieden ter ondersteuning van bedrijfsprocessen en
dienstverlening. Dit onderscheid zorgt ervoor dat:

- Betekenis (informatie) niet afhankelijk is van technische
  implementatie (applicatie)

<!-- -->

- Gegevens consistent en herbruikbaar kunnen worden toegepast over
  verschillende processen en systemen

- Wijzigingen in één laag (bijvoorbeeld applicaties) beperkt effect
  hebben op andere lagen

- Een gemeenschappelijk begrip ontstaat tussen verschillende
  stakeholders en rollen, zoals business, architectuur en development,
  doordat zij vanuit dezelfde begrippen en modellen werken
