# Architectuurprincipes

De strategische doelstellingen beschrijven wat het Platform
Dienstverlening wil bereiken. Dit onderdeel beschrijft de overkoepelende
architectuurprincipes, nodig om deze doelstellingen op een consistente
en samenhangende manier te realiseren.

Deze principes zijn een samenhangende selectie en concretisering van
bestaande uitgangspunten uit landelijke architecturen, gemeentelijk
beleid en de praktijk van het Platform Dienstverlening.

De principes zijn afgeleid uit onder meer:

- De informatiekundige visie Common Ground;

- De Nederlandse Digitaliseringsstrategie (NDS);

- Vastgestelde architectuurbesluiten (Architecture Decision Records
  (ADR's));

- Bestaande platformarchitectuur en technische standaarden;

- Praktijkervaringen uit de ontwikkeling en implementatie van het
  Platform Dienstverlening binnen G4 en Dimpact.

Deze zijn bewust hoog-over en selectief. Zij zijn gekozen omdat zij de
belangrijkste strategische dimensies van het Platform Dienstverlening
vertegenwoordigen. Tijdens het opstellen van deze architectuur zijn de
principes iteratief gevalideerd met de Technische Stuurgroep,
Platformmanagement en architecten van de deelnemende gemeenten.

### Principe: Architectuurgedreven vernieuwing

#### Uitgangspunt

Ontwikkeling begint niet bij de keuze voor een applicatie, maar bij de
gewenste dienstverlening, de onderliggende waardestroom en de behoeften
van inwoners, ondernemers en uitvoerend professionals. Architectuur
bepaalt welke generieke businessfunctionaliteit en voorzieningen nodig
zijn om deze dienstverlening te realiseren; software is daarvan de
implementatie.

#### Implicaties

- Nieuwe ontwikkelingen starten vanuit de publieke opgave en de
  businessbehoefte, niet vanuit een applicatie.

- De waardestroom voor inwoners, ondernemers en uitvoerend professionals
  is leidend bij het ontwerpen van functionaliteit.

- Functionaliteit wordt eerst beoordeeld op generieke toepasbaarheid.

- Hergebruik gaat vóór nieuwbouw.

- Applicaties volgen de architectuur en bepalen deze niet.

**Uitwerking:** Business- en applicatiearchitectuur.

### Principe: Informatiegericht werken

#### Uitgangspunt

Informatie vormt het verbindende element tussen dienstverlening,
processen, applicaties en organisatie. Gegevens worden onafhankelijk van
individuele processen en applicaties beheerd, zodat zij meervoudig
kunnen worden gebruikt. Daarbij wordt niet alleen de gegevensinhoud
vastgelegd, maar ook de context die nodig is om de betekenis, herkomst,
betrouwbaarheid en samenhang van informatie te begrijpen en te
verantwoorden. Implicaties

- Gegevens worden éénmaal vastgelegd en meervoudig gebruikt.

- Processen en dienstverlening geven aanleiding voor het ontstaan en
  wijzigen van gegevens; ze zijn ook afnemer van informatie; de regie op
  informatie ligt bij registraties.

- Registraties bevatten naast gegevens ook de context die nodig is om
  informatie te interpreteren, zoals bron, actor, tijdstip, aanleiding,
  doelbinding, status en onderlinge relaties.

  Herkomst, gebruik en wijzigingen van informatie zijn herleidbaar door
  middel van metadata, contextregistratie en datalineage. Informatie kan
  domeinoverstijgend worden toegepast.

- Consistentie, kwaliteit en herleidbaarheid van gegevens worden
  centraal geborgd.

- Nieuwe vormen van dienstverlening kunnen worden gerealiseerd zonder
  gegevens opnieuw te organiseren.

**Uitwerking:** Businessarchitectuur, Informatiearchitectuur.

### Principe: (Micro) servicearchitectuur

#### Uitgangspunt

Het Platform Dienstverlening bestaat uit kleine, zelfstandige services
die onafhankelijk ontwikkeld, uitgerold en beheerd kunnen worden.

#### Implicaties

- Services zijn autonoom inzetbaar.

- Services hebben een gestandaardiseerde interface.

- Teams kunnen onafhankelijk ontwikkelen.

- Schaalbaarheid vindt plaats per service.

- Geautomatiseerd testen en deployment zijn onderdeel van iedere
  service.

**Uitwerking:** Applicatie- en technologiearchitectuur.

### Principe: Expliciete bedrijfslogica

#### Uitgangspunt

Bedrijfsprocessen, beslisregels en gegevens worden als afzonderlijke
architectuurelementen gemodelleerd. Beslisregels worden waar mogelijk
centraal beheerd en herbruikbaar vastgelegd, zodat zij consistent kunnen
worden toegepast in meerdere processen, BusinessServices en kanalen.

Dit principe anticipeert o.a. op [RegelRecht: van wet naar digitale
werking](https://regelrecht.rijks.app/).

#### Implicaties

- Beslisregels worden niet hard gecodeerd in applicaties wanneer zij
  generiek toepasbaar zijn.

- Processen beschrijven de volgorde van activiteiten; beslisregels
  beschrijven de inhoud van beslissingen.

- Beslisregels zijn herbruikbaar door meerdere BusinessServices en
  processen.

- Beslisregels zijn versieerbaar en historisch reproduceerbaar.

- Beslisregels zijn begrijpelijk voor beleidsmedewerkers, juristen en
  uitvoerende professionals.

- Wijzigingen in beleid of regelgeving leiden primair tot aanpassing van
  beslisregels en niet van procesmodellen of applicaties.

**Uitwerking:** Business-, informatie- en applicatiearchitectuur.

### Principe: Kwaliteit by Design

#### Uitgangspunt

Niet-functionele kwaliteitseisen worden vanaf het ontwerp integraal
meegenomen in architectuur, software en dienstverlening. Aspecten zoals
informatiebeveiliging, privacy, toegankelijkheid, informatiebeheer,
archivering, logging, auditing en beheerbaarheid zijn geen afzonderlijke
voorzieningen achteraf, maar vormen een integraal onderdeel van iedere
platformvoorziening.

#### Implicaties

- Privacy, informatiebeveiliging en informatiebeheer worden vanaf het
  ontwerp meegenomen.

- Logging, auditing en recordmanagement zijn standaard onderdeel van
  iedere voorziening.

- Componenten voldoen aantoonbaar aan geldende wet- en regelgeving en
  architectuurkaders.

- Niet-functionele kwaliteitseisen worden centraal vastgesteld en door
  generieke platformvoorzieningen ingevuld.

- Nieuwe functionaliteit wordt uitsluitend gerealiseerd wanneer ook de
  benodigde kwaliteitsaspecten integraal zijn ontworpen.

**Uitwerking:** Technologiearchitectuur, Informatiearchitectuur en
Governance.

### Principe: Generiek vóór specifiek

#### Uitgangspunt

Nieuwe functionaliteit wordt generiek ontwikkeld wanneer deze in
meerdere processen, domeinen of gemeenten toepasbaar is.
Domeinspecifieke oplossingen worden alleen ontwikkeld wanneer generieke
realisatie aantoonbaar niet passend is.

#### Implicaties

- Generieke functionaliteit wordt centraal ontwikkeld.

- Domeinen bouwen voort op generieke voorzieningen.

- Duplicatie wordt voorkomen.

- Alleen specifieke functionaliteit wordt domeinspecifiek gerealiseerd.

**Uitwerking:** Business- en applicatiearchitectuur.

### Principe: Beleidsruimte als basis

#### Uitgangspunt

Wendbaarheid is een bestuurlijke kwaliteit. Een gemeente die
verantwoordelijk blijft voor haar besluiten moet ook tijdig kunnen
handelen wanneer wetgeving, lokaal beleid of maatschappelijke
omstandigheden veranderen. Waar de aard van de taak en
bevoegdheidsverdeling ruimte bieden voor vergaande standaardisatie kan
die ruimte worden benut; waar de gemeentelijke verantwoordelijkheid
aantoonbaar lokale keuzes vraagt, moet de generieke functionaliteit die
keuzes tijdig en uitvoerbaar kunnen ondersteunen.

#### Implicaties

- Legitieme wettelijke en lokale keuzeruimte wordt in het IT-ontwerp
  ingebouwd, inclusief extensiepunten voor maatwerk;

- Voor ingebruikname toetsen op

  - Ondersteunt de voorziening de beleidsruimte en de menselijke maat

  - Is de oplossing lokaal voldoende wendbaar bij wetswijzigingen

  - Geen normatieve beleidskeuze afgedwongen door technische
    standaardisatie

- Bedrijfszekerheid en omkeerbaarheid (exit mogelijkheid)

**Uitwerking:** Business- en applicatiearchitectuur.

### Principe: Hergebruik

#### Uitgangspunt

Generieke functionaliteit wordt éénmaal ontwikkeld en meervoudig
toegepast.

#### Implicaties

Hergebruik vindt plaats op verschillende niveaus:

- Services;

- Applicatiefuncties;

- BusinessServices;

- Infrastructuur;

- Platformvoorzieningen.

Nieuwe ontwikkeling vindt uitsluitend plaats wanneer bestaande
voorzieningen aantoonbaar niet voldoen.

**Uitwerking:** Business-, applicatie- en technologiearchitectuur.

### Principe: Data bij de bron

#### Uitgangspunt

Gegevens worden beheerd door de daarvoor aangewezen bronhouder en worden
vanuit die bron beschikbaar gesteld. Processen en applicaties gebruiken
gegevens, maar zijn daarvan geen eigenaar.

#### Implicaties

- Registraties vormen de primaire bron voor gemeentelijke gegevens.

- Bestaande [(landelijke, authentieke)
  bronnen](https://www.noraonline.nl/wiki/Stelsel_van_het_heden_(basisregistraties_als_elementaire_bouwstenen))
  blijven leidend.

- Gegevens worden niet onnodig gedupliceerd.

**Uitwerking:** Informatiearchitectuur.

### Principe: Data-autonomie

#### Uitgangspunt

Gemeenten en inwoners behouden zeggenschap over hun gegevens en kunnen
bepalen hoe deze worden vastgelegd, gebruikt, gedeeld en beheerd.

**Implicaties**

- Gegevens volgen gestandaardiseerde semantiek.

- Gegevens zijn overdraagbaar.

- Gemeenten bepalen toegang en gebruik.

- Leveranciers beperken de beschikbaarheid of overdraagbaarheid van
  gegevens niet.

- Inwoners en ondernemers kunnen erop vertrouwen dat hun gegevens
  zorgvuldig, transparant en uitsluitend voor het beoogde doel worden
  gebruikt, waarbij inzichtelijk is welke gegevens worden verwerkt en
  door wie.

**Uitwerking:** Informatiearchitectuur.

### Principe: Open Source

#### Uitgangspunt

Alle generieke software die binnen het Platform Dienstverlening wordt
ontwikkeld of gefinancierd, wordt als Open Source beschikbaar gesteld.

#### Implicaties

- Broncode is openbaar beschikbaar.

- Ontwikkeling vindt transparant plaats.

- Intellectueel eigendom wordt onafhankelijk ondergebracht.

- Hergebruik staat centraal.

**Uitwerking:** Governance.

### Principe: Portabiliteit en compatibiliteit

#### Uitgangspunt

Platformcomponenten zijn overdraagbaar, reproduceerbaar en interoperabel
binnen het Platform Dienstverlening.

#### Implicaties

- Componenten worden als container-images geleverd.

- Buildprocessen zijn reproduceerbaar.

- Componenten sluiten aan op platformstandaarden.

- Integraties en afhankelijkheden worden expliciet beschreven.

**Uitwerking:** Technologiearchitectuur.
