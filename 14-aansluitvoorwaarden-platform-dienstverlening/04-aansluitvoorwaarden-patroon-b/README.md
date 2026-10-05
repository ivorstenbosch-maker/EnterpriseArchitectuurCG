# Aansluitvoorwaarden Patroon B

Deze aansluitvoorwaarden zijn van toepassing op oplossingen die als
applicatie aansluiten op het Platform Dienstverlening (Common Ground).
Zij zijn aanvullend op de
[GIBIT](https://vng.nl/sites/default/files/2026-03/gibit-2025-artikelen.pdf).
Voor alle contractuele, juridische, organisatorische en generieke
kwaliteitseisen geldt de GIBIT, tenzij in deze aansluitvoorwaarden
aanvullende of afwijkende platformspecifieke eisen zijn opgenomen.

De aansluitvoorwaarden bevatten de functionele, niet-functionele en
technische eisen die waarborgen dat een oplossing op een uniforme,
veilige en beheerbare wijze samenwerkt met het Platform Dienstverlening.

### Gegevenslaag 

Het Platform Dienstverlening levert de generieke gegevenslaag van de
gemeentelijke informatievoorziening. Deze bestaat uit generieke
registraties, dataservices en de integratielaag voor veilige en
gestandaardiseerde gegevensuitwisseling. Procesapplicaties sluiten
hierop aan en maken voor het vastleggen, muteren en raadplegen van
gemeentelijke gegevens gebruik van deze generieke voorzieningen.

De gegevenslaag wordt gefaseerd uitgebreid. Uiteindelijk wordt het
volledige Gemeentelijk Gegevensmodel (GGM) hierin gerealiseerd.

Op dit moment zijn de volgende generieke registraties beschikbaar:

- Klanten (Partijen – inwoners en organisaties);

- Zaken;

- Documenten;

- Producten;

- Beslisregels;

- Objecten;

- Verzoeken, Taken en Berichten.

In ontwikkeling zijn registraties voor:

- De interne organisatie (teams, functies, rollen en medewerkers);

- Domeinspecifieke gegevensmodellen voor het Sociaal Domein
  (Participatie en Inburgering).

### Algemene eisen

Iedere aangesloten oplossing voldoet aan de volgende uitgangspunten voor
de gegevenslaag:

- **Eis** – Informatieobjecten die binnen het Platform Dienstverlening
  worden **opgevraagd,** **vastgelegd of gemuteerd**, volgen het
  gegevensmodel en de metadatering van de betreffende registratie.
  Hiermee wordt geborgd dat wordt voldaan aan de eisen voor duurzame
  toegankelijkheid, informatiebeheer en interoperabiliteit.

- **Eis** – Wanneer een oplossing verantwoordelijk is voor het
  **opvragen,** **vastleggen of muteren** van gegevens in een
  registratie, draagt zij er zorg voor dat deze registratie actueel,
  volledig en consistent blijft. De betreffende registratie blijft
  daarmee de authentieke bron van deze gegevens.

### Gebruik van generieke registraties

Wanneer een oplossing verantwoordelijk is voor het **opvragen,**
**vastleggen of muteren** van gegevens binnen één van de onderstaande
domeinen, maakt zij gebruik van de daarvoor aangewezen generieke
registratie of voorziening van het Platform Dienstverlening.

Bij de oplossing moet het interne informatiemodel logisch worden gemapt
naar de Common Ground-domeinen. Concreet betekent dit het aansluiten op
de volgende standaarden:

- **Klantgegevens** hebben als bron **OpenKlant** (Klantinteracties- en
  Contactgegevens API) ([OpenKlant
  GitHub](https://github.com/maykin../../media/open-klant)).

- **(Instanties van) Producten en diensten** hebben als bron
  **OpenProduct** ([OpenProduct)
  GitHub](https://github.com/maykin../../media/open-product)).

- **Zaken** hebben als bron **OpenZaak** ([OpenZaak
  GitHub](https://github.com/open-zaak/open-zaak))

  - **Onderdeel** daarvan is ook de **Documenten API**

- **Verzoeken**, **Taken** en **Berichten** hebben als bron **OpenVTB**
  en volgen respectievelijk het Verzoeken-, Taken- en Berichtenpatroon
  ([OpenVTB GitHub](https://github.com/maykin../../media/open-vtb)).

De actuele documentatie en API-specificaties zijn beschikbaar via de
GitHub links.

#### Aansluitpatronen

Iedere aangesloten oplossing past de functionele en technische
aansluitpatronen toe zoals beschreven in de [Enterprisearchitectuur
Platform
Dienstverlening](https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/enterprisearchitectuur).
Deze patronen beschrijven de uniforme wijze waarop applicaties
samenwerken met registraties, API's en andere platformvoorzieningen.

#### Eisen

- **Eis –** Aangesloten oplossingen integreren met Keycloak via OpenID
  Connect (OIDC) zodat gebruikers van het platform zonder aanvullende
  authenticatiestappen toegang krijgen tot de aangesloten oplossing. 

- **Eis –** De oplossing past de functionele en technische
  aansluitpatronen toe zoals beschreven in de Enterprisearchitectuur
  Platform Dienstverlening.

- **Eis –** Gegevensuitwisseling tussen applicaties en registraties
  vindt plaats via de voorgeschreven API-, interactie- en eventpatronen
  van het Platform Dienstverlening.

- **Eis –** Bij het realiseren van nieuwe functionaliteit worden de
  architectuurprincipes en aansluitpatronen van het Platform
  Dienstverlening gevolgd.

#### Nieuwe registraties en versies

Het Platform Dienstverlening wordt continu doorontwikkeld. Leveranciers
worden geacht nieuwe generieke registraties en nieuwe versies van
bestaande registraties tijdig te ondersteunen, zodat aangesloten
applicaties compatibel blijven met de referentiearchitectuur.

- **Eis –** Wanneer binnen het Platform Dienstverlening een voor de
  oplossing relevante nieuwe generieke registratie of een nieuwe versie
  van een bestaande registratie de status **'In gebruik'** bereikt,
  ondersteunt de leverancier deze registratie uiterlijk zes maanden
  nadat deze status is bereikt.

#### Gebruik van brongegevens

Common Ground gaat uit van het principe **data bij de bron**. Gegevens
worden waar mogelijk rechtstreeks geraadpleegd vanuit de authentieke
registratie. Het structureel dupliceren van gegevens wordt zoveel
mogelijk voorkomen.

- **Wens –** Gegevens die via gestandaardiseerde API's realtime
  beschikbaar zijn vanuit een registratie of andere bronvoorziening
  worden niet structureel gekopieerd of structureel lokaal opgeslagen.
  Bij de uitvoering van een handeling in een afhandelcomponent worden de
  gegevens opgehaald uit de gegevenslaag en weer teruggeschreven in de
  gegevenslaag.

### Integratielaag

Naast de gegevenslaag maakt iedere aangesloten oplossing gebruik van de
generieke platformvoorzieningen voor gegevensuitwisseling,
observability, authenticatie en autorisatie.

- **Eis** – Communicatie met andere componenten verloopt via
  [Federatieve Service Connectiviteit
  (FSC).](https://docs.open-fsc.nl/introduction)

- **Eis** – Gebeurtenissen worden geconsumeerd via **Open
  Notificaties**, conform het notificatiepatroon ([Open Notificaties
  GitHub](https://github.com/open-zaak/open-notificaties)).

- **Eis** – Logging en telemetry volgen
  [OpenTelemetry](https://opentelemetry.io/docs/what-is-opentelemetry/).

#### Platformbrede voorzieningen

De onderstaande platformvoorzieningen bevinden zich nog in ontwikkeling.
Vanaf zes maanden nadat een voorziening de status **'In gebruik'** heeft
bereikt, gelden de volgende aanvullende aansluitvoorwaarden:

- [OpenFTV/AuthZEN](https://vng-realisatie.github.io/ftv/) – Autorisatie
  maakt gebruik van de centrale voorziening voor federatieve
  authenticatie en autorisatie

- [Logboek
  Dataverwerkingen](https://github.com/Logius-standaarden/logboek-dataverwerkingen)
  – De oplossing registreert gegevensverwerkingen via het centrale
  Logboek Dataverwerkingen.
