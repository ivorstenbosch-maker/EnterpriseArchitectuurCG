# Patronen in ontwikkeling

Het Platform Dienstverlening ontwikkelt zich continu. Naast de in dit
onderdeel beschreven patronen kunnen nieuwe generieke interactiepatronen
worden toegevoegd wanneer deze bijdragen aan een betere ontkoppeling,
herbruikbaarheid of standaardisatie.

Nieuwe patronen worden ontwikkeld conform de architectuurprincipes uit
dit document en maken, na vaststelling, onderdeel uit van de
referentiearchitectuur van het platform. De volgende patronen zijn in
2026/27 kandidaat:

### Autorisatiepatroon (OpenFTV / AuthZEN)

Binnen het Platform Dienstverlening wordt autorisatie niet door
individuele services ingericht, maar als een generieke
platformvoorziening toegepast. Hiervoor wordt aangesloten op de
architectuur van **OpenFTV** en de **AuthZEN-standaard**. Dit maakt het
mogelijk om autorisatiebeslissingen centraal, consistent en
contextafhankelijk uit te voeren.

Het uitgangspunt is dat iedere service verantwoordelijk blijft voor zijn
eigen gegevens en functionaliteit, maar autorisatiebeslissingen
delegeert aan de centrale autorisatievoorziening. Hierdoor worden
autorisatieregels éénmaal beheerd en platformbreed toegepast.

Het patroon bestaat uit de volgende stappen:

- **Doen van een verzoek**  
  Een gebruiker of service doet een aanvraag om een bepaalde handeling
  uit te voeren, bijvoorbeeld het raadplegen of wijzigen van gegevens.

- **Opbouwen van de autorisatiecontext**  
  De uitvoerende service verzamelt de benodigde context, zoals:

  - De identiteit van de actor;

  - De gevraagde handeling;

  - Het betreffende object of de resource;

- **Autorisatiebeslissing**  
  De service vraagt via de AuthZEN-interface een autorisatiebeslissing
  op bij de centrale Policy Decision Point (PDP). Daarbij worden
  beleidsregels uit het Policy Administration Point (PAP) toegepast,
  aangevuld met gegevens uit één of meer Policy Information Points
  (PIP).

- **Afdwingen van de beslissing**  
  De ontvangende service fungeert als Policy Enforcement Point (PEP) en
  voert de beslissing uit. Alleen wanneer de beslissing *Permit* luidt
  wordt de gevraagde handeling uitgevoerd.

Hierdoor ontstaat een uniforme autorisatiearchitectuur waarin beleid,
uitvoering en verantwoording van elkaar zijn gescheiden.

#### Aansluiten op het patroon

Services die persoonsgegevens of andere beschermde gegevens verwerken:

- Implementeren de AuthZEN-interface voor autorisatiebeslissingen.

- Treden op als **Policy Enforcement Point (PEP)**.

- Verstrekken de benodigde context aan de centrale
  autorisatievoorziening.

- Respecteren de teruggegeven autorisatiebeslissing (*Permit* of
  *Deny*).

- Registreren de autorisatiebeslissing als onderdeel van de ketenbrede
  verwerking.

### Loggingpatroon (OpenTelemetry en Logboek Dataverwerkingen)

Binnen het Platform Dienstverlening wordt logging als een generiek
platformpatroon toegepast. Hierbij wordt onderscheid gemaakt tussen de
technische registratie van gebeurtenissen en de juridische
verantwoording van gegevensverwerkingen.

OpenTelemetry (OTel) vormt de technische standaard voor het vastleggen
van logs, traces en events over de gehele keten. Het **Logboek
Dataverwerkingen (LDV)** bouwt hierop voort door deze technische logging
te verrijken met informatie over doelbinding, grondslag en de
uitgevoerde gegevensverwerking. Hierdoor ontstaat één samenhangend beeld
van een gegevensverwerking, ongeacht hoeveel services daarbij betrokken
zijn.

Het patroon bestaat uit de volgende stappen:

- **Start van een verwerking**  
  Een gebruiker of service initieert een verwerking. Daarbij wordt een
  ketenbrede trace gestart conform de W3C Trace Context-standaard.

- **Verwerking door services**  
  Iedere service legt relevante gebeurtenissen vast volgens de
  OpenTelemetry-standaard. Hierbij worden onder andere de trace-id, de
  uitgevoerde handeling en de betrokken component geregistreerd.

- **Registratie van autorisatie en gegevensgebruik**  
  Autorisatiebeslissingen, API-aanroepen en gegevensmutaties worden als
  onderdeel van dezelfde trace vastgelegd. Hierdoor ontstaat een
  volledig beeld van de uitgevoerde verwerking.

- **Verrijking met verwerkingscontext**  
  De technische logging wordt gekoppeld aan de bijbehorende
  verwerkingsactiviteit uit het Verwerkingsregister. Daarbij worden
  onder meer doelbinding, grondslag en de aard van de gegevensverwerking
  vastgelegd.

- **Registratie in het Logboek Dataverwerkingen**  
  Alle relevante gebeurtenissen worden samengebracht in één
  platformbreed Logboek Dataverwerkingen. Hierdoor ontstaat een complete
  en herleidbare registratie van de uitgevoerde gegevensverwerking.

Deze werkwijze maakt het mogelijk om gegevensverwerkingen over meerdere
componenten heen te reconstrueren en ondersteunt zowel operationeel
beheer als wettelijke verantwoording.

#### Aansluiten op het patroon

Alle componenten binnen het Platform Dienstverlening:

- Gebruiken **OpenTelemetry** voor logging, metrics en distributed
  tracing.

- Propageren de **trace-id** over alle API-calls en events.

- Leggen relevante handelingen en gebeurtenissen vast conform de
  platformstandaard.

- Registreren autorisatiebeslissingen als onderdeel van dezelfde trace.

- Verrijken logging met de benodigde context voor het Logboek
  Dataverwerkingen.

- Leveren hun logging aan de centrale OTel-infrastructuur.

De centrale loggingvoorziening bestaat uit:

- **OpenTelemetry Collectors** voor het verzamelen van logs, traces en
  metrics;

- **OpenTelemetry Backend(s)** voor opslag en analyse;

- **Logboek Dataverwerkingen (LDV)** voor de registratie van
  gegevensverwerkingen;

- **Verwerkingsregister** voor de registratie van
  verwerkingsactiviteiten, doelbinding en grondslag.

**Uitgangspunten**

Bij de inrichting van het loggingpatroon gelden de volgende
uitgangspunten:

- Iedere relevante gegevensverwerking is volledig herleidbaar over de
  gehele keten.

- Alle componenten gebruiken hetzelfde OpenTelemetry-formaat.

- Persoonsgegevens worden niet onnodig opgenomen in technische logging;
  waar mogelijk worden stabiele identifiers gebruikt.

- Het Logboek Dataverwerkingen bevat de semantische en juridische
  context van de verwerking en vormt de basis voor verantwoording
  richting inwoners, toezichthouders en auditors.

- Logging ondersteunt zowel technische observability als compliance,
  zonder dat hiervoor afzonderlijke loggingmechanismen per component
  nodig zijn.
