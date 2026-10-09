# 1. Over dit document

| **Compact:** |
|----|
| Dit hoofdstuk legt uit wat dit document is, waarom het bestaat en hoe je het moet lezen. Het is de gezamenlijke enterprise-architectuur voor het Platform Dienstverlening van de G4 en geeft richting aan de ontwikkeling van generieke voorzieningen binnen Common Ground. De architectuur volgt de TOGAF-werkwijze en verbindt business, informatie, applicaties en techniek. Ook wordt afgebakend wat dit document wel en niet pretendeert te zijn. |

Het Statement of Architecture Work vormt de formele opdracht voor de
architectuurontwikkeling. Het beschrijft de aanleiding, doelstelling,
scope, werkwijze, betrokken partijen en de verwachte
architectuurproducten.

De Enterprisearchitectuur beschrijft de gezamenlijke architectuur voor
het Platform Dienstverlening zoals ontwikkeld door de G4-gemeenten
(Amsterdam, Den Haag, Rotterdam en Utrecht). Zij vormt het
richtinggevende kader voor de ontwikkeling van generieke voorzieningen
binnen Common Ground en ondersteunt besluitvorming over de verdere
ontwikkeling van het platform.

## Relatie met andere architecturen

Deze architectuur staat niet op zichzelf, maar is een specialisatie van
een reeks landelijke en sectorale kaders. Dit zijn de belangrijkste, zie
verder het hoofdstuk [Samenhang met andere
ontwikkelingen](../04-samenhang-met-andere-ontwikkelingen/README.md#samenhang-met-andere-ontwikkelingen).

| **Kader** | **Niveau** | **Kernbijdrage aan de architectuur** |
|----|----|----|
| [NORA](https://www.noraonline.nl/wiki/Nederlandse_Overheid_Referentie_Architectuur_(NORA)) | Landelijk | Overheidsbrede kernwaarden en kwaliteitsdoelen; basis voor alle onderliggende kaders. |
| [GDI Domeinarchitectuur](https://open.overheid.nl/documenten/2496672b-3d8b-4894-818f-abaaced60d5f/file) | Landelijk | Interactiedoelen en capabilities (vermogens die de overheid moet bezitten, ontwikkelen of versterken) om de beleidsdoelen te realiseren, vastgesteld door de Architectuurraad Digitale Overheid. |
| [GEMMA](https://www.gemmaonline.nl/wiki/Hoofdpagina) | Gemeentelijk (landelijk) | Gemeentelijke referentiearchitectuur en vertaling van NORA/GDI-principes, incl. Omnichannel-referentiearchitectuur. |

## Opdracht en opdrachtgever

Deze Enterprisearchitectuur is opgesteld in opdracht van de
programmamanagers Common Ground van de G4.

De opdracht is het ontwikkelen van een gezamenlijke
Enterprisearchitectuur die:

- Richting geeft aan de gezamenlijke ontwikkeling van het Platform
  Dienstverlening;

- Een gemeenschappelijk referentiekader biedt voor architecten,
  ontwikkelteams en leveranciers;

- De samenhang beschrijft tussen business-, informatie-, applicatie- en
  technische architectuur;

- Aansluit bij de Nederlandse Digitaliseringsstrategie.

## Werkwijze

De opbouw van deze Enterprisearchitectuur volgt de **TOGAF® Architecture
Development Method (ADM)**.

<img
src="../media/media/image1.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

[TOGAF](https://www.opengroup.org/togaf) is een internationaal erkende
methode voor het ontwikkelen en beheren van enterprise-architecturen. De
kern van TOGAF wordt gevormd door de [**Architecture Development Method
(ADM)**](http://www.togaf.com/admref/_welcome.html): een iteratief
proces waarmee organisaties op gestructureerde wijze architecturen
ontwikkelen, implementeren en beheren.

De ADM onderscheidt opeenvolgende architectuurfasen, waaronder:

- Architecture Vision;

- Business Architecture;

- Information Systems Architecture (informatie- en
  applicatiearchitectuur);

- Technology Architecture;

- Opportunities & Solutions;

- Migration Planning;

- Implementation Governance;

- Architecture Change Management.

De fasen bouwen logisch op elkaar voort. De Architecture Vision bepaalt
de strategische richting en vormt het uitgangspunt voor de uitwerking
van de business-, informatie-, applicatie- en technische architectuur.
Vanuit deze architectuurdomeinen worden implementatiemogelijkheden,
migratie en governance uitgewerkt. Tijdens de realisatie kunnen nieuwe
inzichten ontstaan die aanleiding geven om eerdere architectuurkeuzes te
heroverwegen of verder te verfijnen.

De ADM is daarmee geen lineair proces, maar een iteratieve methode
waarin de verschillende architectuurdomeinen elkaar voortdurend
beïnvloeden. Ontwikkeling, implementatie en wijzigingsbeheer vormen een
doorlopende cyclus, zodat de architectuur kan meebewegen met
veranderende wetgeving, bestuurlijke prioriteiten, technologische
ontwikkelingen en voortschrijdend inzicht.

Deze Enterprisearchitectuur volgt deze logische opbouw. Niet iedere
ADM-fase resulteert in een afzonderlijk hoofdstuk, maar de structuur van
dit document sluit aan op de opeenvolgende architectuurdomeinen zoals
TOGAF die onderscheidt. Hierdoor is de architectuur systematisch
opgebouwd, zijn ontwerpkeuzes herleidbaar tot de oorspronkelijke
doelstellingen en biedt het document een consistente basis voor zowel
doorontwikkeling als implementatie.

Deze Enterprise architectuur is een product met een organisatiebrede
scope. Het geeft kaders en richtlijnen voor het platform. Het platform
wordt uitgewerkt aan de hand van visie. Op basis hiervan worden de
leidende specifieke principes beschreven. De gewenste inrichting (op
hoofdlijnen) wordt beschreven in een aantal modellen, zowel voor de
businesskant als voor software en infrastructuur op de volgende
dimensies:

- **Breedte**: de scope van de architectuur, gericht op samenhang,
  consistentie en herbruikbaarheid van principes, patronen en
  componenten.

- **Diepte**: verdieping (tot detailniveau) van de architectuur tot
  concrete implementaties. Dit laat zien hoe abstracte keuzes vertaald
  worden naar operationele oplossingen.

- **Tijd**: de ontwikkeling en roadmap van de architectuur, inclusief de
  gewenste situatie op termijn en beslissingsprocessen; op dit vlak
  wordt deels verwezen naar externe bronnen waar de actuele backlog en
  roadmap is vastgelegd.

  <img
  src="../media/media/image2.png"
  style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
  alt="Afbeelding met tekst, schermopname, diagram, lijn Door AI gegenereerde inhoud is mogelijk onjuist." />

Waar mogelijk sluit deze architectuur expliciet aan bij relevante
standaarden voor gegevensuitwisseling en modellering. In gevallen waar
deze aansluiting niet expliciet is uitgewerkt, kan worden aangenomen dat
nadere concretisering plaatsvindt binnen implementaties of
vervolgarchitectuur.

## Leeswijzer

Dit document is bedoeld voor verschillende doelgroepen. Afhankelijk van
de rol van de lezer zijn niet alle hoofdstukken even relevant.

Bij grote hoofdstukken zijn korte abstracts toegevoegd voor wie geen
tijd of zin heeft om de hele tekst te lezen, zodat in ieder geval
duidelijk is wat de hoofdgedachte en relevantie van het onderdeel is.

| **Doelgroep** | **Aanbevolen hoofdstukken** |
|----|----|
| **Bestuurders, opdrachtgevers en programmamanagers** | Managementsamenvatting, hoofdstuk 2 t/m 5. Deze hoofdstukken beschrijven de aanleiding, strategische doelen, architectuurvisie, uitgangspunten, governance en scope van het Platform Dienstverlening. Daarnaast is in het bijzonder paragraaf **6.7. Implicaties voor de bestaande organisatie** relevant. |
| **Enterprise- en domeinarchitecten** | Het volledige document. De architectuur is opgebouwd volgens de TOGAF Architecture Development Method (ADM) en beschrijft de samenhang tussen business-, informatie-, applicatie- en technische architectuur. |
| **Solution- en softwarearchitecten** | Hoofdstuk 4 t/m 14. Deze hoofdstukken beschrijven de architectuurprincipes, architectuurpatronen, bouwstenen, API's, technische architectuur en implementatiepatronen. |
| **Ontwikkelteams en leveranciers** | Hoofdstuk 5 t/m 14. Deze hoofdstukken bevatten de architectuurkaders voor de ontwikkeling van businessanalyse, softwarecomponenten, registraties, API's, infrastructuur en technische implementaties. |
| **Projectleiders en implementatiemanagers** | Hoofdstuk 4, 5, 6, 8, 9, 13 en 14. Deze hoofdstukken beschrijven de architectuurkaders waarbinnen implementatieprojecten worden uitgevoerd en wijzigingen worden beheerd. |

### Leesvolgorde

Eerst worden aanleiding, doelstellingen en architectuurvisie beschreven.
Vervolgens worden de verschillende architectuurdomeinen uitgewerkt:
business-, informatie-, applicatie- en technologiearchitectuur. Het
document sluit af met implementatiepatronen, generieke bouwstenen en de
governance voor doorontwikkeling en wijzigingsbeheer. Hierdoor kan het
document zowel sequentieel als thematisch worden gebruikt, afhankelijk
van de informatiebehoefte van de lezer. Waar mogelijk is redundantie
voorkomen; op enkele plaatsen is bewust gekozen voor beperkte herhaling
om afzonderlijke hoofdstukken zelfstandig leesbaar en bruikbaar te
houden.

### Begrippenlijst

Waar mogelijk worden begrippen toegelicht op de plaats waar zij voor het
eerst worden geïntroduceerd of wordt verwezen naar de onderliggende
standaarden en referentiearchitecturen waarin de achterliggende
concepten en ontwerpkeuzes uitgebreider zijn beschreven.

Voor overige architectuur- en softwarebegrippen bestaat veel algemeen
beschikbare documentatie. Deze begrippenlijst beperkt zich daarom tot
termen die binnen het Platform Dienstverlening een specifieke betekenis
hebben:

#### Service (ook wel: component)

Een **service** is een zelfstandig softwarecomponent binnen het Platform
Dienstverlening met een duidelijk afgebakende verantwoordelijkheid.
Services communiceren uitsluitend via gestandaardiseerde API's en
notificaties en kunnen onafhankelijk worden ontwikkeld, uitgerold en
beheerd.

Binnen de architectuur worden de volgende typen services onderscheiden,
binnen een lagenmodel dat wordt toegelicht in [Het Vijf-lagen
model](../08-applicatiearchitectuur/README.md#het-vijf-lagen-model) (in het hoofdstuk
Applicatie-architectuur):

- **Interactieservice** – een service in **laag 5 (Interactie)** die de
  communicatie met inwoners, ondernemers of medewerkers ondersteunt,
  bijvoorbeeld via portalen, formulieren of werkvoorraadschermen.

- **Processervice** – een service in **laag 4 (Proces)** die processen
  orkestreert, beslisregels toepast, taken beheert en de voortgang van
  dienstverlening bewaakt.

- **Connectiviteitsservice** – een service in **laag 3
  (Connectiviteit)** die de communicatie tussen componenten faciliteert,
  bijvoorbeeld via notificaties, events of federatieve
  serviceconnectiviteit (FSC).

- **Dataservice** – een service in **laag 2 (Diensten)** die gegevens
  uit registraties ontsluit via gestandaardiseerde, handelingsgerichte
  API's en daarbij validatie, autorisatie en publicatie van
  gebeurtenissen verzorgt.

- **Registratie** – een service in **laag 1 (Registraties)** die
  verantwoordelijk is voor het duurzaam vastleggen, beheren en
  beschikbaar stellen van gegevens binnen een afgebakend domein. Ook
  wel: register. **Domein**registers zijn een specialisatie van
  registraties in de context van een domein.

  Dit kunnen *logische* of *fysieke* bouwblokken zijn; op zeker niveau
  zijn Registraties en Dataservices gecombineerd, net als interactie- en
  processervices.

- **BusinessService -** Een BusinessService omvat een logisch
  samenhangend geheel van gegevens, beslisregels, proceslogica en
  interactie rondom één businesscapaciteit. Zij verbindt de
  verschillende architectuurlagen: gegevens uit registraties, proces- en
  beslislogica, interactie met inwoners en medewerkers en de
  uiteindelijke vastlegging van resultaten. Hierdoor ontstaat een
  verzameling herbruikbare businesscapaciteiten die in verschillende
  processen en dynamisch kan worden toegepast.

## Grenzen en positionering van dit document

Om de leesbaarheid, focus en toepasbaarheid te waarborgen, is een aantal
onderwerpen bewust beperkt of buiten scope gelaten.

#### Roadmap

Dit document bevat geen uitgewerkte roadmap of gefaseerde
transitie-architecturen (plateaus). De reden hiervoor is dat de
ontwikkeling van het Platform Dienstverlening plaatsvindt binnen een
continu architecturaal proces, waarin:

- Prioritering en fasering worden bepaald via een gezamenlijke [backlog
  van
  G4](https://app.notion.com/p/platformvoordienstverlening/e9375da1960249bba23c49d038d3c888?v=2b078b5f4db4808da728000c21a96e11)
  en betrokken partners;

- Keuzes iteratief worden gemaakt op basis van voortschrijdend inzicht
  en implementatie-ervaring;

<!-- -->

- Architectuur en realisatie gelijktijdig evolueren.

#### Beheer, financiën

De inrichting van beheer, financiering en exploitatie is in deze versie
van de architectuur heel beperkt beschreven. Dit hangt samen met de
lopende ontwikkeling naar een landelijke beheer- en ontwikkelorganisatie
voor generieke voorzieningen binnen Common Ground. Waar relevant zijn
wel architectuurprincipes en randvoorwaarden opgenomen (zoals
containerisatie en portabiliteit), zodat toekomstige invulling
consistent kan plaatsvinden.

#### Informatie-architectuur (detailniveau)

De informatie-architectuur beschrijft principes, kaders en methodieken
(zoals MIM en begrippenkaders), maar bevat geen volledig uitgewerkte
domeinmodellen.

Dit is een keuze, omdat:

- Semantiek en datamodellen sterk domeinafhankelijk zijn;

- Modellering plaatsvindt binnen concrete implementaties en
  ontwikkelingen;

- Domain-Driven Design (DDD) wordt toegepast om modellen iteratief en
  contextspecifiek te ontwikkelen.

Het document biedt daarmee het raamwerk voor modellering, niet de
uitwerking ervan.

#### Security- en compliance-uitwerking

Beveiliging, privacy en compliance (zoals BIO, CBW, AI Act en AVG en
toekomstige regelgeving) zijn randvoorwaardelijk voor architectuur, maar
worden in dit document niet volledig uitgewerkt. In plaats daarvan zijn
relevante aspecten opgenomen binnen specifieke onderdelen (zoals
identificatie, autorisatie en omgang met persoonsgegevens). Dit is een
bewuste gap die in later stadium wordt ingevuld.

## Verantwoording en totstandkoming

#### In opdracht van

Programmamanagers Common Ground G4

#### Opgesteld door

Ilja Vorstenbosch

#### Dit document

Versie: 2.0 / oktober 2026

Dit architectuurdocument is opgesteld op basis van een iteratief
ontwerpproces waarin architectuur, praktijkervaring en bestuurlijke
afstemming samenkomen. De inhoud is tot stand gekomen in nauwe
samenwerking met de **Technische Stuurgroep** (architecten) en het
**Platformmanagement** (programmamanagers) van de samenwerking tussen G4
en Dimpact. Daarnaast zijn meerdere reviewrondes uitgevoerd met
architecten, informatieadviseurs en andere specialisten uit deelnemende
gemeenten. De beschreven architectuur weerspiegelt daarmee zowel de
gezamenlijke ontwerpkeuzes als de praktijkervaringen uit de
gemeentelijke uitvoering. Voor de redactionele ondersteuning bij het
opstellen van dit document is gedeeltelijk gebruikgemaakt van GPT-5. De
uiteindelijke tekst is door mensen vastgesteld en geverifieerd.

De opgenomen schema's, illustraties en infographics zijn gebaseerd op de
inhoud van dit document en dienen ter ondersteuning van de leesbaarheid
en communicatie. Een deel van deze afbeeldingen is met behulp van GPT-5
gegenereerd op basis van tekstuele beschrijvingen en vervolgens
redactioneel beoordeeld en waar nodig aangepast. De afbeeldingen zijn
bedoeld als informatieve visualisaties en bouwstenen voor presentaties
en communicatie richting verschillende doelgroepen; de tekst van dit
document is leidend.

Dit document is een levend architectuurproduct en maakt onderdeel uit
van de doorlopende architectuurgovernance van het Platform
Dienstverlening. Nieuwe inzichten uit ontwerp, implementatie,
gemeentelijke toepassing en bestuurlijke besluitvorming worden periodiek
verwerkt. Naar verwachting wordt het document **elk kwartaal tot
halfjaarlijks** geactualiseerd, of eerder wanneer belangrijke
ontwikkelingen daarom vragen. Per versie worden inhoudelijke wijzigingen
geregistreerd, zodat besluitvorming en de ontwikkeling van de
architectuur in de tijd navolgbaar en herleidbaar blijven.

Voor zover dit document met een externe organisatie of met een
leverancier gedeeld is, geldt dat aan dit document geen rechten ontleend
kunnen worden. De auteur aanvaardt geen aansprakelijkheid voor schade
als gevolg van mogelijke onjuistheden of onvolledigheden in de
aangeboden informatie. Leverancier dient tijdens de initiatie- of
inventarisatiefase van het (implementatie)project de aangeboden
informatie te verifiëren en ontbrekende informatie op te halen.
