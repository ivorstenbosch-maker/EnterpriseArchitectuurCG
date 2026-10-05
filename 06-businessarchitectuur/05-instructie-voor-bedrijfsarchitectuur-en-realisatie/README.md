# Instructie voor bedrijfsarchitectuur en realisatie

De bedrijfsarchitectuur vormt het vertrekpunt voor de verdere uitwerking
van project- en solutionarchitecturen. Zij bepaalt de gewenste
waardestroom, de BusinessServices en de samenhang tussen
dienstverlening, processen en informatie. De onderliggende
architectuurdomeinen – informatie-, applicatie- en
technologiearchitectuur – werken deze keuzes vervolgens verder uit
binnen hun eigen verantwoordelijkheidsgebied.

Voor de ontwikkeling van software betekent dit een andere manier van
werken. De volgende ontwerpstappen gelden:

1.  **Start bij de maatschappelijke opgave en de waardestroom**

    Beschrijf eerst welke publieke waarde moet worden geleverd, welke
    gebeurtenis of behoefte van een inwoner of ondernemer centraal staat
    en welke waardestroom daarbij hoort. Pas daarna worden processen,
    gegevens en software beschouwd.

2.  **Bepaal de juiste architectuurscope**

    Project- en solutionarchitecturen worden vaak gestart vanuit een
    concrete vraag, zoals de vervanging van een applicatie of de
    verbetering van één bedrijfsproces. Deze afbakening is begrijpelijk
    vanuit projectsturing, maar vormt niet vanzelfsprekend de juiste
    architectuurscope.

    De architect onderzoekt daarom eerst de samenhang met de bredere
    dienstverlening. Dit vraagt om abstraheren en uitzoomen: welke
    waardestroom wordt ondersteund, welke andere processen, domeinen of
    organisatieonderdelen raken hetzelfde vraagstuk, en welke gegevens
    of BusinessServices worden gedeeld?

    Het doel is te voorkomen dat een lokaal vraagstuk leidt tot een
    lokale oplossing, terwijl een generieke voorziening of bredere
    architectuurkeuze leidt tot een betere dienstverlening voor de
    inwoner en meerwaarde biedt voor meerdere processen, domeinen of
    gemeenten.

3.  **Onderzoek bestaande bouwstenen**

    Voordat nieuwe functionaliteit wordt ontworpen, wordt onderzocht
    welke voorzieningen reeds beschikbaar zijn binnen het Platform
    Dienstverlening en de bredere Common Ground-community. Dit onderzoek
    omvat meerdere niveaus van hergebruik:

- Bestaande BusinessServices;

- Procesblauwdrukken (Process Blueprints, MijnServices);

- Building Blocks, formulieren en subprocessen;

- Beslisregels;

- Plugins en generieke koppelingen;

- Bestaande gegevensmodellen en registraties.

4.  **Modelleer de business**

    Vertaal de waardestroom naar samenhangende BusinessServices en
    bepaal welke verantwoordelijkheden, rollen en bedrijfsobjecten
    daarbij horen. Identificeer welke functionaliteit generiek is en
    welke domeinspecifiek blijft. BusinessServices vormen de logische
    bouwstenen waaruit processen worden samengesteld.

5.  **Werk de architectuurdomeinen uit**

    De gekozen BusinessServices vormen vervolgens het uitgangspunt voor
    de verdere uitwerking binnen de overige architectuurdomeinen:

- Informatiearchitectuur: begrippen, informatiemodellen, registraties en
  gegevenskwaliteit. Dit is ook de fase waarin Duurzame Toegankelijkheid
  en Rapportage wordt voorbereid, ingericht en getoetst.

- Applicatiearchitectuur: procesinrichting, services, API's,
  formulieren, beslisregels en integraties.

- Technologiearchitectuur: infrastructuur, beveiliging, deployment en
  operationele voorzieningen.

  Hierdoor blijven alle architectuurdomeinen consistent met dezelfde
  bedrijfsarchitectuur en waardestroom.

6.  **Ontwikkel iteratief**

    BusinessServices worden iteratief ontwikkeld, toegepast en verbeterd
    op basis van praktijkervaring. Implementaties leveren nieuwe
    inzichten op die kunnen leiden tot verbeteringen van de
    businessarchitectuur, waarna deze opnieuw beschikbaar worden gesteld
    aan de community. Zo ontstaat een levende referentiearchitectuur die
    zich continu ontwikkelt.

    <img
    src="../../media/media/image18.png"
    style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />
