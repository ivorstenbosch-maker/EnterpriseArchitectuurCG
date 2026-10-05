# Rapportage, datawarehousing & Platform Dienstverlening

Verschillende stakeholders – zoals medewerkers, behandelaren,
management, bestuur en externe partners (bijvoorbeeld het CBS) – hebben
behoefte aan inzicht in het verloop van processen. Deze informatie is
essentieel voor beleidsvorming, het beoordelen van prestaties, het
verdelen van werkdruk en het bepalen van urgentie.

### Voorwaarden in ontwerp en architectuur

Een effectieve en betrouwbare ontsluiting van data begint bij de
inrichting van de software. Daarbij gelden de volgende randvoorwaarden:

- **Eenduidige en doordachte datamodellering**

  Voorafgaand aan het configureren en bouwen van services en
  registraties moeten duidelijke keuzes worden gemaakt over
  datamodellen, entiteiten en relaties. Dit voorkomt
  interpretatieverschillen en maakt hergebruik van data mogelijk.

- **Consistente procesinrichting en service-interacties**

  Er moet expliciet zijn vastgelegd welke processtappen leiden tot welke
  servicecalls en welke gegevens in welke registraties worden
  vastgelegd. Alleen dan ontstaat een betrouwbare en complete
  datagrondslag voor zowel operationele overzichten als rapportages.

- **Vroegtijdige validatie en testbaarheid**

  Softwareontwikkeling, data-extractie en rapportagevoorzieningen worden
  integraal en vanaf het begin van het traject ontworpen en gevalideerd.
  Dit is noodzakelijk om te waarborgen dat data volstaat voor
  uiteenlopende doeleinden.

- **Documentatie en transparantie**

  Datadefinities, datatypen, eenheden en formaten, herkomst (lineage) en
  gebruiksdoelen moeten goed worden gedocumenteerd. Dit ondersteunt
  correct gebruik en voorkomt verschillende interpretaties van dezelfde
  data.

- **Koppeling met KPI’s en sturingsinformatie**

  De business moet voorafgaand aan de ontwikkeling expliciet aangeven
  welke KPI’s en controlemechanismen relevant zijn, en hoe die relateren
  aan het informatiemodel. Op basis daarvan kan worden bepaald:

  - Welke datapunten noodzakelijk zijn

  - Waar in het proces deze worden vastgelegd

  - En hoe deze later ontsloten worden voor rapportage

  - Op basis van welke grondslag.

> Deze aanpak borgt dat data niet achteraf “bij elkaar gezocht” hoeft te
> worden, maar by design beschikbaar is voor zowel operationele sturing
> als strategische rapportage.

### Overzichten versus rapportages

Binnen deze informatiebehoefte wordt een fundamenteel onderscheid
gemaakt tussen **operationele overzichten** en **rapportages**.

**Operationele overzichten** bieden een actuele, beknopte weergave van
gegevens in tabel- of lijstvorm, zonder historische context of
trendanalyse. Ze zijn nadrukkelijk handelingsgericht: het doel is om te
sturen op het behalen van doelstellingen in de dagelijkse uitvoering,
zoals het binnen termijnen houden van werk, het voorkomen van
achterstanden en het tijdig oppakken van urgente zaken.

Deze overzichten ondersteunen direct de workflow en kunnen daarin ook
actief worden ingezet, bijvoorbeeld door:

- Het tonen van geprioriteerde werklijsten

- Het zichtbaar maken van urgente of achterstallige dossiers

- Het suggereren van eerstvolgende acties of op te pakken werk

- Het bieden van inzicht in werkvoorraden en capaciteit.

Operationele overzichten manifesteren zich in de praktijk als lijstwerk,
werkschermen en lichte dashboarding binnen applicaties. Ze zijn daarmee
een integraal onderdeel van de uitvoering en operationele sturing.

**Operationele overzichten** zijn onderdeel van de **processervices**
(of ‘taakapplicaties). Dit is de plek waar het werk daadwerkelijk wordt
uitgevoerd en waar beslissingen over prioritering en werkverdeling
worden genomen. Dit betekent dat bij het ontwerp en de implementatie van
processervices expliciet rekening moet worden gehouden met de
beschikbaarheid van actuele, direct bruikbare data in de juiste vorm,
zodat applicaties (zoals GZAC) deze informatie kunnen gebruiken binnen
de workflow.

**Rapportages** daarentegen voorzien in tactische en strategische
sturingsinformatie. Zij bieden inzicht in KPI’s, historische
ontwikkelingen, trends en prestaties over langere perioden. Rapportages
combineren gegevens uit meerdere processen en bronnen en maken analyse
en verantwoording mogelijk. Daarmee dienen zij een wezenlijk ander doel
dan operationele overzichten en zijn zij nadrukkelijk geen onderdeel van
de operationele procesondersteuning.

Binnen de referentie-architectuur worden rapportages gerealiseerd via
een afzonderlijke **rapportageketen (datawarehouse)**. In deze keten
wordt data uit verschillende bronservices verzameld, gevalideerd,
getransformeerd en geïntegreerd. Vervolgens wordt deze data ontsloten in
een vorm die geschikt is voor analyse, dashboards en
managementinformatie.

Deze scheiding borgt dat:

- Operationele processen beschikken over actuele, handelingsgerichte en
  workflow-ondersteunende informatie

- Rapportagevoorzieningen kunnen optimaliseren voor consistentie,
  historie en analysemogelijkheden.

### Omgang met persoonsgegevens (PII)

Persoonsgegevens worden verwerkt conform de beginselen van de Algemene
Verordening Gegevensbescherming (AVG). Deze beginselen worden binnen het
Platform Dienstverlening vanaf het ontwerp toegepast (*privacy by
design*).

- **Rechtmatigheid, behoorlijkheid en transparantie**  
  Persoonsgegevens worden uitsluitend verwerkt op basis van een geldige
  wettelijke grondslag. De verwerking is transparant, herleidbaar en
  uitlegbaar voor inwoners.

- **Doelbinding**  
  Persoonsgegevens worden uitsluitend verwerkt voor een expliciet
  omschreven en gerechtvaardigd doel. Hergebruik voor andere doeleinden
  vindt alleen plaats wanneer hiervoor een rechtmatige grondslag
  bestaat.

- **Dataminimalisatie**  
  Alleen persoonsgegevens die noodzakelijk zijn voor het beoogde doel
  worden verwerkt. Voor rapportages en analyses wordt waar mogelijk
  gebruikgemaakt van geaggregeerde, gepseudonimiseerde of
  geanonimiseerde gegevens.

- **Juistheid**  
  Persoonsgegevens worden beheerd bij de aangewezen bron en waar nodig
  geactualiseerd. BusinessServices gebruiken brongegevens en voorkomen
  onnodige duplicatie, zodat de kwaliteit van gegevens behouden blijft.

- **Opslagbeperking**  
  Persoonsgegevens worden niet langer bewaard dan noodzakelijk.
  Bewaartermijnen, vernietiging en – waar wettelijk vereist –
  overbrenging worden ondersteund door de generieke voorzieningen voor
  duurzame toegankelijkheid.

- **Integriteit en vertrouwelijkheid**  
  Persoonsgegevens worden passend beschermd tegen ongeautoriseerde
  toegang, wijziging of verlies. Gevoelige gegevens worden standaard
  versleuteld opgeslagen en beveiligd tijdens transport. Toegang vindt
  uitsluitend plaats op basis van expliciete autorisatie, waarbij
  logging en auditing integraal onderdeel zijn van de architectuur.

#### Dataminimalisatie en doelbinding

Persoonsgegevens worden uitsluitend verwerkt voor een expliciet
gedefinieerd en rechtmatig doel en beperkt tot wat daarvoor noodzakelijk
is. Voor rapportagedoeleinden wordt kritisch beoordeeld of
persoonsgegevens überhaupt nodig zijn; waar mogelijk wordt gewerkt met
geaggregeerde, gepseudonimiseerde of geanonimiseerde gegevens.
Persoonsgegevens worden standaard versleuteld opgeslagen en uitsluitend
ontsloten aan geautoriseerde gebruikers en services overeenkomstig de
geldende autorisatie- en beveiligingskaders.

#### Scheiding tussen operationeel en analytisch gebruik

PII wordt primair verwerkt binnen operationele systemen
(processervices). In de rapportageketen (datawarehouse) wordt het
gebruik van direct herleidbare persoonsgegevens vermeden.

#### Pseudonimisering en anonimisering

Indien persoonsgegevens noodzakelijk zijn voor analyse, worden deze bij
voorkeur gepseudonimiseerd (bijv. via sleutels of hashing). Het platform
voorziet nog niet in deze functionaliteit, en die ligt momenteel dus
extern (in deze context bij de gemeentelijke datavoorziening).

#### Toegangsbeheer en autorisatie

Toegang tot datasets met PII is strikt gereguleerd en gebaseerd op
rollen en noodzaak (need-to-know). Analytische omgevingen maken gebruik
van fijnmazige autorisatie, waarbij onderscheid wordt gemaakt tussen
gebruikersgroepen (bijv. operationeel, analytisch, extern).

#### Dataretentie en lifecycle management

Ook voor persoonsgegevens worden duidelijke bewaartermijnen gehanteerd.
In analytische omgevingen worden gegevens niet langer bewaard dan
noodzakelijk en waar mogelijk tijdig verwijderd of geanonimiseerd.

#### Gebruik van testdata

In ontwikkel- en testomgevingen wordt geen gebruik gemaakt van echte
persoonsgegevens. Er wordt gewerkt met synthetische of geanonimiseerde
datasets.

### Exports voor externe partijen (bijv. CBS)

Gemeenten moeten in sommige context rapportages over hun processen
aanleveren bij gerelateerde instanties, zoals het CBS (voorbeeld:
<https://www.cbs.nl/nl-nl/deelnemers-enquetes/decentrale-overheden/overzicht/wet-inburgering>).
Dit verplicht gemeenten om maandelijks een CSV-bestand aan te leveren
met een snapshot van alle personen binnen een proces, inclusief PII
(persoonsgegevens) en statusinformatie.

#### Positionering in de architectuur

De CBS-aanlevering wordt gepositioneerd binnen de rapportageketen
(datawarehouse) en nadrukkelijk niet binnen de operationele
processervices. Dit voorkomt dat:

- Operationele systemen worden belast met extractielogica

- Er ongecontroleerde extracties van persoonsgegevens plaatsvinden.

Het datawarehouse fungeert als de enige bron (“single point of truth”)
voor de samenstelling van de CBS-levering.

#### Inrichting van de dataflow

De aanbevolen inrichting bestaat uit de volgende stappen:

1.  **Bronregistratie (processervices / registraties)** Gegevens worden
    vastgelegd conform procesinrichting, inclusief relevante statussen
    en (noodzakelijke) persoonsgegevens.

2.  **Ontsluiting naar datawarehouse** Data wordt via replica’s
    ontsloten naar het datawarehouse.Binnen Haven+ is dat
    CloudNativePG-kopie, die structureel up-to-date wordt gehouden en
    een parallelle bron geeft voor ander type (bulk) bevragingen.

3.  **Historisering en peildatumlogica** In het datawarehouse wordt
    expliciet voorzien in:

- Historisering van statussen

- Het kunnen bepalen van een peildatum (snapshotdatum)

- Reproduceerbaarheid van eerdere snapshots.

4.  **CBS-specifieke datamart / extractielaag** Er worden aparte,
    logisch afgebakende datasets ingericht waarin:

- Alleen de voor CBS benodigde velden worden opgenomen

- Datadefinities expliciet zijn vastgelegd conform CBS-specificaties

- Transformaties (bijv. coderingen, afleidingen) eenduidig plaatsvinden.

5.  **Generatie van de CSV (geautomatiseerd)** De maandelijkse levering
    wordt volledig geautomatiseerd:

- Selectie op basis van peildatum

- Export naar CSV-formaat conform CBS-specificaties.

#### Gescheiden verwerkingszone

Richt ook binnen het datawarehouse een afgeschermde zone in voor
datasets met PII die bestemd zijn voor externe levering. Toegang tot de
CBS-dataset en extractieprocessen is beperkt tot een zeer kleine,
geautoriseerde groep. Elke extractie en levering wordt gemonitord en
gelogd, conform de eisen die [BIO (Baseline Informatiebeveiliging
Overheid)](https://www.bio-overheid.nl/bio2/bio-producten/baseline-informatiebeveiliging-overheid-2-bio2/)
stelt.

Overweeg om de deze aanlevering te positioneren als een
gestandaardiseerd dataproduct binnen de organisatie:

- Met een duidelijke eigenaar

- Met expliciete SLA’s (tijdigheid, kwaliteit) en

- Met vaste definities.

### Ontsluiten van data voor rapportage

Binnen de huidige Common Ground-implementaties stellen registraties
primair operationele API’s beschikbaar. Deze API’s zijn ontworpen voor
transactieverwerking en het ondersteunen van processtappen binnen
applicatieprocessen. Hoewel deze API’s technisch gebruikt kunnen worden
voor het vullen van een landing zone of datawarehouse (bijvoorbeeld door
middel van iteratief ophalen/looping), is dit vanuit architectuur- en
performanceperspectief niet optimaal. Dit leidt tot onnodige belasting
van bronsystemen, inefficiënte dataverwerking en verhoogde complexiteit
in dataplatformen.

Om datagebruik beter te faciliteren, wordt binnen Haven+ voorzien in
alternatieve ontsluitingsmechanismen. Zo worden via CloudNativePG
replica-databases beschikbaar gesteld.

CloudNativePG is een Kubernetes-operator voor PostgreSQL die het
mogelijk maakt om databases als schaalbare en beheersbare cloud-native
workloads te draaien. Hierbij worden primaire databases (de operationele
registraties) automatisch gerepliceerd naar één of meerdere
read-replica’s. Deze replica’s worden continu gesynchroniseerd via
streaming replication en bevatten daardoor een (near) real-time
afspiegeling van de brondatasets.

Door deze architectuur ontstaat een duidelijke scheiding tussen:

- **Transactionele belasting** op de primaire databases (ten behoeve van
  procesvoering en API’s)

- **Analytische belasting** op de replica’s (ten behoeve van rapportage
  en data-analyse).

De replica-databases zijn specifiek bedoeld voor analytische doeleinden
en worden ontsloten voor datateams binnen gemeenten. Zij kunnen hierop
eigen queries uitvoeren, datasets samenstellen en data extraheren voor
verdere verwerking in bijvoorbeeld een datawarehouse of dataplatform,
zonder impact op de performance, stabiliteit en beschikbaarheid van de
operationele processen en API’s.

Daarnaast voorziet de roadmap van Common Ground-registraties in
uitbreidingen waarmee data efficiënter en doelgerichter ontsloten kan
worden voor analyse- en rapportagedoeleinden. Hiervoor zijn
verschillende implementatievarianten mogelijk:

- **Bulk Data API (Data API)** Een API gericht op het in één keer
  ontsluiten van volledige datasets of relevante deelverzamelingen
  (bijvoorbeeld per domein of periode). Dit voorkomt inefficiënte
  looping en maakt initiële vulling van een datawarehouse eenvoudiger en
  betrouwbaarder.

- **Delta API (wijzigingen sinds tijdstip X)** Een API die uitsluitend
  mutaties (inserts, updates, deletes) sinds een bepaald moment
  retourneert. Dit ondersteunt efficiënte incrementele laadprocessen en
  sluit aan bij gangbare datawarehouse-principes zoals change data
  capture (CDC).

- **Event-driven ontsluiting (event streams / notificaties)**
  Registraties publiceren gebeurtenissen (events) bij wijzigingen,
  bijvoorbeeld via messaging of event streaming (zoals Kafka-achtige
  patronen). Dataplatformen kunnen deze events consumeren en verwerken
  tot analytische datasets.

- **Voorgedefinieerde extracties / ETL-services** Door de leverancier of
  infrastructuur aangeboden extracties (bijvoorbeeld periodieke dumps of
  downloadbare datasets) die met minimale inspanning kunnen worden
  ingeladen in een datawarehouse.

<img
src="../../media/media/image20.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />
