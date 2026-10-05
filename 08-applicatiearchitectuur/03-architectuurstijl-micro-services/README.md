# Architectuurstijl: (micro)services

Binnen de (historische) ontwikkeling van applicatie-architecturen zijn
verschillende stijlen te onderscheiden:

- **Monolithische architectuur:** Eén codebase en deployment. Eenvoudig
  te starten, maar beperkt schaalbaar en lastig aanpasbaar.

- **Modulaire monoliet:** Logische scheiding binnen één applicatie.
  Beter gestructureerd, maar nog steeds één deploybare eenheid.

- **Service-georiënteerde architectuur (SOA):** Services met centrale
  orkestratie (bijv. via ESB). Flexibeler, maar vaak complex door
  centrale afhankelijkheden.

<!-- -->

- **Microservice-architectuur:** Kleine, zelfstandige services die
  onafhankelijk deploybaar zijn en gericht zijn op wendbaarheid en
  schaalbaarheid.

Er bestaan verschillende manieren om de architectuur van het Platform
Dienstverlening te beschrijven, zoals *microservice-architectuur* of
*composable architecture*. Ook wordt soms gesproken over een
*distributed monolith* wanneer de technische ontkoppeling onvoldoende is
gerealiseerd. Binnen deze architectuur wordt bewust gekozen voor de term
(**micro)service-architectuur** als referentiemodel voor de verdere
uitwerking, omdat deze aansluit bij de eisen rondom flexibiliteit,
schaalbaarheid en snelle aanpasbaarheid (bijv. door beveiligingseisen).

### Kenmerken van services

Binnen het platform vormen services de centrale bouwstenen. Dit is de
realisatie van het [**Principe: (Micro)
servicearchitectuur**](../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-micro-servicearchitectuur). Een service
wordt gekenmerkt door:

- **Single Responsibility Boundary:** Een service ondersteunt één
  duidelijke business capability

- **Autonomie:** Services zijn zelfstandig te ontwikkelen, testen en
  deployen

### Afbakening van services

De grootte en grenzen van services worden bepaald aan de hand van
meerdere perspectieven:

- **Domain-Driven Design (bounded contexts):** Diensten worden gebaseerd
  op betekenisvolle domeinen

- **Business capabilities:** Wat de dienstverlening moet leveren vormt
  de basis

- **Performance en belasting:** Verschillende loadprofielen → aparte
  services

- **Foutisolatie:** Kritische onderdelen worden gescheiden.

De set van services binnen het platform is niet statisch. Op basis van
nieuwe inzichten en gebruik kan de architectuur worden aangepast, door
het:

- Samenvoegen van services

- Opsplitsen van services en

- Introduceren van nieuwe services.

Dit maakt onderdeel uit van het architecturaal continuüm, waarin de
architectuur meegroeit met de organisatie en het platform.

### Criteria voor services

Elke service in het platform moet voldoen aan de volgende criteria:

- **Single purpose (één duidelijke verantwoordelijkheid) -** Elke
  service heeft één afgebakende taak of business capability. Dit
  voorkomt dat logica onnodig wordt verweven met andere functionaliteit

- **Hergebruik binnen het platform -** Services interacteren met
  bestaande services in het landschap en introduceren geen reeds
  aanwezige functionaliteit. Dit voorkomt duplicatie, bevordert
  consistent gedrag, faciliteert dat je kunt standaardiseren op
  services/capabilities en verlaagt beheer- en onderhoudslast binnen het
  platform.

- **Aansluiten op het platform -** Services sluiten volledig aan op de
  applicatie infrastructuur (waaronder technische notificaties, logging,
  authorisatie, identificatie)

- De [Patronen en API-specificaties](../11-toegepaste-patronen/README.md#toegepaste-patronen) worden
  gevolgd.

### Voordelen van de gekozen architectuur

De microservice-architectuur biedt de volgende voordelen:

- Single purpose (één duidelijke verantwoordelijkheid): Elke service
  heeft een afgebakende taak

- Technologische flexibiliteit: Teams kiezen zelf technologie per
  service

- Onafhankelijke deployability: Services kunnen los uitgerold worden

- Schaalbaarheid: Alleen zwaar belaste onderdelen worden opgeschaald

- Veerkracht en foutisolatie: Storingen blijven beperkt tot één service

- Beheersbare codebases: Kleinere systemen zijn beter te begrijpen

- Autonome teams: Teams zijn eigenaar van hun service

- Continue levering (CI/CD): Snelle en veilige releases

- Experimenteerbaarheid: Nieuwe functionaliteit kan geïsoleerd
  ontwikkeld worden.

De gekozen architectuur stelt ook eisen aan de organisatie en techniek:

- Sterke automatisering: CI/CD, testing en monitoring zijn essentieel

- Volwassen DevOps-teams: Teams zijn verantwoordelijk voor de volledige
  lifecycle

- Gestandaardiseerde interfaces: API’s en events moeten uniform zijn

- Observability: Logging, monitoring en tracing zijn noodzakelijk

- Governance op architectuurprincipes: Zonder kaders ontstaat
  fragmentatie.
