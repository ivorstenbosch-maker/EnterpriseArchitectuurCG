# Implicaties voor de bestaande organisatie

De invoering van Common Ground en het Platform Dienstverlening betekent
meer dan een verandering van de technische architectuur. Het
introduceert een andere manier van kijken naar gemeentelijke
dienstverlening, waarbij publieke waarde, generieke BusinessServices en
intergemeentelijke samenwerking het uitgangspunt vormen. Dit heeft
gevolgen voor de manier waarop beleid, architectuur, analyse,
ontwikkeling, beheer en governance worden ingericht.

De volledige organisatorische en bestuurlijke impact van deze transitie
valt buiten de scope van deze architectuur. Dit hoofdstuk schetst daarom
uitsluitend de belangrijkste implicaties op hoofdlijnen voor de rollen
en verantwoordelijkheden die direct raken aan de ontwikkeling,
realisatie en het beheer van het Platform Dienstverlening. De verdere
organisatorische inrichting, governance en veranderkundige implementatie
vragen om een afzonderlijke uitwerking.

### Directie, proceseigenaren en opdrachtgevers

De invoering van een platformbenadering verandert ook de wijze waarop
gemeenten investeren in digitalisering. Waar de nadruk traditioneel ligt
op het selecteren, aanbesteden en implementeren van afzonderlijke
applicaties, verschuift de aandacht naar de gezamenlijke ontwikkeling en
doorontwikkeling van generieke functionaliteit.

Voor directeuren, proceseigenaren en andere opdrachtgevers betekent dit
dat zij:

- Ontwikkelingen primair beoordelen vanuit de bijdrage aan de
  gezamenlijke dienstverlening;

- Vaker investeren in gezamenlijke ontwikkeling met andere gemeenten dan
  in individuele aanbestedingen;

- Hergebruik en standaardisatie meewegen als volwaardig onderdeel van
  businesscases;

- Gezamenlijk prioriteiten stellen voor de doorontwikkeling van het
  platform.

Hierdoor verschuift de focus van het verwerven van software naar het
gezamenlijk ontwikkelen en beheren van publieke digitale voorzieningen.

### Concern- en thema-architecturen

Deze werkwijze heeft ook consequenties voor gemeentelijke thema- en
concernarchitecturen. Deze zijn van nature domeinoverstijgend, maar
binnen Common Ground gaan ze niet langer primair over applicaties of
systemen, maar over registraties, bedrijfsobjecten en gegevensstromen.

Dit betekent bijvoorbeeld dat eisen aan autorisatie, metadata, logging,
auditing, archivering of datakwaliteit niet op applicatieniveau worden
uitgewerkt, maar moeten aansluiten op een landschap waarin gegevens en
functionaliteit verdeeld zijn over meerdere samenwerkende services.

### Project- en solutionarchitecten

Voor project- en solutionarchitecten verschuift de focus van
applicatiegericht ontwerpen naar bedrijfsarchitectuur als vertrekpunt.
Nieuwe initiatieven worden niet langer primair afgebakend vanuit een
project, applicatie of organisatorisch domein, maar vanuit de
onderliggende waardestroom en de BusinessServices die daarvoor nodig
zijn.

Dit betekent dat architecten:

- Nieuwe vraagstukken eerst toetsen aan de bestaande
  bedrijfsarchitectuur;

- Actief zoeken naar bestaande BusinessServices en andere herbruikbare
  bouwstenen;

- De architectuurscope verbreden wanneer meerdere processen of domeinen
  hetzelfde vraagstuk raken;

- Alleen nieuwe functionaliteit ontwerpen wanneer bestaande
  voorzieningen aantoonbaar onvoldoende aansluiten.

Hierdoor verschuift de rol van projectarchitect van het ontwerpen van
individuele oplossingen naar het bewaken van samenhang binnen het
platform.

### Informatiebeveiliging en privacy

Ook de rol van informatiebeveiligings- en privacyfunctionarissen
verandert. Doordat generieke platformvoorzieningen centraal worden
ontwikkeld en beheerd, kunnen beveiligings- en privacymaatregelen steeds
vaker platformbreed worden ingericht en beoordeeld.

Voor privacy officers en informatieadviseurs betekent dit dat de
aandacht verschuift van het afzonderlijk toetsen van iedere applicatie
naar het beoordelen en bewaken van de generieke platformvoorzieningen en
de daarop gebaseerde architectuur.

Nieuwe oplossingen hoeven daardoor niet telkens opnieuw volledig op
dezelfde generieke aspecten te worden beoordeeld, maar kunnen
voortbouwen op reeds gevalideerde voorzieningen voor bijvoorbeeld
authenticatie, autorisatie, logging, auditing, gegevensuitwisseling en
beveiliging. Hierdoor ontstaat meer uniformiteit, neemt de kwaliteit van
de toetsing toe en wordt dubbel werk voorkomen.

### Businessanalisten

Ook voor businessanalisten verandert de manier van analyseren. De nadruk
verschuift van het beschrijven van bestaande processen naar het
modelleren van de onderliggende dienstverlening.

Businessanalisten richten zich daarom nadrukkelijk op:

- Het identificeren van de maatschappelijke opgave en de gewenste
  waardestroom;

- Het ontwikkelen van een gedeelde taal tussen beleid, uitvoering en IT;

- Het identificeren van BusinessServices en bedrijfsobjecten;

- Het identificeren van beslisregels: beslisregels vormen een expliciet
  onderdeel van de dienstverlening en beschrijven hoe wetgeving en
  beleid worden toegepast;

- Het onderscheiden van generieke en domeinspecifieke functionaliteit;

- Het modelleren van processen als samenstelling van bestaande
  BusinessServices.

Hierdoor ontstaat een stabielere bedrijfsarchitectuur die minder
afhankelijk is van de inrichting van individuele applicaties.

### Functioneel en technisch beheer

Ook de inrichting van beheer verandert. Binnen een componentgebaseerde
architectuur verschuift het beheer van complete applicaties naar het
beheren van platformvoorzieningen, generieke services en configuraties.

Dit betekent onder meer dat:

- Functioneel beheer zich meer richt op de inrichting van generieke
  voorzieningen, formulieren, beslisregels, procesmodellen en
  configuraties dan op afzonderlijke applicaties;

- Technisch beheer zich ontwikkelt van applicatiebeheer naar
  platformbeheer, waarbij aandacht verschuift naar generieke
  infrastructuur, deployment, monitoring, beveiliging en beschikbaarheid
  van platformdiensten;

- Wijzigingen vaker plaatsvinden binnen gedeelde voorzieningen en
  daardoor een bredere impact kunnen hebben;

- Samenwerking tussen beheerteams belangrijker wordt, omdat meerdere
  gemeenten en meerdere BusinessServices gebruikmaken van dezelfde
  platformcomponenten.

Hierdoor verschuift het beheer geleidelijk van een applicatiegerichte
naar een servicegerichte organisatie.

### Ontwikkeling van gemeentelijke IV-organisaties

Op langere termijn ondersteunt de platformarchitectuur ook een andere
inrichting van de gemeentelijke IV-organisatie. Doordat gemeenten steeds
vaker gebruikmaken van dezelfde architectuur, standaarden en
platformvoorzieningen, ontstaat een meer uniforme manier van
ontwikkelen, beheren en doorontwikkelen.

Hierdoor wordt het eenvoudiger om kennis, software en capaciteit tussen
gemeenten uit te wisselen. Ontwikkelaars, architecten, beheerders en
andere IV-professionals kunnen gemakkelijker samenwerken aan dezelfde
voorzieningen en hun expertise breder inzetten. Dit vergroot niet alleen
de continuïteit van het platform, maar draagt ook bij aan een
efficiënter gebruik van schaarse IV-capaciteit binnen de gemeentelijke
sector.

### Doorontwikkeling van de governance

De ontwikkeling van het Platform Dienstverlening vindt plaats binnen een
groeiend samenwerkingsverband van gemeenten. Daarbij wordt toegewerkt
naar een meer landelijke inrichting van ontwikkeling, beheer en
governance.

De inrichting van een structurele landelijke beheerorganisatie maakt
onderdeel uit van de roadmap. De exacte invulling hiervan is nog
onderwerp van verdere uitwerking. Gemeenten doen er daarom goed aan om
bij nieuwe ontwikkelingen rekening te houden met toekomstige landelijke
samenwerking, bijvoorbeeld door gebruik te maken van open standaarden,
generieke voorzieningen en gezamenlijke ontwikkelprocessen.

Tegelijkertijd is terughoudendheid gewenst om vooruit te lopen op
governancekeuzes die nog niet zijn gemaakt. De huidige architectuur is
daarom zo ingericht dat zij zowel binnen de bestaande G4-samenwerking
als binnen een toekomstige landelijke beheerorganisatie toepasbaar
blijft. Hierdoor kan de governance zich geleidelijk ontwikkelen zonder
dat fundamentele architectuurkeuzes opnieuw hoeven te worden gemaakt.
