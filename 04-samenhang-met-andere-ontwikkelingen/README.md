# 4. Samenhang met andere ontwikkelingen

| **Compact:** |
|----|
| Het Platform Dienstverlening is geen eiland. Dit hoofdstuk legt uit hoe het platform zich verhoudt tot de NDS, andere landelijke ontwikkelingen en de gemeentelijke praktijk. De grote lijn: landelijke ambities rond standaarden, hergebruik, data delen, digitale autonomie en gezamenlijke voorzieningen worden vertaald naar een concrete gemeentelijke inrichting. Het platform is daarmee niet nóg een strategisch praatstuk, maar probeert de stap te maken van “we vinden dit allemaal belangrijk” naar “zo gaan we het daadwerkelijk bouwen en gebruiken”. |

Het Platform Dienstverlening is een zelfstandig architectuur- en
ontwikkelprogramma met een eigen scope, governance en roadmap. Het vormt
de meest concrete uitwerking van de informatiekundige visie Common
Ground. Tegelijkertijd wordt het platform niet in een vacuüm ontwikkeld.

Dit hoofdstuk beschrijft hoe het Platform Dienstverlening zich verhoudt
tot de belangrijkste landelijke ontwikkelingen, welke uitgangspunten
worden overgenomen en op welke onderdelen het platform een eigen
invulling of verdere concretisering geeft.

## Relatie met de Nederlandse Digitaliseringsstrategie (NDS)

De [Nederlandse
Digitaliseringsstrategie](https://www.digitaleoverheid.nl/wp-content/uploads/sites/8/2025/07/108.201-NDS-publicatie_v19-WEB.pdf)
beschrijft de beweging naar één digitale overheid, waarin gezamenlijke
regie, (verplicht te stellen) standaarden, herbruikbare bouwstenen en de
ontwikkeling naar een federatief datastelsel centraal staan.

Het Platform Dienstverlening vormt een concrete invulling van deze
strategie op gemeentelijk niveau. De architectuur vertaalt de
strategische uitgangspunten van de NDS naar een samenhangend geheel van:

- Een servicegerichte architectuur met herbruikbare componenten, waarin
  dienstverlening centraal staat en processen worden herontworpen vanuit
  de leefwereld van burgers en ondernemers. Dit ondersteunt proactieve
  dienstverlening (‘één overheid’) en vermindert afhankelijkheid van
  specifieke leveranciersoplossingen (prioriteit 4: burgers en
  ondernemers centraal; prioriteit 5: digitale autonomie en
  weerbaarheid)

- Een gegevenslaag gebaseerd op ‘data bij de bron’, semantische
  standaardisatie en federatieve uitwisseling (prioriteit 2: data delen
  en benutten)

- Gezamenlijk ontwikkelde en beheerde bouwblokken, die hergebruik en
  schaalvoordelen ondersteunen (prioriteit 4: dienstverlening;
  prioriteit 6: digitaal vakmanschap en samenwerking)

- Een infrastructuur gebaseerd op cloud-native principes en
  portabiliteit, passend bij de ontwikkeling naar gezamenlijke
  cloudvoorzieningen (prioriteit 1: cloud)

- Inrichting van centrale beveiliging, autonomie en controle op data en
  componenten (prioriteit 5: digitale weerbaarheid en autonomie)

- Ondersteuning van datagedreven werken en informatiegedreven
  dienstverlening (prioriteit 2: data; prioriteit 6: digitaal
  vakmanschap)

De expliciete focus op eenduidige semantiek en hoogwaardige
datakwaliteit vormt daarbij een randvoorwaarde voor het verantwoord
toepassen van artificiële intelligentie (prioriteit 3). Zonder data kan
AI geen betrouwbare of uitlegbare bijdrage leveren.

<img
src="../media/media/image9.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

## Andere landelijke ontwikkelingen

### Interactiedoelen Architectuur Digitale Overheid 2030 (GDI-NORA)

De [Architectuur Digitale Overheid
2030](https://pgdi.nl/file/download/8e2cdce9-5f23-451d-9537-946d2086c557/20251103-architectuur-digitale-overheid-2030-versie-102.pdf)
(ADO2030) formuleert de beleidsdoelen voor de ontwikkeling van de
digitale overheid. Voor het contact en de dienstverlening aan burgers en
bedrijven zijn deze doelen verder geconcretiseerd in de
[Domeinarchitectuur
Interactie](https://file.notion.com/f/f/8b8dc544-81d0-40fc-90e8-ce6ddba9548c/12b9b5ee-d397-4829-9bce-4539a783b1a9/20251110_AR_08_Domeinarchitectuur_Interactie.pdf?table=block&id=3d578b5f-4db4-80f5-b367-fbbb11c3653d&spaceId=8b8dc544-81d0-40fc-90e8-ce6ddba9548c&expirationTimestamp=1790899200000&signature=5bi9pZ0-sM3KZ6VhtHhXNCdSIvFNG_-57KF8tZHh3x8&downloadName=20251110+AR+08+Domeinarchitectuur+Interactie.pdf).
Deze domeinarchitectuur vertaalt de beleidsdoelen van ADO2030 naar 11
interactiedoelen, waaronder

- één-overheidsbeleving,

- proactieve dienstverlening,

- samenhangende communicatie,

- regie op gegevens,

- open overheid,

- kanaalonafhankelijke dienstverlening en

- transparante en volgbare dienstverleningsprocessen.

Deze zijn vastgesteld door de Architectuurraad Digitale Overheid. Een
doel is rechtstreeks verbonden aan de bijpassende kernwaarden,
kwaliteitsdoelen en architectuurprincipes in de NORA.

#### Relatie met Platform Dienstverlening

Het Platform Dienstverlening maakt gebruik van en geeft invulling aan
delen van de doelen en capabilities conform de Architectuur Digitale
Overheid. Het biedt generieke architectuurblokken en herbruikbare
softwarecomponenten die gemeenten kunnen inzetten bij de inrichting en
doorontwikkeling van hun dienstverlening. Een globale mapping als volgt:

<img
src="../media/media/image10.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Federatief Datastelsel (FDS)

Het [**Federatief Datastelsel
(FDS)**](https://federatief.datastelsel.nl/) is een landelijk
afsprakenstelsel voor het verantwoord delen en gebruiken van data binnen
de overheid. Het FDS faciliteert het zoeken, delen en in samenhang
toepassen van hoogwaardige gegevens uit verschillende bronnen, waarbij
gegevens bij de bron blijven en via open standaarden beschikbaar worden
gesteld. Het beschrijft de benodigde stelselfuncties,
architectuurprincipes en standaarden voor een federatief
gegevenslandschap.

#### Relatie met Platform Dienstverlening

Het Platform Dienstverlening realiseert de uitgangspunten van het
Federatief Datastelsel voor de gemeentelijke praktijk. De
platformarchitectuur sluit aan op de architectuurprincipes, standaarden
en stelselfuncties van het FDS en implementeert deze in concrete
generieke voorzieningen, gegevensdiensten en registraties.

### Federatieve Toegangsverlening (FTV)

[**Federatieve Toegangsverlening
(FTV)**](https://vng-realisatie.github.io/ftv/) is een open standaard
voor toegangsverlening binnen het Federatief Datastelsel. De standaard
is gebaseerd op *Externalized Authorization Management (EAM)* en maakt
het mogelijk om autorisatiebeleid los te koppelen van applicaties.
Toegangsbeslissingen worden daardoor centraal, contextafhankelijk,
transparant en traceerbaar genomen, op basis van open standaarden.

#### Relatie met Platform Dienstverlening

Het Platform Dienstverlening realiseert de ondersteuning voor
Federatieve Toegangsverlening als generieke platformvoorziening.
Hierdoor kunnen alle aangesloten componenten gebruikmaken van een
uniforme, landelijke standaard voor federatieve autorisatie en
toegangsverlening.

### Gemeentelijk Gegevensmodel (GGM)

Het **Gemeentelijk Gegevensmodel (GGM)** is het integrale logische
gegevensmodel voor de gemeentelijke informatievoorziening. Het
beschrijft de semantische structuur van gemeentelijke gegevens over alle
beleidsdomeinen heen en vormt daarmee de basis voor eenduidige
gegevensuitwisseling, registraties en informatiemodellen.

<img
src="../media/media/image11.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

#### Relatie met Platform Dienstverlening

Het Platform Dienstverlening gebruikt het Gemeentelijk Gegevensmodel als
uitgangspunt voor de inrichting van generieke registraties en
gegevensdiensten. Omdat deze registraties daadwerkelijk binnen gemeenten
worden geïmplementeerd, levert het platform praktijkervaringen en
concrete actualiseringsvoorstellen voor de verdere ontwikkeling van het
GGM. Daarmee ontstaat een continue wisselwerking tussen
modelontwikkeling en implementatie, waarbij het GGM richting geeft aan
de platformarchitectuur en implementaties binnen het Platform
Dienstverlening bijdragen aan de verdere doorontwikkeling van het model.

## Relatie met gemeentelijke ontwikkeling

De relatie met gedeelde, of parallelle gemeentelijke ontwikkelingen is
als volgt:

#### VNG / VNG Realisatie (Kenniscentrum Architectuur – KCA)

- **Wat het is:** landelijke koepel van gemeenten; VNG Realisatie
  beheert GEMMA‑architectuur.

- Documentatie:

  - [GEMMA Online](https://www.gemmaonline.nl/wiki/Hoofdpagina)

<!-- -->

- Onderdeel van VNG Realisatie is het vastleggen van gemeentelijke
  standaarden (zoals de ZGW-API’s).

#### VNG - MijnServices

MijnServices is een initiatief binnen VNG dat zich richt op het
ontwikkelen van herbruikbare servicedesings voor digitale diensten voor
inwoners en ondernemers. De bron voor de MijnServices is de
implementatie van het Platform Dienstverlening in de Gemeente Den Haag.
Dit is in een landelijk programma opgeschaald naar overheidsbrede
servicedesigns.

- **Wat het is:** een verzameling generieke, herbruikbare servicedesigns

- Documentatie & informatie:

- [MijnServices dienstverlening \| VNG](https://vng.nl/MijnServices)

#### VNG - Landelijk Programma Common Ground (LPCG)

- **Wat het is:** landelijk programma dat de Common Ground‑beweging
  ondersteunt

- Documentatie:

  - [Website Common Ground](https://commonground.nl/)

    <img
    src="../media/media/image12.png"
    style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

#### G4D/Dimpact (Amsterdam, Rotterdam, Den Haag, Utrecht)

- **Wat het is:** samenwerking van de vier grote gemeenten en Dimpact;
  werkt gezamenlijk aan **Platform Dienstverlening**. Dimpact gebruikt
  de bouwstenen als onderdeel van het platform PodiumD

- Documentatie:

  - Notion – samenwerkruimte Common Ground

    - [Backlog](https://www.notion.so/e9375da1960249bba23c49d038d3c888?pvs=21)

    - [Beschrijving Governance &
      proces](https://www.notion.so/Proces-backlog-documentatie-21b78b5f4db4804c828fc43bec7b544c?pvs=21)

  - GitBook – publieke documentatie Platform Dienstverlening

    - [Introductie \| Platform Dienstverlening -
      Public](https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public)

      <img
      src="../media/media/image13.png"
      style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

## Platform Dienstverlening in context

Binnen dit landschap neemt het Platform Dienstverlening een bijzondere
positie in. Waar veel initiatieven zich richten op visieontwikkeling,
architectuurkaders, standaarden of servicedesigns, richt het Platform
Dienstverlening zich op de concrete realisatie daarvan in software en
implementatie. Dit gebeurt in nauwe samenwerking met de
uitvoeringspraktijk. Hierdoor worden architectuurkeuzes getoetst aan
concrete vraagstukken uit de praktijk, zoals veranderende wetgeving,
complexe dienstverlening, gegevensuitwisseling en de dagelijkse
uitvoerbaarheid voor medewerkers en inwoners. Daarmee fungeert het
Platform Dienstverlening als een levende referentiearchitectuur.

Hoewel het in eerste instantie is ontwikkeld voor de gemeentelijke
praktijk, zijn de onderliggende informatiekundige principes generiek
toepasbaar binnen de gehele overheid. Vraagstukken rond gegevensdeling,
transparantie, digitale autonomie, herbruikbare voorzieningen en
publieke dienstverlening spelen niet uitsluitend bij gemeenten. Daarmee
vervult het Platform Dienstverlening niet alleen een uitvoerende rol
binnen de gemeentelijke sector, maar ook een richtinggevende rol voor
andere overheden die werken aan de modernisering van de digitale
overheid.
