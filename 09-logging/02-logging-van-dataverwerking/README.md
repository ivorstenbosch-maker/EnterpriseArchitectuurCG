# Logging van dataverwerking

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
