# 14. Aansluitvoorwaarden Platform Dienstverlening

| **Compact:** |
|----|
| Wie wil aansluiten op het Platform Dienstverlening krijgt een aantal voorwaarden. Dit hoofdstuk beschrijft wanneer en hoe oplossingen binnen Common Ground passen, welke eisen gelden voor platformservices en Patroon B, hoe softwarekwaliteit wordt geborgd en welke organisatorische voorwaarden gelden. |

## Handleiding bij de aansluitvoorwaarden

Voorafgaand aan een ontwikkeling (een doelarchitectuur, of
aanbesteding/vervanging van software) moet bepaald worden of deze binnen
de scope van Common Ground valt en, zo ja, welke aansluitvoorwaarden van
toepassing zijn. Hiervoor geldt het volgende onderscheid:

- Processen die uitsluitend de interne bedrijfsvoering ondersteunen,
  zoals bij HRM-, ERP- en financiële systemen, vallen in beginsel buiten
  de scope van Common Ground.

- Processen met een directe of indirecte relatie met gemeentelijke
  dienstverlening aan inwoners, ondernemers of organisaties, vallen
  binnen de scope van Common Ground. Het kan dus zowel gaan om een
  oplossing waarmee een inwoner, ondernemer of organisatie rechtstreeks
  contact heeft met de gemeente, als om een oplossing die onderdeel is
  van het achterliggende dienstverleningsproces. Dit gaat niet zuiver
  over het domein Dienstverlening, maar – potentieel – over oplossingen
  in alle domeinen.

Valt de oplossing binnen deze scope? Dan gelden de Common Ground
aansluitvoorwaarden.

<img
src="../media/media/image33.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

## Common Ground en Platform Dienstverlening

Het Platform Dienstverlening is de implementatie van Common Ground
binnen de G4-gemeenten. Het vormt de referentiearchitectuur voor de
gemeentelijke informatievoorziening en biedt een samenhangend geheel van
software (generieke registraties, dataservices, integratievoorzieningen
en procesapplicaties) waarmee de gemeentelijke dienstverlening op een
generieke manier kan worden gerealiseerd. Het volgt een <a href="https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/enterprisearchitectuur" target="_blank" rel="noopener noreferrer">Enterprise
architectuur</a>
en realiseert een ontkoppeld landschap van (micro)services volgens het
model van Common Ground:

<img
src="../media/media/image34.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Bij een nieuwe functionele behoefte (of een bestaande die ingevuld
wordt, maar waarvan de software niet langer voldoet of contractueel
eindigt) wordt eerst onderzocht of deze kan worden ingevuld met de
bestaande voorzieningen van het Platform Dienstverlening. Het platform
wordt maximaal benut voordat wordt besloten nieuwe software te
ontwikkelen of een SaaS-oplossing aan te schaffen. Dit proces volgt een
beslisboom waarin twee patronen worden onderscheiden, die hieronder
worden toegelicht.

<img
src="../media/media/image35.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Patroon A: Realisatie in Platform Dienstverlening

Er wordt eerst vastgesteld of de gevraagde functionaliteit reeds
beschikbaar is binnen het Platform Dienstverlening of met beperkte
uitbreiding van bestaande platformservices kan worden gerealiseerd.

Wanneer de benodigde functionaliteit nog niet beschikbaar is, wordt
beoordeeld of deze als nieuwe generieke platformservice kan worden
ontwikkeld en opgenomen in het Platform Dienstverlening. Daarbij wordt
onder meer gekeken naar de generieke toepasbaarheid, de bijdrage aan de
referentiearchitectuur, de verwachte herbruikbaarheid door meerdere
gemeenten en de aansluiting op de roadmap van het Platform
Dienstverlening.

Een platformservice wordt onderdeel van het Platform Dienstverlening
zelf. De component:

- Levert generieke functionaliteit;

- Wordt opgenomen in de platformarchitectuur;

- Valt onder de architectuurgovernance van het platform;

- Wordt gezamenlijk beheerd;

- Maakt onderdeel uit van de referentie-implementatie zoals die door G4
  wordt vastgesteld.

Voor platformservices gelden zowel de [(niet-)functionele
aansluitvoorwaarden Common Ground](README.md#aansluitvoorwaarden-patroon-b) als
[aanvullende platformeisen](README.md#aanvullende-eisen-voor-platformservices).

### Patroon B: Aansluiten van een (SaaS-)oplossing

Alleen wanneer ontwikkeling als platformservice niet doelmatig of
haalbaar is, bijvoorbeeld vanwege de complexiteit, beperkte generieke
toepasbaarheid, beschikbare ontwikkelcapaciteit of gewenste
implementatiesnelheid, wordt – tijdelijk – gekozen voor een
SaaS-oplossing. Het is van belang dat deze ontwikkeling wordt
geadresseerd bij de PO’s van het Platform, zodat parallel gewerkt wordt
aan doorontwikkeling en de capabilities beschikbaar komen.

Als gekozen wordt voor een SaaS-oplossing is het vereist dat deze
integreert met het Platform Dienstverlening. Dat betekent voldoen aan de
aansluitvoorwaarden van het Platform Dienstverlening en gebruik maken
van de generieke registraties, API's en integratievoorzieningen.

Een aangesloten applicatie blijft eigendom en verantwoordelijkheid van
de leverancier (of community) en maakt geen onderdeel uit van het
Platform Dienstverlening. De applicatie maakt gebruik van de generieke
voorzieningen van het platform, zoals registraties, dataservices, API's
en integratievoorzieningen. Het Platform biedt hier ruimte voor in de
vorm van generieke aansluitingen (“stekkers”) op de gegevenslaag.

<img
src="../media/media/image36.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Leveranciers en communities behouden vrijheid in de inrichting en
implementatie van hun software, voor zover de applicatie voldoet aan de
aansluitvoorwaarden van het Platform Dienstverlening.

## Aansluitvoorwaarden Patroon B 

Deze aansluitvoorwaarden zijn van toepassing op oplossingen die als
applicatie aansluiten op het Platform Dienstverlening (Common Ground).
Zij zijn aanvullend op de
<a href="https://vng.nl/sites/default/files/2026-03/gibit-2025-artikelen.pdf" target="_blank" rel="noopener noreferrer">GIBIT</a>.
Voor alle contractuele, juridische, organisatorische en generieke
kwaliteitseisen geldt de GIBIT, tenzij in deze aansluitvoorwaarden
aanvullende of afwijkende platformspecifieke eisen zijn opgenomen.

De aansluitvoorwaarden bevatten de functionele, niet-functionele en
technische eisen die waarborgen dat een oplossing op een uniforme,
veilige en beheerbare wijze samenwerkt met het Platform Dienstverlening.

### Gegevenslaag 

Het Platform Dienstverlening levert de generieke gegevenslaag van de
gemeentelijke informatievoorziening. Deze bestaat uit generieke
registraties, dataservices en de integratielaag voor veilige en
gestandaardiseerde gegevensuitwisseling. Procesapplicaties sluiten
hierop aan en maken voor het vastleggen, muteren en raadplegen van
gemeentelijke gegevens gebruik van deze generieke voorzieningen.

De gegevenslaag wordt gefaseerd uitgebreid. Uiteindelijk wordt het
volledige Gemeentelijk Gegevensmodel (GGM) hierin gerealiseerd.

Op dit moment zijn de volgende generieke registraties beschikbaar:

- Klanten (Partijen – inwoners en organisaties);

- Zaken;

- Documenten;

- Producten;

- Beslisregels;

- Objecten;

- Verzoeken, Taken en Berichten.

In ontwikkeling zijn registraties voor:

- De interne organisatie (teams, functies, rollen en medewerkers);

- Domeinspecifieke gegevensmodellen voor het Sociaal Domein
  (Participatie en Inburgering).

### Algemene eisen

Iedere aangesloten oplossing voldoet aan de volgende uitgangspunten voor
de gegevenslaag:

- **Eis** – Informatieobjecten die binnen het Platform Dienstverlening
  worden **opgevraagd,** **vastgelegd of gemuteerd**, volgen het
  gegevensmodel en de metadatering van de betreffende registratie.
  Hiermee wordt geborgd dat wordt voldaan aan de eisen voor duurzame
  toegankelijkheid, informatiebeheer en interoperabiliteit.

- **Eis** – Wanneer een oplossing verantwoordelijk is voor het
  **opvragen,** **vastleggen of muteren** van gegevens in een
  registratie, draagt zij er zorg voor dat deze registratie actueel,
  volledig en consistent blijft. De betreffende registratie blijft
  daarmee de authentieke bron van deze gegevens.

### Gebruik van generieke registraties

Wanneer een oplossing verantwoordelijk is voor het **opvragen,**
**vastleggen of muteren** van gegevens binnen één van de onderstaande
domeinen, maakt zij gebruik van de daarvoor aangewezen generieke
registratie of voorziening van het Platform Dienstverlening.

Bij de oplossing moet het interne informatiemodel logisch worden gemapt
naar de Common Ground-domeinen. Concreet betekent dit het aansluiten op
de volgende standaarden:

- **Klantgegevens** hebben als bron **OpenKlant** (Klantinteracties- en
  Contactgegevens API) (<a href="https://github.com/maykinmedia/open-klant" target="_blank" rel="noopener noreferrer">OpenKlant
  GitHub</a>).

- **(Instanties van) Producten en diensten** hebben als bron
  **OpenProduct** (<a href="https://github.com/maykinmedia/open-product" target="_blank" rel="noopener noreferrer">OpenProduct)
  GitHub</a>).

- **Zaken** hebben als bron **OpenZaak** (<a href="https://github.com/open-zaak/open-zaak" target="_blank" rel="noopener noreferrer">OpenZaak
  GitHub</a>)

  - **Onderdeel** daarvan is ook de **Documenten API**

- **Verzoeken**, **Taken** en **Berichten** hebben als bron **OpenVTB**
  en volgen respectievelijk het Verzoeken-, Taken- en Berichtenpatroon
  (<a href="https://github.com/maykinmedia/open-vtb" target="_blank" rel="noopener noreferrer">OpenVTB GitHub</a>).

De actuele documentatie en API-specificaties zijn beschikbaar via de
GitHub links.

#### Aansluitpatronen

Iedere aangesloten oplossing past de functionele en technische
aansluitpatronen toe zoals beschreven in de <a href="https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/enterprisearchitectuur" target="_blank" rel="noopener noreferrer">Enterprisearchitectuur
Platform
Dienstverlening</a>.
Deze patronen beschrijven de uniforme wijze waarop applicaties
samenwerken met registraties, API's en andere platformvoorzieningen.

#### Eisen

- **Eis –** Aangesloten oplossingen integreren met Keycloak via OpenID
  Connect (OIDC) zodat gebruikers van het platform zonder aanvullende
  authenticatiestappen toegang krijgen tot de aangesloten oplossing. 

- **Eis –** De oplossing past de functionele en technische
  aansluitpatronen toe zoals beschreven in de Enterprisearchitectuur
  Platform Dienstverlening.

- **Eis –** Gegevensuitwisseling tussen applicaties en registraties
  vindt plaats via de voorgeschreven API-, interactie- en eventpatronen
  van het Platform Dienstverlening.

- **Eis –** Bij het realiseren van nieuwe functionaliteit worden de
  architectuurprincipes en aansluitpatronen van het Platform
  Dienstverlening gevolgd.

#### Nieuwe registraties en versies

Het Platform Dienstverlening wordt continu doorontwikkeld. Leveranciers
worden geacht nieuwe generieke registraties en nieuwe versies van
bestaande registraties tijdig te ondersteunen, zodat aangesloten
applicaties compatibel blijven met de referentiearchitectuur.

- **Eis –** Wanneer binnen het Platform Dienstverlening een voor de
  oplossing relevante nieuwe generieke registratie of een nieuwe versie
  van een bestaande registratie de status **'In gebruik'** bereikt,
  ondersteunt de leverancier deze registratie uiterlijk zes maanden
  nadat deze status is bereikt.

#### Gebruik van brongegevens

Common Ground gaat uit van het principe **data bij de bron**. Gegevens
worden waar mogelijk rechtstreeks geraadpleegd vanuit de authentieke
registratie. Het structureel dupliceren van gegevens wordt zoveel
mogelijk voorkomen.

- **Wens –** Gegevens die via gestandaardiseerde API's realtime
  beschikbaar zijn vanuit een registratie of andere bronvoorziening
  worden niet structureel gekopieerd of structureel lokaal opgeslagen.
  Bij de uitvoering van een handeling in een afhandelcomponent worden de
  gegevens opgehaald uit de gegevenslaag en weer teruggeschreven in de
  gegevenslaag.

### Integratielaag

Naast de gegevenslaag maakt iedere aangesloten oplossing gebruik van de
generieke platformvoorzieningen voor gegevensuitwisseling,
observability, authenticatie en autorisatie.

- **Eis** – Communicatie met andere componenten verloopt via
  <a href="https://docs.open-fsc.nl/introduction" target="_blank" rel="noopener noreferrer">Federatieve Service Connectiviteit
  (FSC).</a>

- **Eis** – Gebeurtenissen worden geconsumeerd via **Open
  Notificaties**, conform het notificatiepatroon (<a href="https://github.com/open-zaak/open-notificaties" target="_blank" rel="noopener noreferrer">Open Notificaties
  GitHub</a>).

- **Eis** – Logging en telemetry volgen
  <a href="https://opentelemetry.io/docs/what-is-opentelemetry/" target="_blank" rel="noopener noreferrer">OpenTelemetry</a>.

#### Platformbrede voorzieningen

De onderstaande platformvoorzieningen bevinden zich nog in ontwikkeling.
Vanaf zes maanden nadat een voorziening de status **'In gebruik'** heeft
bereikt, gelden de volgende aanvullende aansluitvoorwaarden:

- <a href="https://vng-realisatie.github.io/ftv/" target="_blank" rel="noopener noreferrer">OpenFTV/AuthZEN</a> – Autorisatie
  maakt gebruik van de centrale voorziening voor federatieve
  authenticatie en autorisatie

- <a href="https://github.com/Logius-standaarden/logboek-dataverwerkingen" target="_blank" rel="noopener noreferrer">Logboek
  Dataverwerkingen</a>
  – De oplossing registreert gegevensverwerkingen via het centrale
  Logboek Dataverwerkingen.

## Aanvullende eisen voor platformservices

Een **platformservice (Categorie A)** maakt onderdeel uit van het
Platform Dienstverlening. In tegenstelling tot een aangesloten
applicatie wordt een platformservice opgenomen in de
referentiearchitectuur, valt deze onder de architectuurgovernance van
het platform en wordt zij gezamenlijk beheerd en doorontwikkeld.

<img
src="../media/media/image37.png"
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
worden gestuurd door de <a href="https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/enterprisearchitectuur" target="_blank" rel="noopener noreferrer">Enterprisearchitectuur Common Ground & Platform
Dienstverlening</a>.
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
  Dienstverlening.](../08-applicatiearchitectuur/README.md#architectuur-van-registraties)

- **Eis –** REST API's voldoen aan de <a href="https://logius-standaarden.github.io/API-Design-Rules/" target="_blank" rel="noopener noreferrer">REST API Design
  Rules</a>

- **Eis –**API's worden gespecificeerd conform de <a href="https://spec.openapis.org/oas/latest.html" target="_blank" rel="noopener noreferrer">OpenAPI Specification
  3.x</a>

- **Eis –** Eventgedreven integraties implementeren het <a href="https://www.gemmaonline.nl/wiki/De_CloudEvents_standaard" target="_blank" rel="noopener noreferrer">CloudEvents
  NL-profiel</a>

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
  <a href="https://openid.net/developers/how-connect-works/" target="_blank" rel="noopener noreferrer">(OIDC)</a>**. De
  applicatie ondersteunt iedere OIDC-conforme Identity Provider en mag
  geen afhankelijkheid hebben van een specifieke implementatie, zoals
  Keycloak.

#### Integratie

- **Eis** – Verkeer van en naar API's is mogelijk binnen het
  Haven-cluster. Daarnaast is inkomende en uitgaande integratie via
  **Federatieve Service Connectiviteit (FSC)** aantoonbaar werkend en
  gedocumenteerd. Hiervoor worden demonstratievoorzieningen beschikbaar
  gesteld in de demo-directory.

- **Eis** – De applicatie ondersteunt de <a href="https://gateway-api.sigs.k8s.io" target="_blank" rel="noopener noreferrer">**Gateway
  API**</a>, de opvolger van de Kubernetes
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
  <a href="https://opentelemetry.io/docs/what-is-opentelemetry/" target="_blank" rel="noopener noreferrer">**OpenTelemetry
  (OTel)**</a>.

- **Wens** – Bij de applicatie worden standaard
  <a href="https://grafana.com" target="_blank" rel="noopener noreferrer">**Grafana**</a>-dashboards en bijbehorende
  alert-definities meegeleverd.

#### Security

- **Eis** – De pod-definitie en applicatie voldoen aan de <a href="https://kubernetes.io/docs/concepts/security/pod-security-standards/" target="_blank" rel="noopener noreferrer">**Kubernetes
  Pod Security Standards –
  Restricted**</a>.

- **Eis** – Secrets worden niet in de applicatie of containerimage
  opgeslagen. Secret-referenties zijn configureerbaar via GitOps/Helm,
  zodat integratie met een centraal secretmanagementsysteem mogelijk is.

#### Applicatiearchitectuur

- **Eis** – De beheerinterface is logisch en technisch te scheiden van
  de gebruikersinterface en API, zodat deze op afzonderlijke endpoints
  of load balancers kan worden aangeboden.

- **Eis** – De applicatie voldoet zoveel mogelijk aan de principes van
  de <a href="https://12factor.net" target="_blank" rel="noopener noreferrer">**Twelve-Factor App**</a>. Afwijkingen zijn
  toegestaan, mits deze expliciet zijn gemotiveerd en gedocumenteerd.

## Kwaliteitsborging van de softwareontwikkeling

Dit onderdeel beschrijft de eisen die worden gesteld aan het
ontwikkelproces van platformservices. Deze hebben onder meer betrekking
op softwarekwaliteit, documentatie, testautomatisering, en gebruik van
AI. Niet alleen het eindproduct moet van hoge kwaliteit zijn, ook het
ontwikkelproces moet transparant, overdraagbaar en reproduceerbaar zijn.

De algemene eisen ten aanzien van softwareontwikkeling, kwaliteit,
beveiliging, documentatie, testen, acceptatie en onderhoud zijn
opgenomen in de
<a href="https://vng.nl/sites/default/files/2026-03/gibit-2025-artikelen.pdf" target="_blank" rel="noopener noreferrer">GIBIT</a>.
De onderstaande bepalingen vormen daarop een aanvulling en gelden
specifiek voor software die onderdeel uitmaakt van het Platform
Dienstverlening.

#### Principes

- **Leverancier is verantwoordelijk.** De leverancier is
  eindverantwoordelijk voor de kwaliteit van de opgeleverde software,
  ongeacht de inzet van AI.

- **Menselijke beoordeling is verplicht.** Alle opgeleverde software
  wordt beoordeeld door voldoende gekwalificeerde ontwikkelaars.
  AI-output wordt nooit zonder review geaccepteerd.

- **Kwaliteit boven metrics.** Kwaliteit wordt vastgesteld op basis van
  onderhoudbaarheid, beveiliging, architectuur, testbaarheid en naleving
  van afspraken. Geautomatiseerde analyses ondersteunen dit, maar
  vervangen geen inhoudelijke review.

- **Passende technologie.** De gekozen programmeertaal, frameworks en
  architectuur moeten aantoonbaar passend zijn voor de functionele en
  niet-functionele eisen van de oplossing.

- **Onderhoudbaarheid staat centraal.** Software moet begrijpelijk,
  overdraagbaar en duurzaam onderhoudbaar zijn gedurende de gehele
  levenscyclus.

#### Verplichtingen voor de leverancier

Onverminderd de verplichtingen uit de GIBIT toont de leverancier
aanvullend aan dat:

- De opgeleverde software aantoonbaar is gereviewd door ervaren
  ontwikkelaars; dit kan onderbouwd worden met gedocumenteerde Pull
  Requests gereviewed door ervaren ontwikkelaars;

- De gekozen architectuur, programmeertaal en gebruikte technologie
  passend zijn voor de oplossing;

- Beveiliging, testbaarheid en onderhoudbaarheid onderdeel zijn van het
  ontwikkelproces;

- Eventuele inzet van AI niet afdoet aan de kwaliteit of
  verantwoordelijkheid voor het eindproduct;

- De software zodanig is gedocumenteerd dat beheer en doorontwikkeling
  door een opvolgende partij mogelijk zijn;

- Het is verplicht om AI-gebruik aan te geven; in dat geval wordt
  vastgelegd:

  - Welke AI-middelen zijn gebruikt en waarvoor;

  - Op welke onderdelen AI een wezenlijke bijdrage heeft geleverd;

  - Welke menselijke reviews en controles zijn uitgevoerd, bij
    realisatie van functionaliteit, en routine-/procesmatige checks;

  - Indien gebruik is gemaakt van agentic AI of vergelijkbare autonome
    ontwikkelprocessen: de gebruikte prompts, instructies, guardrails,
    beslisregels en werkwijze, voor zover deze noodzakelijk zijn om de
    software te begrijpen, reproduceren en onderhouden. Deze informatie
    maakt onderdeel uit van de architectuur- en projectdocumentatie en
    wordt samen met de broncode in de repository opgeleverd.

#### Toelatingsvoorwaarde/Borging van compliance

Het voldoen aan deze richtlijn is een voorwaarde voor ingebruikname van
software door gemeenten en voor opname van software in het Platform
Dienstverlening. De leverancier toont voorafgaand aan oplevering aan dat
aan de gestelde eisen is voldaan en levert de hiervoor benodigde
documentatie, reviewresultaten en architectuurartefacten aan.

#### Richtlijn toetsing

De toetsing richt zich niet uitsluitend op de kwaliteit van de broncode,
maar ook op de professionaliteit en beheersbaarheid van het
softwareontwikkelproces. Binnen de governance van het Platformmanagement
is een toetsingscommissie ingericht; deze organiseert deze beoordeling
samen met leveranciers, softwarespecialisten en architecten.

Bij de beoordeling wordt vastgesteld of de leverancier kan aantonen dat:

- Architectuur- en technologiekeuzes navolgbaar zijn onderbouwd;

- Softwareontwikkeling plaatsvindt volgens aantoonbare kwaliteits- en
  reviewprocessen;

- Beheer, doorontwikkeling en overdracht aan een andere partij voldoende
  zijn geborgd;

- Documentatie, deployment-instructies en architectuurartefacten actueel
  beschikbaar zijn;

- De inzet van AI, indien van toepassing, transparant is vastgelegd en
  onder menselijke verantwoordelijkheid plaatsvindt.

De toetsing kan worden ondersteund door steekproeven op pull requests,
architectuurreviews, reproduceerbaarheidstesten, kwaliteitsrapportages
en securityscans. Hierbij staat centraal of de leverancier aantoonbaar
werkt volgens professioneel software-engineering- en beheerproces, en
niet uitsluitend of het eindproduct functioneel voldoet.

Geautomatiseerde kwaliteitsmetingen en securityscans kunnen hierbij
worden gebruikt als ondersteunend bewijs, aangevuld met een inhoudelijke
beoordeling door architecten en/of senior softwareontwikkelaars,
bijvoorbeeld van andere softwarepartners. Bij onvoldoende onderbouwing
of kwaliteit kan de software niet worden geaccepteerd of opgenomen
totdat de geconstateerde tekortkomingen zijn hersteld.

## Organisatorische aansluitvoorwaarden

Organisatorische aansluitvoorwaarden beschrijven de eisen die worden
gesteld aan de wijze waarop een leverancier of ontwikkelorganisatie
participeert binnen het Platform Dienstverlening. Hieronder vallen onder
meer afspraken over Open Source-licenties, samenwerking binnen de
community, governance, bijdrage aan de referentie-implementatie en
naleving van de geldende Code of Conduct.

### Samenwerking

Platformservices maken onderdeel uit van een gezamenlijk ontwikkeld
platform. Nieuwe functionaliteit wordt niet geïsoleerd ontwikkeld, maar
afgestemd op de gezamenlijke architectuur, roadmap en
ontwikkelprioriteiten.

De ontwikkeling van het Platform Dienstverlening wordt aangestuurd door
de gezamenlijke Lead Product Owners (LPO's). Zij zijn verantwoordelijk
voor de prioritering van ontwikkelingen, de gezamenlijke roadmap en de
inrichting van de backlog. Leveranciers stemmen de ontwikkeling van
platformservices af met de verantwoordelijke Lead Product Owner en
houden rekening met de gezamenlijke planning en afhankelijkheden binnen
het platform.

**Eisen**

- **Eis** – Nieuwe functionaliteit wordt afgestemd met de
  verantwoordelijke Lead Product Owner voordat met ontwikkeling wordt
  gestart.

- **Eis** – Functionele uitbreidingen en architectuurwijzigingen worden
  ingebracht via de gezamenlijke backlog van het Platform
  Dienstverlening.

- **Eis** – Ontwikkeling van platformservices sluit aan op de
  gezamenlijke roadmap en de prioriteiten van het Platformmanagement.

- **Eis** – Wijzigingen met impact op de architectuur of op andere
  platformservices worden vooraf afgestemd met de Technische Stuurgroep
  en het Platformmanagement.

- **Eis** – Leveranciers werken transparant samen met gemeenten en
  andere leveranciers en delen relevante ontwerpkeuzes, planning en
  voortgang voor zover deze betrekking hebben op de gezamenlijke
  ontwikkeling van het platform.

### Open Source

#### Uitgangspunt

Alle generieke software die binnen het Platform Dienstverlening wordt
ontwikkeld of waarvan de ontwikkeling geheel of gedeeltelijk uit
publieke middelen wordt gefinancierd, wordt als **Open Source**
beschikbaar gesteld. De algemene bepalingen met betrekking tot Open
Source zijn opgenomen in hoofdstuk 15 van de GIBIT. De onderstaande
bepalingen vormen daarop een aanvulling voor software die onderdeel
uitmaakt van het Platform Dienstverlening.

#### Implicaties

Dit uitgangspunt stelt de volgende eisen:

- **Eis** – De broncode wordt beheerd in een publiek toegankelijk
  versiebeheersysteem op basis van Git.

- **Eis** – De volledige ontwikkelhistorie, inclusief issues,
  wijzigingen en pull requests, is inzichtelijk, tenzij zwaarwegende
  redenen anders vereisen.

- **Eis** – De software wordt gepubliceerd onder de **European Union
  Public Licence (EUPL)**

- **Eis** – Het intellectueel eigendom wordt zodanig georganiseerd dat
  continuïteit, gezamenlijk beheer en overdraagbaarheid van de software
  zijn gewaarborgd.

- **Eis** – De leverancier levert wijzigingen en verbeteringen terug aan
  de oorspronkelijke Open Source-community (*upstream first*)

- **Eis** – De build-, test- en deploymentconfiguratie maken integraal
  onderdeel uit van de broncode, zodat de software reproduceerbaar kan
  worden gebouwd en uitgerold.

### Code of Conduct

Naast de technische en architectonische eisen gelden voor
platformservices ook organisatorische uitgangspunten die bijdragen aan
een duurzame samenwerking binnen het Platform Dienstverlening. Deze
uitgangspunten hebben betrekking op samenwerking, governance,
transparantie, gezamenlijke verantwoordelijkheid en de wijze waarop
gemeenten en leveranciers deelnemen aan het platform.

Ter ondersteuning hiervan wordt momenteel een **Code of Conduct (CoC)**
ontwikkeld voor zowel gemeenten als leveranciers. Deze Code of Conduct
is gebaseerd op de eerder vastgestelde samenwerkingsprincipes en
beschrijft de wederzijdse verwachtingen en afspraken voor deelname aan
het Platform Dienstverlening. De CoC verduidelijkt:

- Het doel van de samenwerking;

- De doelgroep waarvoor de Code of Conduct is bedoeld;

- Wat van deelnemers wordt verwacht;

- Waaraan deelnemers zich committeren;

- De samenhang met het afsprakenstelsel van het Platform
  Dienstverlening.

Na vaststelling maakt de Code of Conduct integraal onderdeel uit van de
organisatorische aansluitvoorwaarden van het Platform Dienstverlening.
