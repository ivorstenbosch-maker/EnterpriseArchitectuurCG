# Architectural Building Blocks (ABB’s) en clusters

Architectural Building Blocks (ABB's) beschrijven generieke capabilities
binnen het Platform Dienstverlening. Ze moeten tenslotte invulling geven
aan de hele gemeentelijke dienstverlening. Een uitgangspunt voor de
gemeentelijke processen zijn GEMMA’s applicatieservices. GEMMA biedt een
overzicht van
[referentiecomponenten](https://www.gemmaonline.nl/wiki/Overzicht_alle_referentiecomponenten)
en de bijbehorende services die gerealiseerd kunnen worden. Waar
GEMMA‑services vooral concrete softwarefuncties beschrijven, richten
ABB’s zich op de onderliggende capabilities die in *alle* gemeentelijke
domeinen terugkomen.

### ABB’s per functionele laag

De architectuur maakt het mogelijk om generiek te ontwerpen en
domeinoverstijgend te sturen. We clusteren functionaliteiten globaal op
het vijflagenmodel.

#### Laag 5 – Interactie

- **Functionaliteit:** Portalen, formulieren, klant- en objectbeelden,
  medewerkerinterfaces, en beheerinterfaces.

- **Doel:** Faciliteren van de interactie tussen inwoners, ondernemers,
  medewerkers en het platform.

- **Functionele eisen:**

  - Ondersteunt verschillende gebruikersgroepen en kanalen.

  - Verzamelt invoer en presenteert informatie, status en voortgang.

  - Begeleidt gebruikers bij het uitvoeren van taken en aanvragen.

  - Maakt gebruik van onderliggende proces- en dataservices, zonder deze
    te dupliceren.

#### Laag 4 – Procesinrichting

- **Functionaliteit:** Workflow, procesorkestratie, taakafhandeling,
  casusregie, besluitvorming en business rules.

- **Doel:** Uitvoeren, coördineren en bewaken van gemeentelijke
  dienstverlening.

- **Functionele eisen:**

  - Orkestreert processtappen en workflow.

  - Past wet- en regelgeving en businessregels toe.

  - Ondersteunt besluitvorming, taakafhandeling en casusregie.

  - Bewaakt voortgang en samenhang van processen.

  - Maakt uitsluitend gebruik van gegevens uit de registraties en
    dataservices.

#### Laag 3 – Connectiviteit

- **Functionaliteit**: API's, FSC, events, notificaties, omnichannel
  communicatie.

- **Doel**: Verbinden van services en realiseren van veilige,
  gestandaardiseerde gegevensuitwisseling.

- **Functionele eisen:**

  - Ondersteunt synchrone en asynchrone communicatie.

  - Verzorgt notificaties, events en berichtuitwisseling.

  - Faciliteert federatieve gegevensuitwisseling en integratie.

  - Borgt interoperabiliteit door gebruik van open standaarden.

#### Laag 2 – Diensten

- **Functionaliteit**: Dataservices voor klanten, zaken, producten,
  verzoeken, berichten, taken en referentiegegevens.

- **Doel**: Valideren, ontsluiten en beschikbaar stellen van gegevens en
  businessfunctionaliteit.

- **Functionele eisen:**

  - Valideert en verwerkt mutaties op gegevens.

  - Biedt gestandaardiseerde API's voor raadpleging en mutatie.

  - Voorkomt duplicatie van gegevens en businesslogica.

  - Ontsluit gegevens onafhankelijk van de onderliggende registratie.

#### Laag 1 – Registraties

- **Functionaliteit**: Klant-, zaak-, product- en domeinregistraties,
  referentielijsten en externe bronnen.

- **Doel**: Duurzaam vastleggen en beheren van gegevens als bron voor
  het platform.

- **Functionele eisen:**

  - Vormen de bron voor de aan hen toegewezen gegevens.

  - Beheren gegevens, relaties, historie en metadata.

  - Bieden een consistente en herleidbare gegevensbasis.

  - Stellen gegevens uitsluitend beschikbaar via gestandaardiseerde
    dataservices.

### Crossfunctionele Architectural Building Blocks (ABB’s) 

Naast de vijf lagen kent het platform een aantal doorsnijdende
Architectural Building Blocks. Deze leveren generieke functionaliteit
die door meerdere lagen wordt gebruikt en zijn daarom niet aan één
specifieke laag toe te wijzen. Dit gaat om: Identity & Accessmanagement,
Autorisatie, Logging, Auditing, Security,Privacy, Monitoring en
Observability. Deze worden deels in de technische architectuur
gerealiseerd (Haven+) en deels in ABB’s die haaks op het vijflagenmodel
staan.

#### Functionele eisen:

- Borgen authenticatie, autorisatie en beveiliging.

- Verzorgen logging, auditing en observability.

- Ondersteunen duurzame toegankelijkheid, archivering en
  recordmanagement.

- Faciliteren omnichannel communicatie, notificaties en generieke
  platformdiensten.

  <img
  src="../../media/media/image24.png"
  style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Specificatie ABB’s niveau 2 

Op niveau 2 worden ABB’s uitgewerkt als configuraties binnen
componenten, waarmee de generieke services uit niveau 1 concreet worden
ingevuld. Het gaat hier om de vertaling van een BusinessService naar
configureerbare elementen zoals formulieren, BPMN-processen, business
rules en gegevensmodellen.

Het is mogelijk deze ABB’s structureel te mappen op de
GEMMA-applicatieservices, zie daarvoor [BIJLAGE - ABB’s GEMMA en
Platform
Dienstverlening](#bijlage---abbs-gemma-en-platform-dienstverlening).
