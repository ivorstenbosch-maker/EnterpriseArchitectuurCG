# Architectuur van registraties

Registraties vormen de basis van de gegevensvoorziening binnen het
Platform Dienstverlening. Een registratie is een zelfstandige
softwarecomponent die verantwoordelijk is voor het duurzaam vastleggen,
beheren en beschikbaar stellen van gegevens over een afgebakend domein
of objecttype.

Registraties realiseren de informatiekundige uitgangspunten uit de
informatie- en data-architectuur, waaronder **data bij de bron**,
**data-autonomie** en **duurzame toegankelijkheid**. Zij vormen de
authentieke bron voor de gegevens waarvoor zij verantwoordelijk zijn en
zijn onafhankelijk van de processen waarin deze gegevens worden
gebruikt.

Binnen de applicatiearchitectuur bestaat een registratie uit twee
logisch gescheiden onderdelen:

- De **registratie**, waarin gegevens duurzaam worden beheerd;

- De **dataservice (API)** waarmee deze gegevens gestandaardiseerd
  beschikbaar worden gesteld.

  <img
  src="../../media/media/image27.png"
  style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Processen communiceren uitsluitend met de dataservice; de registratie
blijft verantwoordelijk voor de kwaliteit, integriteit en historie van
de gegevens.

### Referentiearchitectuur van een registratie

Hoewel registraties verschillende gegevens beheren, volgen zij binnen
het Platform Dienstverlening dezelfde referentiearchitectuur. Een
registratie is een zelfstandige softwarecomponent die bestaat uit een
**registratie** (laag 1) en een **dataservice** (laag 2).

De **registratie** bestaat uit:

- **State**

  - De actuele en historische toestand van de geregistreerde gegevens.
    Iedere wijziging resulteert in een nieuwe state, waardoor zowel de
    actuele situatie als de formele en materiële historie behouden
    blijven.

- **Events**

  - Iedere betekenisvolle wijziging wordt vastgelegd als gebeurtenis.
    Events beschrijven welke handeling heeft plaatsgevonden en vormen de
    basis voor notificaties, auditing en herleidbaarheid.

- **Metadata**

  - Bij iedere registratie en gebeurtenis wordt context vastgelegd,
    zoals bron, actor, tijdstip, aanleiding, doelbinding en
    betrouwbaarheid. Hiermee wordt invulling gegeven aan
    verwerkingsverantwoording en de beoordeling van de kwaliteit en
    herkomst van gegevens.

    De **dataservice (API)** vormt de gestandaardiseerde toegang tot de
    registratie. Naast het raadplegen van gegevens biedt zij
    handelingsgedreven API-acties voor betekenisvolle mutaties op de
    registratie. Iedere API-actie valideert de handeling, autoriseert de
    uitvoering, legt de bijbehorende gebeurtenis en metadata vast,
    creëert indien nodig een nieuwe state en publiceert notificaties. De
    architectuur van deze API's wordt verder uitgewerkt in [Architectuur
    van API's](../11-architectuur-van-api-s/README.md#architectuur-van-apis).

    <img
    src="../../media/media/image28.png"
    style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Functionele eisen aan registraties

Om gegevens duurzaam, betrouwbaar en herbruikbaar beschikbaar te
stellen, moeten alle registraties binnen het Platform Dienstverlening
aan dezelfde functionele eisen voldoen:

#### Enkelvoudige bron en standaardisatie

Registraties:

- Vormen de enige bron voor de gegevens waarvoor zij verantwoordelijk
  zijn.

- Leggen gegevens eenduidig en gestandaardiseerd vast.

- Voorzien ieder object van een unieke identiteit.

#### Betrouwbaarheid

Registraties:

- Leggen iedere wijziging duurzaam vast.

- Ondersteunen volledige historie en reproduceerbaarheid.

- Maken de herkomst van gegevens inzichtelijk.

- Borgen de integriteit en consistentie van gegevens.

#### Herbruikbaarheid

Registraties:

- Ondersteunen meerdere BusinessServices.

- Zijn onafhankelijk van processen en gebruikersinterfaces.

- Voorkomen duplicatie van gegevens.

- Stellen gegevens op uniforme wijze beschikbaar.

#### Interoperabiliteit

Registraties moeten:

- Beschikken over één generieke en gestandaardiseerde aansluitingsvorm

- Zowel protocollair (bijv. API-standaarden, eventformaten) als qua type
  aanroep (raadplegen, muteren, events) uniform zijn

- Volgen de vastgestelde semantische en technische standaarden van het
  platform.

- Aansluiten op de integratiestandaarden van het platform (o.a. via
  FSC), zodat services in de proces- en interactielaag (laag 4/5) zonder
  maatwerk kunnen koppelen.

### Betrouwbare registratie

Een registratie moet niet alleen gegevens opslaan, maar ook aantoonbaar
kunnen verantwoorden wat is geregistreerd, wanneer, door wie, op basis
van welke grondslag en hoe een registratie zich in de tijd heeft
ontwikkeld. Betrouwbare registraties zijn essentieel voor rechtmatige
besluitvorming, transparante dienstverlening, toezicht, auditing en het
duurzaam gebruik van gegevens binnen de overheid.

Het project [**Uit Betrouwbare Bron
(UBB)**](https://uitbetrouwbarebron.rijks.app/handreiking-respec/)
beschrijft de eigenschappen waaraan overheidsregistraties moeten voldoen
om als betrouwbare bron te kunnen functioneren. UBB biedt hiervoor een
referentiemodel met uitgangspunten voor onder meer historie,
herleidbaarheid, verwerkingsverantwoording, betrouwbaarheid en de
context van registraties.

De registratiearchitectuur sluit aan bij deze uitgangspunten. De
verschillende UBB-concepten worden niet als afzonderlijke administraties
geïmplementeerd, maar gerealiseerd door de samenhang tussen
**handelingsgedreven API-acties**, **events**, **states** en
**metadata**.

#### Handelingsgedreven API-acties

Mutaties op een registratie vinden plaats via expliciete, betekenisvolle
API-acties. Iedere handeling resulteert in een gecontroleerde wijziging
van de registratie en legt de bijbehorende gebeurtenis en metadata vast.

Voorbeelden van gestandaardiseerde handelingen zijn:

- **Registreren** (aanmaken van een nieuw object);

- **Wijzigen** (actualiseren van gegevens);

- **Corrigeren** (herstellen van onjuiste gegevens zonder verlies van
  historie);

- **Herzien** (herstellen van één of meer historische states);

- **Ongedaan maken** (terugdraaien van een eerder uitgevoerde
  handeling);

- **Archiveren** (overbrengen naar een e-depot of vernietiging).

Deze API-acties vormen de technische invulling van betekenisvolle
domeinhandelingen en sluiten aan op de handelingsgedreven
API-architectuur zoals beschreven in [Architectuur van
API's](../11-architectuur-van-api-s/README.md#architectuur-van-apis).

#### Historie en reproduceerbaarheid

Doordat iedere wijziging resulteert in een nieuwe state en een
bijbehorend event, kunnen historische situaties volledig worden
gereconstrueerd. Hiermee wordt inzichtelijk welke gegevens op een
bepaald moment geldig waren en welke handelingen daartoe hebben geleid.

#### Verwerkingsverantwoording

Iedere wijziging legt vast:

- Welke handeling is uitgevoerd;

- Welke gegevens zijn gewijzigd;

- Door welke actor;

- Op welk moment;

- Op basis van welke aanleiding en grondslag.

#### Betrouwbaarheid en herkomst

Metadata leggen aanvullende informatie vast over de kwaliteit en
herkomst van gegevens, waaronder:

- De bron.

- De onderzoekstatus.

- De betrouwbaarheid of het zekerheidsniveau.

- De aanleiding van registratie.

Hierdoor kan niet alleen worden vastgesteld *wat* is geregistreerd, maar
ook *hoe betrouwbaar* die informatie op een bepaald moment werd geacht.

#### Leveringen en notificaties

Gegevens worden beschikbaar gesteld via gestandaardiseerde dataservices
en notificaties. Leveringen zijn projecties op de onderliggende
registratie; de registratie houdt daarom geen afzonderlijke
leveringenadministratie bij. Hierdoor kunnen dezelfde gegevens vanuit
verschillende perspectieven worden ontsloten zonder duplicatie van
informatie.

### Datamodelleringseisen

Een betrouwbare registratie begint bij een eenduidig informatiemodel.
Alleen wanneer objecten, eigenschappen en relaties op een consistente
wijze zijn gemodelleerd, kunnen gegevens betrouwbaar worden
uitgewisseld, hergebruikt en geïnterpreteerd door verschillende
processen, applicaties en organisaties. Datamodellering vormt daarmee de
basis voor interoperabiliteit, semantische consistentie en duurzame
gegevensuitwisseling.

Binnen het Platform Dienstverlening wordt waar mogelijk aangesloten op
het [**Metamodel Informatie Modellering
(MIM)**](https://docs.geostandaarden.nl/mim/mim/), de landelijke
standaard voor het modelleren van informatiemodellen binnen de overheid.
MIM biedt een uniforme manier om objecttypen, attributen, relaties,
begrippen en regels vast te leggen, waardoor informatiemodellen
onderling vergelijkbaar, uitwisselbaar en herbruikbaar worden.

Voor elke registratie moet een datamodel worden opgesteld dat zich
conformeert aan het MIM**:**

- Het informatiemodel beschrijft primair de werkelijkheid (objecten,
  eigenschappen en relaties) en niet de technische implementatie.
  Technische structuren zoals tabellen, JSON of API’s zijn een afgeleide
  van dit model.

<!-- -->

- Data wordt gemodelleerd in termen van objecttypen, attribuutsoorten en
  relaties. Data-objecten in registraties corresponderen met
  objecttypen; attributen en relaties worden expliciet en betekenisvol
  vastgelegd.

- Relaties tussen objecten worden expliciet gemodelleerd als onderdeel
  van het informatiemodel en niet alleen impliciet via technische
  koppelingen zoals foreign keys.

- Alle modelelementen (objecttypen, attributen, relaties) hebben een
  eenduidige naam en een formele definitie. Deze definities zijn leidend
  voor de interpretatie van de gegevens.

- Het datamodel wordt uitgewerkt op meerdere niveaus:

  - Een conceptueel model (betekenis en samenhang)

  - Een logisch model (structuur van gegevens)

  <!-- -->

  - Een fysiek/technisch datamodel (implementatie).

Modellering start op conceptueel niveau en wordt daarna pas technisch
uitgewerkt.

- De **semantiek (betekenis van begrippen)** wordt expliciet vastgelegd
  en is niet alleen af te leiden uit veldnamen of technische structuren.
  Waar mogelijk wordt aangesloten op een begrippenkader.

- **Constraints en validatieregels** maken onderdeel uit van het
  datamodel. Dit betreft zowel structurele regels (zoals cardinaliteit
  en verplichtheid) als inhoudelijke regels. Deze worden niet
  uitsluitend in applicatielogica geïmplementeerd.

- Het datamodel is **technologie-onafhankelijk opgesteld**. Keuzes voor
  databases, datastructuren of uitwisselingsformaten beïnvloeden het
  model niet, maar volgen eruit.

- Het model is ingericht op **interoperabiliteit en herbruikbaarheid**.
  Dit betekent dat het model begrijpelijk en toepasbaar moet zijn buiten
  de context van één specifieke registratie of implementatie.

- Het datamodel moet **zelfstandig interpreteerbaar** zijn, zonder
  afhankelijkheid van kennis van de technische implementatie of
  applicatielogica.

Deze uitgangspunten zorgen ervoor dat datamodellen binnen registraties
consistent, uitwisselbaar en duurzaam toepasbaar zijn binnen het
Platform.
