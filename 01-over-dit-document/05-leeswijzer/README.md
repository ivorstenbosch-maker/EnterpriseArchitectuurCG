# Leeswijzer

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
model](../08-applicatiearchitectuur/02-het-vijf-lagen-model/README.md#het-vijf-lagen-model) (in het hoofdstuk
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
