# Enterprise Architectuur Common Ground & Platform Dienstverlening

Dit is de Enterprise Architectuur voor Common Ground en het Platform Dienstverlening. 

## Beschikbare vormen

- **GitBook** — de architectuur is links op deze pagina per hoofdstuk en onderdeel ontsloten.
- **PDF** — [de volledige Enterprise Architectuur als één document](Enterprisearchitectuur%20Common%20Ground%20%26%20Platform%20Dienstverlening.pdf), geschikt om te lezen, te delen en te archiveren.
- **Volledige Markdown** — [Enterprisearchitectuur-GPT.md](Enterprisearchitectuur-GPT.md) bevat de volledige architectuur in één Markdown-bestand en kan bijvoorbeeld worden gebruikt als context voor GPT of andere AI-toepassingen.

## Leeswijzer

Dit document is bedoeld voor verschillende doelgroepen. Afhankelijk van
de rol van de lezer zijn niet alle hoofdstukken even relevant.

Bij grote hoofdstukken zijn korte abstracts toegevoegd voor wie geen
tijd of zin heeft om de hele tekst te lezen, zodat in ieder geval
duidelijk is wat de hoofdgedachte en relevantie van het onderdeel is.

| **Doelgroep** | **Aanbevolen hoofdstukken** |
|----|----|
| **Bestuurders, opdrachtgevers en programmamanagers** | De [**managementsamenvatting**](#managementsamenvatting), hoofdstuk 2 t/m 5. Deze hoofdstukken beschrijven de aanleiding, strategische doelen, architectuurvisie, uitgangspunten, governance en scope van het Platform Dienstverlening. Daarnaast is in het bijzonder het onderdeel **[Implicaties voor de bestaande organisatie](06-businessarchitectuur/README.md#implicaties-voor-de-bestaande-organisatie)** relevant. |
| **Enterprise- en domeinarchitecten** | Het volledige document. De architectuur is opgebouwd volgens de TOGAF Architecture Development Method (ADM) en beschrijft de samenhang tussen business-, informatie-, applicatie- en technische architectuur. |
| **Solution- en softwarearchitecten** | Hoofdstuk 4 t/m 14. Deze hoofdstukken beschrijven de architectuurprincipes, architectuurpatronen, bouwstenen, API's, technische architectuur en implementatiepatronen. |
| **Ontwikkelteams en leveranciers** | Hoofdstuk 5 t/m 14. Deze hoofdstukken bevatten de architectuurkaders voor de ontwikkeling van businessanalyse, softwarecomponenten, registraties, API's, infrastructuur en technische implementaties. |
| **Projectleiders en implementatiemanagers** | Hoofdstuk 4, 5, 6, 8, 9, 13 en 14. Deze hoofdstukken beschrijven de architectuurkaders waarbinnen implementatieprojecten worden uitgevoerd en wijzigingen worden beheerd. |

## Managementsamenvatting

Gemeenten staan voor een fundamentele vernieuwing van hun
informatievoorziening. Toenemende maatschappelijke verwachtingen, nieuwe
wet- en regelgeving, hogere eisen aan transparantie en digitale
dienstverlening vragen om een informatievoorziening die wendbaar,
samenhangend en duurzaam is. Common Ground biedt hiervoor de richting.
Deze Enterprisearchitectuur beschrijft de architectuur van Common Ground
binnen de gezamenlijke ontwikkeling van de G4-gemeenten. De architectuur
vormt het richtinggevende kader voor de gezamenlijke ontwikkeling van
generieke voorzieningen en de toepassing daarvan binnen de deelnemende
gemeenten.

Het **Platform Dienstverlening** is de referentie-implementatie van
Common Ground: een gezamenlijk door de G4 ontwikkelde combinatie van
architectuur, visie en softwarevoorzieningen. Het platform bestaat uit
een samenhangend geheel van herbruikbare softwarecomponenten,
registraties, API's en infrastructuur waarmee gemeenten hun
dienstverlening realiseren. Daarmee vertaalt het Common Ground naar een
concreet en toepasbaar software-ecosysteem en vormt het een praktische
invulling van landelijke ontwikkelingen zoals de Nederlandse
Digitaliseringsstrategie (NDS).

De architectuur heeft een organisatiebrede scope binnen de
G4-samenwerking en biedt richting voor zowel de ontwikkeling als de
toepassing van het Platform Dienstverlening. Daarbij worden kaders
gegeven voor:

- De businessarchitectuur;

- De informatie- en data-architectuur;

- De applicatiearchitectuur;

- De technische architectuur;

- Implementatiepatronen;

- Governance en doorontwikkeling.

Werken onder architectuur betekent dat business, programmamanagement en
realisatie werken vanuit een gedeelde set van architectuurprincipes,
kaders en ontwerpkeuzes. De architectuur vormt daarbij het
gemeenschappelijke afwegingskader voor strategische keuzes,
investeringsbeslissingen, prioritering en de ontwikkeling van
voorzieningen binnen de G4.

#### Organisatorische transitie

De realisatie van Common Ground betekent een organisatorische
verandering. De nadruk verschuift van applicatiegericht werken naar het
gezamenlijk ontwikkelen en beheren van generieke voorzieningen.

Dit vraagt om een stevige rol van de business, waarbij gemeenten vanuit
het perspectief van één overheid sturen op gezamenlijke dienstverlening.
Innovatie, de maatschappelijke opgave en de waardestroom voor inwoners
en ondernemers staan centraal, en dit heeft gevolgen voor bestaande
rollen verantwoordelijkheden binnen gemeenten.

####
