# Aanvullende eisen voor platformservices

Een **platformservice (Categorie A)** maakt onderdeel uit van het
Platform Dienstverlening. In tegenstelling tot een aangesloten
applicatie wordt een platformservice opgenomen in de
referentiearchitectuur, valt deze onder de architectuurgovernance van
het platform en wordt zij gezamenlijk beheerd en doorontwikkeld.

<img
src="../../media/media/image37.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Om die reden gelden voor platformservices, naast de (niet-)functionele
aansluitvoorwaarden Common Ground, aanvullende eisen op het gebied van
platformkwaliteit, ontwikkelkwaliteit en organisatorische inbedding.
Deze aanvullende eisen waarborgen dat platformservices op een uniforme,
veilige en beheerbare wijze bijdragen aan de doorontwikkeling van het
Platform Dienstverlening.

### Platformkwaliteit

Platformkwaliteit beschrijft de technische, niet-functionele en
architectonische eisen waaraan software moet voldoen om onderdeel te
kunnen worden van het Platform Dienstverlening. Deze eisen zorgen ervoor
dat platformservices veilig, beheersbaar en uitwisselbaar kunnen worden
ingezet binnen een cloud-native Haven-infrastructuur en bijdragen aan
een uniforme referentiearchitectuur.

Gemeenten willen platformservices van verschillende leveranciers zonder
maatwerk kunnen combineren binnen één samenhangend platform. Daarom
worden eisen gesteld aan onder meer architectuur, hergebruik van
bestaande voorzieningen, releasebeheer, deployment, security,
observability, documentatie, registraties, API's en runtime-gedrag. Door
deze eisen uniform toe te passen ontstaat een toekomstbestendig platform
waarin componenten onafhankelijk kunnen worden ontwikkeld, beheerd en
doorontwikkeld, terwijl de samenhang van de referentiearchitectuur
behouden blijft.

### Eisen aan architectuur

Als platformservice wordt de oplossing onderdeel van het Platform
Dienstverlening. De inrichting en doorontwikkeling van dit platform
worden gestuurd door de [Enterprisearchitectuur Common Ground & Platform
Dienstverlening](https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/enterprisearchitectuur).
Deze architectuur beschrijft de visie, architectuurprincipes,
referentiearchitectuur, standaarden en governance die richting geven aan
de ontwikkeling van het platform. Platformservices sluiten hierop aan en
dragen bij aan een samenhangend, herbruikbaar en toekomstbestendig
platform.

De architectuur vormt daarmee het toetsingskader voor ontwerp- en
implementatiekeuzes. Van leveranciers wordt verwacht dat zij kunnen
aantonen hoe hun oplossing aansluit op de architectuurprincipes, de
referentiearchitectuur en de geldende standaarden van het Platform
Dienstverlening. Afwijkingen zijn uitsluitend toegestaan wanneer deze
vooraf zijn gemotiveerd en door het Platformmanagement zijn
geaccepteerd.

- **Eis** – De platformservice voldoet aan de architectuurprincipes
  zoals beschreven in de *Enterprisearchitectuur Common Ground &
  Platform Dienstverlening*.

- **Eis** – De leverancier toont aan hoe de oplossing past binnen de
  referentiearchitectuur en de toegepaste architectuurpatronen.

- **Eis** – Afwijkingen van de Enterprisearchitectuur worden vooraf
  gemotiveerd, vastgelegd en ter besluitvorming voorgelegd aan het
  Platformmanagement.

  **Businessarchitectuur**

  Platformservices ondersteunen de businessarchitectuur van het Platform
  Dienstverlening. Ontwikkeling vindt plaats vanuit de gewenste
  dienstverlening en de onderliggende businesscapabilities en
  waardestromen, niet vanuit een individuele applicatie of
  organisatorische eenheid. Platformservices sluiten aan op de
  architectuurprincipes en ontwerpuitgangspunten zoals beschreven in de
  Enterprisearchitectuur Common Ground & Platform Dienstverlening.

#### Eisen

- Eis – De leverancier toont aan hoe de platformservice aansluit op de
  businessarchitectuur en de architectuurprincipes van het Platform
  Dienstverlening.

- Eis – De afbakening en verantwoordelijkheid van de platformservice
  sluiten aan op de businessarchitectuur en de daarin beschreven
  service-indeling.

- Eis – Nieuwe functionaliteit wordt ontwikkeld conform het principe
  Generiek vóór specifiek en draagt bij aan een samenhangend en
  herbruikbaar platform.

### Registraties en API's

Registraties en API's vormen de kern van de applicatiearchitectuur van
het Platform Dienstverlening. De inrichting van registraties,
dataservices en API's voldoet aan de referentiearchitectuur,
ontwerpprincipes en standaarden zoals beschreven in de
Enterprisearchitectuur Common Ground & Platform Dienstverlening. Dit
betreft onder meer de architectuur van registraties, de scheiding tussen
registraties, dataservices en processen, de eisen aan betrouwbare
registraties en de architectuur van API's.

**Eisen**

- **Eis** – Nieuwe registraties worden uitsluitend gerealiseerd wanneer
  hiervoor een aantoonbare architectuurnoodzaak bestaat en bestaande
  registraties niet kunnen worden uitgebreid.

- **Eis –** API's voldoen aan de binnen het Platform Dienstverlening
  toegepaste API-architectuur, standaarden en ontwerpprincipes zoals
  beschreven in de [Enterprisearchitectuur Platform
  Dienstverlening.](../../08-applicatiearchitectuur/10-architectuur-van-registraties/README.md#architectuur-van-registraties)

- **Eis –** REST API's voldoen aan de [REST API Design
  Rules](https://logius-standaarden.github.io/API-Design-Rules/)

- **Eis –**API's worden gespecificeerd conform de [OpenAPI Specification
  3.x](https://spec.openapis.org/oas/latest.html)

- **Eis –** Eventgedreven integraties implementeren het [CloudEvents
  NL-profiel](https://www.gemmaonline.nl/wiki/De_CloudEvents_standaard)

- Eis – De leverancier toont aan dat registraties en API's aansluiten op
  de referentiearchitectuur van het Platform Dienstverlening.

### Eisen aan releases

De wijze waarop software wordt gebouwd, verpakt en uitgerold is bepalend
voor de betrouwbaarheid en beheerbaarheid van het Platform
Dienstverlening. Daarom worden eisen gesteld aan releasebeheer,
packaging, versiebeheer en testautomatisering.

#### GitOps

- **Eis** – Releasebeheer volgt de **GitOps-methodiek**
  (<https://opengitops.dev>) en is gebaseerd op een gedocumenteerd en
  beproefd proces.

  - De gewenste systeemstatus wordt declaratief vastgelegd in
    **YAML**-bestanden (<https://yaml.org/spec/>), en niet door middel
    van imperatieve scripts.

  - Git vormt de *Single Source of Truth* voor alle configuratie en
    bevat een volledige, versiegecontroleerde historie van wijzigingen,
    zodat iedere wijziging reproduceerbaar is en eenvoudig kan worden
    teruggedraaid.

  - GitOps-agents, zoals **Flux** (<https://fluxcd.io>) of **Argo CD**
    (<https://argo-cd.readthedocs.io>), monitoren de Git-repository
    continu en rollen goedgekeurde wijzigingen automatisch uit naar de
    doelomgeving.

  - GitOps-agents vergelijken continu de werkelijke toestand met de
    gewenste toestand zoals vastgelegd in Git (*continuous
    reconciliation*) en herstellen afwijkingen automatisch.

- **Eis** – Configuratiemanagement is volledig ingericht volgens de
  GitOps-principes.

#### Packaging en versiebeheer

- **Eis** – De applicatie wordt verpakt en uitgerold met **Helm charts**
  (<https://helm.sh>) die voldoen aan de **Helm Chart Best Practices**
  (<https://helm.sh/docs/chart_best_practices/>).

- **Eis** – Voor iedere release worden release notes opgesteld en actief
  beschikbaar gesteld, inclusief wijzigingen aan Helm charts.

- **Eis** – Software, containerimages en Helm charts worden
  versiebeheerd conform **Semantic Versioning 2.0.0 (SemVer)**
  (<https://semver.org>).

- **Eis** – Vanaf versie **1.0.0** (*production ready*) worden minimaal
  maandelijks nieuwe patch-releases van de containerimages beschikbaar
  gesteld, zodat beveiligingsupdates van het onderliggende
  besturingssysteem en gebruikte libraries tijdig kunnen worden
  toegepast.

#### Containerimages

- **Eis** – Containerimages bevatten uitsluitend de functionaliteit die
  noodzakelijk is voor de werking van de applicatie. Hierdoor wordt het
  aanvalsvlak beperkt, de herkomst van softwarecomponenten inzichtelijk
  gehouden en de signaal-ruisverhouding van kwetsbaarheidsscanners,
  zoals **CVE** (<https://www.cve.org>), verbeterd.

- **Eis** – Er wordt gebruikgemaakt van minimale containerimages, bij
  voorkeur **distroless images**
  (<https://edu.chainguard.dev/chainguard/chainguard-images/about/>).
  Indien dit niet mogelijk is, bevatten containerimages geen
  OS-packagemanagers of shells. Wanneer dergelijke componenten tijdens
  het buildproces noodzakelijk zijn, worden zij vóór oplevering uit het
  uiteindelijke containerimage verwijderd.

#### Geautomatiseerde kwaliteitscontroles

- **Eis** – Iedere release doorloopt een geautomatiseerde
  CI/CD-pipeline. De testmethodieken, testresultaten en opvolging zijn
  volledig transparant en reproduceerbaar vanuit de Git-repository.

- **Eis** – Uit de documentatie blijkt:

  - Welke kwaliteitscontroles zijn uitgevoerd;

  - Hoe deze controles zijn ingericht;

  - Wat de resultaten zijn;

  - Welke kwetsbaarheden zijn geconstateerd;

  - Hoe geconstateerde kwetsbaarheden zijn gemitigeerd; of

  - Waarom een geregistreerde uitzondering (*exception*) is
    geaccepteerd.

- **Eis** – De CI/CD-pipeline bevat ten minste de volgende
  geautomatiseerde kwaliteitscontroles:

  - Regressietests op een Haven-omgeving in combinatie met
    veelvoorkomende platformcomponenten;

  - Unit tests (aanbevolen);

  - Performancetests op basis van een vaste resourcetoewijzing;

  - Containerscans op bekende kwetsbaarheden, bijvoorbeeld met **Trivy**
    (<https://trivy.dev>);

  - Statische analyse van de applicatiecode (*Static Application
    Security Testing – SAST*);

- **API fuzz testing** voor het identificeren van fouten en potentiële
  kwetsbaarheden.

### Eisen aan technische documentatie

Platformservices moeten zelfstandig kunnen worden geïnstalleerd,
geconfigureerd, beheerd en doorontwikkeld. Daarom is actuele, volledige
en technisch inhoudelijke documentatie beschikbaar voor implementatie,
beheer, integratie en operationeel gebruik.

- **Eis** – Installatieprocedures, configuratieopties en
  beheermogelijkheden zijn volledig gedocumenteerd.

- **Eis** – De documentatie bevat een **High Level Design (HLD)** en
  **Low Level Design (LLD)** van de applicatie, inclusief de
  architectuur, componenten en integratiemogelijkheden met andere
  platformcomponenten.

- **Eis** – De documentatie beschrijft het gebruikers- en
  autorisatiemodel, waaronder de beschikbare rollen, rechten en de
  mogelijkheden om deze te configureren of uit te breiden.

- **Eis** – De minimale systeemeisen van de applicatie, waaronder CPU-,
  geheugen- en eventuele opslagvereisten, zijn gedocumenteerd.

- **Eis** – De documentatie bevat een schaalbaarheidsadvies waarin is
  beschreven hoe de applicatie horizontaal en/of verticaal kan worden
  opgeschaald, welke randvoorwaarden daarvoor gelden en welk gedrag van
  de applicatie tijdens het schalen mag worden verwacht.

### Technische eisen aan de applicatie

Platformservices worden uitgevoerd binnen een Kubernetes-gebaseerde
Haven-omgeving. Daarom gelden aanvullende eisen aan interoperabiliteit,
runtime-gedrag, security, observability en beheerbaarheid. Deze eisen
waarborgen dat componenten van verschillende leveranciers op een
uniforme wijze kunnen worden geïmplementeerd, beheerd en doorontwikkeld.

#### Authenticatie en autorisatie

- **Eis** – Integratie met een **Identity Provider (IdP)** vindt plaats
  op basis van **OpenID Connect
  [(OIDC)](https://openid.net/developers/how-connect-works/)**. De
  applicatie ondersteunt iedere OIDC-conforme Identity Provider en mag
  geen afhankelijkheid hebben van een specifieke implementatie, zoals
  Keycloak.

#### Integratie

- **Eis** – Verkeer van en naar API's is mogelijk binnen het
  Haven-cluster. Daarnaast is inkomende en uitgaande integratie via
  **Federatieve Service Connectiviteit (FSC)** aantoonbaar werkend en
  gedocumenteerd. Hiervoor worden demonstratievoorzieningen beschikbaar
  gesteld in de demo-directory.

- **Eis** – De applicatie ondersteunt de [**Gateway
  API**](https://gateway-api.sigs.k8s.io), de opvolger van de Kubernetes
  Ingress API, zodat deze onafhankelijk is van de gebruikte
  ingress-implementatie (zoals Istio of Traefik).

#### Runtime

- **Eis** – De applicatie is **stateless** en kan volledig redundant
  worden uitgevoerd. Alle persistente gegevens worden opgeslagen in
  externe voorzieningen, zoals databases, caches, queues of
  objectopslag.

- **Eis** – De applicatie is bestand tegen verstoringen in afhankelijke
  systemen en voorkomt cascade- of domino-effecten wanneer componenten
  binnen de keten tijdelijk niet beschikbaar zijn.

- **Eis** – Monitoring-endpoints voor health, logging en metrics zijn
  beschikbaar zodat de operationele toestand van de applicatie continu
  kan worden bewaakt.

#### Observability

- **Eis** – Logs, traces en metrics worden beschikbaar gesteld via
  [**OpenTelemetry
  (OTel)**](https://opentelemetry.io/docs/what-is-opentelemetry/).

- **Wens** – Bij de applicatie worden standaard
  [**Grafana**](https://grafana.com)-dashboards en bijbehorende
  alert-definities meegeleverd.

#### Security

- **Eis** – De pod-definitie en applicatie voldoen aan de [**Kubernetes
  Pod Security Standards –
  Restricted**](https://kubernetes.io/docs/concepts/security/pod-security-standards/).

- **Eis** – Secrets worden niet in de applicatie of containerimage
  opgeslagen. Secret-referenties zijn configureerbaar via GitOps/Helm,
  zodat integratie met een centraal secretmanagementsysteem mogelijk is.

#### Applicatiearchitectuur

- **Eis** – De beheerinterface is logisch en technisch te scheiden van
  de gebruikersinterface en API, zodat deze op afzonderlijke endpoints
  of load balancers kan worden aangeboden.

- **Eis** – De applicatie voldoet zoveel mogelijk aan de principes van
  de [**Twelve-Factor App**](https://12factor.net). Afwijkingen zijn
  toegestaan, mits deze expliciet zijn gemotiveerd en gedocumenteerd.
