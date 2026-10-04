# 9. Logging

| **Abstract/TL;DR** |
|----|
| Dit hoofdstuk beschrijft de uitgangspunten voor logging en observability binnen het Platform Dienstverlening. Logging moet helpen om systemen, gebeurtenissen en ketens te begrijpen, fouten te vinden en beheer en toezicht te ondersteunen. Het gaat dus niet om zoveel mogelijk logregels verzamelen, maar om voldoende informatie om te kunnen reconstrueren wat er is gebeurd. |

Logging is een essentieel onderdeel van de kwaliteitseisen van het
Platform Dienstverlening en geeft invulling aan het principe Kwaliteit
by Design.

Het ondersteunt uiteenlopende doelen, zoals het bewaken van de
technische werking van het platform, het reconstrueren van uitgevoerde
handelingen en het voldoen aan wettelijke eisen op het gebied van
verantwoording, informatiebeheer en beveiliging.

## Vormen van logging binnen de architectuur

Verschillende doelen stellen ook verschillende eisen aan de vastgelegde
informatie, de bewaartermijnen en de wijze waarop logging wordt
gebruikt. Logging is daarom geen eenduidige voorziening, maar bestaat
uit meerdere vormen die elk een eigen verantwoordelijkheid en
toepassingsgebied hebben.

Op hoofdlijnen worden binnen de architectuur drie vormen onderscheiden:

- Technische logging (infrastructuur en observability)

  - Deze vorm richt zich op het functioneren van systemen en
    infrastructuur. Het gaat om logs, metrics en traces die inzicht
    geven in beschikbaarheid, performance en onderlinge communicatie
    tussen services.

  - Deze logging wordt gerealiseerd in de onderliggende infrastructuur
    (Haven/Haven+) en via standaarden zoals OpenTelemetry. Zij maakt het
    mogelijk om storingen te analyseren, ketens te volgen en de
    technische werking van het platform te monitoren.

- Security logging

  - Security logging richt zich op het detecteren en analyseren van
    beveiligingsincidenten en afwijkend gedrag.

  - Deze logging ontstaat op meerdere plekken in het platform, zoals de
    infrastructuur, identity-voorzieningen en autorisatieketen, en wordt
    gebruikt voor monitoring, alarmering en incidentonderzoek. Het
    resultaat is een set events die inzicht geven in mogelijke
    dreigingen en misbruik.

- Logging op juridisch en verantwoordingsniveau

  - De derde vorm betreft logging vanuit het perspectief van
    gegevensgebruik. In deze context bestaan drie niveaus van logging:

    - Connectie van services (via FSC),

    - Toegang (via (Open)FTV) en

    - Verwerking (waarvoor het [Logboek
      dataverwerkingen](https://logius-standaarden.github.io/logboek-dataverwerkingen/) -
      LDV - de standaard is).

  - Deze zijn formeel met elkaar verbonden in de standaarden. Voor de
    terminologie is het belangrijk alleen LDV een dataverwerking te
    noemen. FTV en FSC (of elke andere gateway) doen geen verwerking in
    wettelijke zin (AVG/Wpg/etc).

Bij logging van Dataverwerking staat de vraag centraal:

- Wie heeft welke gegevens gebruikt, wanneer, met welk doel en op basis
  van welke grondslag?

Deze logging is noodzakelijk voor rechtmatigheid, transparantie en
verantwoording richting inwoners, toezichthouders en bestuur, en dit is
het hoofdthema van dit onderdeel.

## Logging van dataverwerking

#### Verantwoordelijkheden

De proceseigenaar (lijnmanagement) is de eigenaar van
informatie(systemen) en verantwoordelijk voor het toepassen van de
verplichte beheersmaatregelen en overheidsmaatregelen uit de BIO voor
het informatiesysteem. ([BIO2
§12.2](https://www.bio-overheid.nl/bio2/bio-producten/baseline-informatiebeveiliging-overheid-2-bio2/)).

De architectuur is stelt de generieke kaders voor logging vast binnen
het platform. De software en infrastructuur moet de mogelijkheden bieden
om die kaders in te vullen. De uiteindelijke inrichting (implementatie)
realiseert de logging tenslotte.

Services zijn verantwoordelijk voor het produceren van de juiste
logevents en het meegeven van de vereiste context. De architectuur zorgt
ervoor dat de logging ketenbreed kan worden verzameld, gekoppeld en
ontsloten.

De verantwoordelijkheid voor het bepalen van het noodzakelijke
detailniveau, de bewaartermijn en het gebruik van de logging blijft bij
de proceseigenaar en de daarvoor verantwoordelijke
organisatieonderdelen.

#### Niveau van logging

Voor logging van dataverwerking geldt: log het laagste detailniveau
waarmee je de noodzakelijke verantwoording kunt afleggen, zonder onnodig
veel persoonsgegevens en opslaglast vast te leggen.

Logboek Dataverwerking onderscheidt [drie
niveaus](https://logius-standaarden.github.io/logboek-dataverwerkingen/#definities-van-niveaus):

- **Niveau 1 – registerverwijzing:** alleen de processing_activity_id en
  daarmee een verwijzing naar het Register worden vastgelegd. Je kunt
  achteraf zien **welke soort verwerking** heeft plaatsgevonden en welke
  gegevens daar potentieel bij horen, maar niet welke gegevens
  daadwerkelijk zijn gebruikt. Dit niveau past wanneer het voldoende is
  om aan te tonen dát een bepaalde verwerking heeft plaatsgevonden.

- **Niveau 2 – kolomverwijzing:** naast de verwijzing naar het Register
  worden ook de **daadwerkelijk gebruikte gegevenscategorieën**
  vastgelegd. Je kunt daarmee achteraf zien welke soorten gegevens zijn
  verwerkt, maar niet welke concrete waarden deze hadden. Dit niveau
  past wanneer je moet kunnen aantonen **welke gegevenscategorieën zijn
  gebruikt**, zonder dat de waarden zelf nodig zijn.

- **Niveau 3 – concrete data:** naast het Register en de
  gegevenscategorieën worden ook de **concrete waarden** vastgelegd.
  Daarmee kan de feitelijke dataverwerking achteraf volledig worden
  gereconstrueerd. Dit niveau past wanneer het noodzakelijk is om te
  kunnen aantonen **welke concrete gegevens daadwerkelijk zijn
  verwerkt**. Kort gezegd: niveau 1 = *wat voor verwerking?*, niveau 2 =
  *welke gegevenscategorieën?*, niveau 3 = *welke concrete waarden?*

Per proces moet dit niveau bij de implementatie bepaald worden. Soms is
de inhoud van de protocollering en logging voorgeschreven, zoals bij
RVIG (BRP-V).
[Suwinet](https://bkwi.nl/standaarden/privacy-beveiliging/suwinet-guidance-2025-voor-de-toepassing-van-de-bio)
schrijft niet alleen logging voor, maar ook dat deze logging voldoende
gedetailleerd is, wordt beschermd, gedurende een vastgestelde periode
beschikbaar blijft én periodiek wordt beoordeeld.

#### Formaat van logs

Het logboek Dataverwerkingen schrijft de volgende velden voor (zie de
[bron](https://logius-standaarden.github.io/logboek-dataverwerkingen/#interface)
voor volledige definities):

| **Veld** | **Verplicht?** | **Definitie** |
|----|----|----|
| trace_id | Verplicht | Unieke identificerende code van de **Trace** die een **Dataverwerking** volgt. Als meerdere applicaties bijdragen aan dezelfde dataverwerking, gebruiken zij dezelfde trace_id. |
| span_id | Verplicht | Unieke identificerende code van een **Actie** binnen een **Dataverwerking**. Eén dataverwerking kan meerdere span_id's bevatten onder dezelfde trace_id. |
| status | Verplicht | Status van de dataverwerking. Dit is een enumeratie met de waarden Unset, Ok en Error, waarmee wordt aangegeven of de verwerking technisch succesvol, expliciet succesvol of met een interne fout is uitgevoerd. |
| name | Verplicht | Naam van de specifieke **Actie** binnen de **Dataverwerking**. Dit is een tekstuele beschrijving voor mensen, niet voor machines. |
| start_time | Verplicht | Tijdstip waarop de **Actie** is gestart, uitgedrukt in milliseconden sinds de Epoch. |
| end_time | Verplicht | Tijdstip waarop de **Actie** is beëindigd, uitgedrukt in milliseconden sinds de Epoch. |
| parent_span_id | Optioneel | Unieke identificerende code van de aanroepende **Actie**. Hiermee wordt de relatie vastgelegd tussen acties binnen dezelfde applicatie of tussen verschillende applicaties. |
| resource | Optioneel | Object met attributen waarmee een systeem, applicatie of component wordt geïdentificeerd, bijvoorbeeld via naam, versienummer of een verwijzing naar een CMDB-record. |
| attributes | Verplicht | Object met velden in de namespace dpl (Data Processing Log). Het bevat de metadata over de dataverwerking, zoals verwijzingen naar verwerkingsactiviteiten, betrokkenen en andere voorgeschreven attributen. |

En bij **Attributes**:

| **Veldnaam** | **Type** | **Omschrijving** |
|----|----|----|
| dpl.core.processing_activity_id | URI | Verwijzing naar een Register met meer informatie over de Verwerkingsactiviteit. |
| dpl.core.data_subject_id | String | Unieke, versleutelde identificerende code van de Betrokkene. |
| dpl.core.data_subject_id_type | String | Type van de identificerende code, zoals BSN, personeelsnummer, of een URI naar een Register dat het type specificeert. |

#### Vergaren van logs

Het is logisch om alle logregels centraal op te slaan en te ontsluiten
omdat dat ketenbrede reconstructie en eenduidige verantwoording mogelijk
maakt: logregels uit verschillende services kunnen aan elkaar worden
gekoppeld, waardoor een volledige dataverwerking kan worden gevolgd
zonder per systeem afzonderlijk te zoeken. Tegelijkertijd kunnen
beveiliging, autorisatie, bewaarbeleid, auditing en ontsluiting centraal
en uniform worden ingericht, terwijl de afzonderlijke applicaties
verantwoordelijk blijven voor het correct produceren van hun logregels.

#### Bewaartermijn

De LDV-standaard schrijft zelf geen bewaartermijn voor. De bewaartermijn
moet worden bepaald op basis van het doel van de logging, toepasselijke
wettelijke bewaartermijnen en de selectielijst van toepassing. NB. voor
logging van BRP-gegevens bestaat [een bewaartermijn van 20
jaar](https://wetten.overheid.nl/BWBR0034327/2026-07-01/0#:~:text=Bescheiden%20verband%20houdend%20met%20de%20verstrekking%20van%20gegevens%20uit%20de%20basisregistratie%20(waaronder%20verzoeken%20betreffende%20het%20inzagerecht)).

Voor overige processen wordt de bewaartermijn vastgelegd in de
selectielijst van VNG ([Selectielijst \|
VNG](https://vng.nl/artikelen/selectielijst)).

#### Vergaren vs. Benutten

Vergaren en benutten twee verschillende functies. Vergaren gaat over het
betrouwbaar, volledig en veilig verzamelen en bewaren van loggegevens;
benutten gaat over het gericht ontsluiten, raadplegen, analyseren en
gebruiken van die gegevens voor bijvoorbeeld verantwoording, toezicht,
onderzoek of incidentafhandeling. Dit onderscheid kan aanleiding zijn om
beide functies als afzonderlijke voorzieningen te beschouwen, ook
wanneer ze gebruikmaken van dezelfde onderliggende opslag.

## Huidige inrichting

In de huidige vorm van het platform is logging als volgt in te richten:

<img
src="../media/media/image28.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

- **Logging van verkeer tussen services (groene lijn)** vindt plaats in
  de onderliggende infrastructuur, binnen de servicemesh (Istio) en de
  observability stack van Haven+. Dit biedt (nu) beperkt inzicht in de
  onderliggende API-calls tussen services. FSC legt vast welke services
  met elkaar communiceren, wanneer dit gebeurt en hoe het verkeer
  verloopt, en registreert transacties en autorisaties op kanaalniveau.

- **Binnen services en applicaties (laag 4/5) (rode pijl)** wordt
  autorisatie ingericht op basis van rollen en context, en worden - als
  het goed is - auditlogs bijgehouden van handelingen binnen de service
  zelf. Deze logging is gericht op het vastleggen van verwerkingen
  binnen de eigen service. Er is ook geen - centrale of
  gestructureerde - vastgestelde plek die aan de functionele eisen voor
  Duurzame Toegankelijkheid (bijv. bewaartermijnen) voldoet, of
  bedrijfsfuncties levert zoals inzage. Er is ook geen standaard in
  gebruik voor het formaat van logregels.

Het vergaren en benutten van logs zijn functionele eisen aan het
platform (en vormen dus een architectural buildingblocks). Deze zijn
momenteel niet ingevuld met solutions. Verschillende gemeenten en
services kiezen eigen oplossingen om aan de eisen te voldoen. Voor deze
buildingblocks zijn bestaande (OpenSource) oplossingen beschikbaar.

## Doelarchitectuur logging

De doelarchitectuur ziet er als volgt uit:

<img
src="../media/media/image29.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

De doelarchitectuur logging is (o.a.) gebaseerd op het Logboek
dataverwerkingen. De doelarchitectuur maakt onderscheid tussen de
verschillende lagen van het Platform Dienstverlening. Per laag ligt de
verantwoordelijkheid voor logging anders. Het uitgangspunt is dat iedere
service voldoende informatie levert om een verwerking **ketenbreed te
kunnen herleiden**, terwijl centrale voorzieningen zorgen voor het
verzamelen, koppelen, bewaren en ontsluiten van de logging.

#### Laag 4/5 – Procesinrichting & interactie

**Voorbeelden:** GZAC, NL-Portal.

Deze laag is belangrijk omdat hier bedrijfsprocessen worden uitgevoerd
en gegevens worden verwerkt in de context van een proces of zaak.

Een service op deze laag moet:

- Iedere relevante gegevensverwerking als event kunnen vastleggen;

- De **trace_id** uit de keten behouden;

- Actor, doelbinding en verwerkingsactiviteit vastleggen;

- Vastleggen welke handeling is uitgevoerd en op welke
  gegevens/resource;

- Interne verwerkingen loggen wanneer gegevens in een eigen database,
  cache of andere opslag worden verwerkt;

- De logging beschikbaar maken voor het centrale Logboek
  Dataverwerkingen.

Voor deze services geldt dat logging niet automatisch ontstaat doordat
een onderliggende registratie wordt gelogd. Een processervice die zelf
gegevens verwerkt, heeft ook een eigen loggingverantwoordelijkheid.
Iedere service op laag 4/5 logt hiervoor iedere relevante actie via
OpenTelemetry (OTel), buffert de logging lokaal en streamt deze naar de
infrastructuur.

Het LDV kent hiervoor, bovenstaand beschreven, drie mogelijke niveaus:

1.  **Registerverwijzing** – aantonen dát een bepaalde verwerking heeft
    plaatsgevonden.

2.  **Kolomverwijzing** – aantonen welke gegevenscategorieën zijn
    gebruikt.

3.  **Concrete data** – kunnen reconstrueren welke concrete waarden zijn
    verwerkt.

Het noodzakelijke niveau wordt per proces bepaald.

#### Laag 3 – Connectiviteit

Op deze laag wordt vooral **de verbinding en toegang** gelogd:

- Welke service communiceert met welke andere service;

- Wanneer de communicatie plaatsvindt;

- Via welk kanaal of welke gateway;

- Welke autorisatie-/toegangsbeslissing heeft plaatsgevonden;

- De technische trace-context.

De logging op deze laag ondersteunt daarmee de ketenbrede
herleidbaarheid.

Belangrijk is dat deze logging niet moet worden verward met logging van
de wettelijke dataverwerking. FSC legt verbinding en toegang vast; het
LDV legt de daadwerkelijke dataverwerking vast.

Op deze laag wordt ook een centrale loggingpipeline ingericht voor

- De verwerking van de logs uit laag 4/5

- Het creëren van logs die naar de registraties (laag 1/2) gaan.

Deze inrichting is inclusief **l**ogcollectie, processing, labeling,
routering naar de juiste storage en retrymechanismen. De service (laag
4/5) blijft verantwoordelijk voor het correct produceren van de
logregels en het behouden van de ketenbrede trace-context.

De logging hoeft daarbij niet noodzakelijk alle gegevenswaarden zelf te
bevatten. Het doel is primair om vast te kunnen stellen welke
gegevensverwerking heeft plaatsgevonden en, afhankelijk van het vereiste
niveau, welke gegevenscategorieën of concrete gegevens daarbij zijn
gebruikt.

## Generieke platformvoorzieningen

Voor bovenstaande inrichting zijn in de doelarchitectuur drie generieke
voorzieningen nodig.

#### Logboek Dataverwerkingen

Het **Logboek Dataverwerkingen** is de centrale voorziening waarin de
verwerkingslogregels ketenbreed worden verzameld.

Het LDV moet onder meer:

- Verwerkingen ketenbreed kunnen reconstrueren;

- Verwerkingen kunnen koppelen aan het verwerkingsregister;

- De autorisatiebeslissing kunnen koppelen;

- Kunnen zoeken en filteren;

- Verschillende doelgroepen gecontroleerd inzage kunnen geven;

- Bewaartermijnen ondersteunen;

- Uitlegbaarheid en inzage mogelijk maken.

#### Verwerkingenregister

Het **Verwerkingenregister** beschrijft vooraf welke verwerkingen zijn
toegestaan: welk doel de verwerking heeft en op welke grondslag deze
plaatsvindt.

Het LDV verwijst vervolgens naar deze registratie. Daardoor ontstaat de
gewenste relatie:

**beleid / doelbinding → toegestane verwerking → feitelijke verwerking →
logregel**

De doelarchitectuur beschrijft dit als de koppeling tussen het register
van verwerkingsactiviteiten en het operationele verwerkingenlog.

#### Presentatie

Bovenop het logboek komt een presentatielaag voor bijvoorbeeld:

- Inzage door de inwoner;

- Auditing;

- Toezicht en verantwoording.

De presentatievoorziening is daarbij niet zelf de bron van de logging.
Zij ontsluit informatie uit het centrale logboek, met autorisatie en
dataminimalisatie passend bij de doelgroep.

## Transitie

Er moet een transitiepad worden bepaald om huidige implementaties te
laten voldoen aan de doelarchitectuur.

## Relatie met Policy Based Access Control

Met de ontwikkeling van **PBAC (Policy Based Access Control)** en
**OpenFTV** (zie onderdeel **8. Identificatie, authenticatie en
autorisatie**) wordt een stap gezet in het platform naar een meer
samenhangende manier van toegang en logging.

Deze voorziening maakt het mogelijk om:

- Gegevensverwerkingen expliciet te koppelen aan beleid, doelbinding en
  autorisatie

- Toegang tot gegevens en het gebruik daarvan centraal en uniform te
  sturen en

- Deze handelingen structureel en herleidbaar vast te leggen

PBAC bepaalt of een gevraagde handeling is toegestaan op basis van
beleid en context. Het logboek van OpenFTV vormt geen zelfstandig
vervangend logboek voor dataverwerkingen, maar is een onderdeel van de
totale verantwoording.

Autorisatiebeslissingen worden als events opgenomen binnen de bredere
trace van een dataverwerking. Het Logboek Dataverwerkingen fungeert als
overkoepelend log, waarin:

- De autorisatiebeslissing (permit/deny) wordt vastgelegd als stap in de
  keten

- De feitelijke uitvoering van de verwerking wordt geregistreerd.

Logging van dataverwerking is ook vastgelegd als (kandidaat) **toegepast
patroon** in het onderdeel [Toegepaste patronen](#toegepaste-patronen).
