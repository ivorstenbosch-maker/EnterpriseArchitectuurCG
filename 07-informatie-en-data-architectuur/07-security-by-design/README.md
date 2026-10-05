# Security by Design

Informatiebeveiliging is een randvoorwaarde voor het Platform
Dienstverlening. Gemeenten zijn verantwoordelijk voor het voldoen aan de
[Baseline Informatiebeveiliging Overheid
(BIO)](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/cybersecurity/bio-en-ensia/baseline-informatiebeveiliging-overheid/)
en de daarop gebaseerde normen, processen en risicobeheersing. Een
volledige toetsing aan de BIO of ISO/NEN 27001 vindt plaats op het
niveau van de ingerichte organisatie, de operationele beheerprocessen en
de daadwerkelijk geïmplementeerde ICT-omgeving, en valt daarmee buiten
de scope van deze Enterprise Architectuur.

Deze architectuur beschrijft uitsluitend de architectonische
uitgangspunten voor *Security by Design*: de wijze waarop beveiliging
vanaf het ontwerp integraal onderdeel vormt van het Platform
Dienstverlening. Hiermee wordt invulling gegeven aan [**Principe:
Kwaliteit by Design**](../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-kwaliteit-by-design):

> Niet-functionele kwaliteitseisen worden vanaf het ontwerp integraal
> meegenomen in architectuur, software en dienstverlening. Aspecten
> zoals informatiebeveiliging, privacy, toegankelijkheid,
> informatiebeheer, logging, auditing en beheerbaarheid zijn geen
> afzonderlijke voorzieningen achteraf, maar vormen een integraal
> onderdeel van iedere platformvoorziening.

### Platformverantwoordelijkheid security

Het Platform Dienstverlening realiseert een belangrijk deel van de
generieke technische beveiligingsvoorzieningen als gemeenschappelijke
platformcapabilities. Hierdoor hoeven individuele services deze
voorzieningen niet telkens opnieuw te implementeren en ontstaat een
uniforme beveiligingsbasis voor het gehele platform.

Deze generieke capabilities worden grotendeels gerealiseerd door de
Haven+ infrastructuur, zie onder meer het principe [*Security by
default* in de Haven+
architectuur](https://havenplus.commonground.nl/docs/haven-plus-architecture-principles/#ap-06--security-by-default).
Hierdoor kunnen ontwikkelteams zich concentreren op de functionele
beveiliging van hun eigen services.

### Verantwoordelijkheid van services

De beschikbaarheid van generieke platformvoorzieningen ontslaat de
proceseigenaar niet van de eigen verantwoordelijkheid voor de inrichting
van de service. Bij iedere implementatie blijft de proceseigenaar
verantwoordelijk voor onder andere:

- Correcte autorisatie van bedrijfsfunctionaliteit;

- Rechtmatige verwerking van gegevens;

- Invoervalidatie en bescherming tegen kwetsbaarheden;

- Correcte toepassing van privacy- en informatiebeveiligingsmaatregelen;

- Veilige softwareontwikkeling en onderhoud.

Platformbeveiliging en applicatiebeveiliging vullen elkaar daarmee aan;
maar ook bij de uitbesteding van ontwikkeling of beheer blijft de
proceseigenaar eindverantwoordelijk.

### Verdere uitwerking

De concrete implementatie van Security by Design wordt in deze
Enterprise Architectuur niet verder uitgewerkt. Hiervoor wordt verwezen
naar:

- De **Technologiearchitectuur** (Haven+ en platformvoorzieningen);

- De **Aansluitvoorwaarden Platform Dienstverlening**, waarin de
  technische beveiligings- en ontwikkelvereisten voor platformservices
  en aangesloten applicaties zijn opgenomen, waaronder eisen aan
  identity, autorisatie, OpenTelemetry, GitOps, Kubernetes, CI/CD,
  containerbeveiliging, softwarekwaliteit en releasebeheer;

- De gemeentelijke BIO-governance, waarin risicomanagement,
  classificatie, incidentmanagement, leveranciersmanagement, auditing en
  compliance zijn belegd.

- Een Security Handboek waarin de BIO2-beheersmaatregelen voor de
  relevante domeinen worden uitgewerkt tot concrete
  beveiligingsstandaarden voor het platform en services. Dit document is
  in ontwikkeling. Publicatie volgt.
