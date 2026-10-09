# 11. Toegepaste patronen

| **Compact:**                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dit hoofdstuk beschrijft herbruikbare oplossingspatronen voor veelvoorkomende vormen van dienstverlening, zoals notificaties, verzoeken, taken en berichten. Ook worden implementatiepatronen en de registratiestrategie beschreven. De gedachte is simpel: als iets vaker voorkomt, maken we er een patroon van. |

## Inleiding

In onderdeel [Samenwerking tussen services](../08-applicatiearchitectuur/#samenwerking-tussen-services) zijn de generieke interactievormen binnen het Platform Dienstverlening beschreven. Daar is onderscheid gemaakt tussen synchrone communicatie (request/response), asynchrone communicatie (event-driven) en API-compositie. Deze beschrijven op welke wijze services technisch met elkaar samenwerken.

Dit hoofdstuk beschrijft een ander abstractieniveau. De hier opgenomen patronen zijn oplossingspatronen voor veelvoorkomende functionele vraagstukken binnen de gemeentelijke dienstverlening. Zij beschrijven hoe meerdere services gezamenlijk invulling geven aan een specifieke capability, zoals het registreren van een verzoek, het uitvoeren van een taak of het verzenden van een bericht.

Een patroon bestaat daarbij uit een samenhang van registraties, API's, notificaties en procescomponenten die volgens vaste afspraken samenwerken. Een patroon kan gebruikmaken van één of meerdere interactievormen. Zo combineert het Verzoekenpatroon bijvoorbeeld a-synchrone notificaties voor de registratie van een verzoek met synchrone API-calls voor de verdere procesafhandeling.

## Notificatiepatroon

Alle interactiepatronen binnen het Platform Dienstverlening bouwen voort op hetzelfde notificatiepatroon. Componenten communiceren zoveel mogelijk asynchroon door gebeurtenissen (events) te publiceren. Andere componenten kunnen zich hierop abonneren zonder dat directe afhankelijkheden ontstaan.

Hiervoor wordt gebruikgemaakt van **Open Notificaties** die een publish/subscribe-mechanisme biedt voor het routeren van gebeurtenissen tussen componenten.

De belangrijkste uitgangspunten zijn:

* Componenten publiceren gebeurtenissen; zij kennen hun afnemers niet.
* Componenten ontvangen notificaties via abonnementen op één of meer kanalen.
* Notificaties bevatten uitsluitend verwijzingen naar gewijzigde gegevens (informatie-arm).
* De ontvangende component bepaalt zelfstandig of en hoe de gewijzigde gegevens worden opgehaald.
* Componenten moeten rekening houden met tijdelijke uitval of gemiste notificaties en implementeren daarom een passende herstelstrategie, bijvoorbeeld retries of periodieke synchronisatie.

Hierdoor ontstaat een losse koppeling tussen registraties, procescomponenten en gebruikersvoorzieningen.

## Verzoekenpatroon

Het verzoekenpatroon vormt het standaardpatroon voor het starten van dienstverlening. Het uitgangspunt is dat een aanvraag eerst als zelfstandig **Verzoek** wordt geregistreerd, voordat een proces of zaak wordt gestart. Hierdoor wordt de interactie met de inwoner losgekoppeld van de procesafhandeling.

Het patroon bestaat uit de volgende stappen:

* Een kanaal registreert een verzoek via de Verzoeken API.
* Het verzoek wordt gevalideerd.
* Het verzoek wordt opgeslagen als zelfstandig informatieobject.
* De registratie publiceert een notificatie.
* Procescomponenten bepalen zelfstandig of en welk proces moet worden gestart.

Hierdoor kunnen meerdere processen gebruikmaken van dezelfde verzoekregistratie.

#### Aansluiten op het patroon

Procescomponenten:

* Abonneren zich op relevante notificaties.
* Halen het volledige verzoek op via de API.
* Bepalen zelfstandig welk proces moet worden gestart.

## Takenpatroon

Taken worden binnen het platform niet rechtstreeks aangeboden vanuit procescomponenten, maar eerst geregistreerd als zelfstandig informatieobject. Procescomponenten zijn verantwoordelijk voor het registreren en beheren van taken; gebruikersinterfaces zijn verantwoordelijk voor het tonen en afhandelen ervan.

Hierdoor ontstaat een generieke takenvoorziening die door meerdere processen en gebruikersinterfaces kan worden hergebruikt.

#### Aansluiten op het patroon

Procescomponenten:

* Registreren taken via de Taken API.
* Koppelen taken aan het relevante hoofdobject.
* Beheren de levenscyclus van de taak.

De takenregistratie:

* Registreert de taken
* Publiceert wijzigingen via notificaties.

Portalen:

* Halen bij login van de gebruiker de taken op
* Tonen de actuele taken
* Verwerken gebruikersacties.

## Berichtenpatroon

Ook berichten worden als zelfstandig informatieobject geregistreerd voordat zij daadwerkelijk worden verzonden. Procescomponenten zijn verantwoordelijk voor **wat** moet worden gecommuniceerd; de berichtenvoorziening (Outputmanagementcomponent en Notify) bepaalt **hoe** en via welk kanaal dit gebeurt.

Het patroon bestaat uit:

* Registratie van het bericht.
* Validatie.
* Opslag.
* Publicatie van een notificatie.
* Verzending door de omnichannelvoorziening.

Hierdoor ontstaat een volledige scheiding tussen proceslogica en communicatiekanalen.

#### Aansluiten op het patroon

Procescomponenten:

* Stellen berichten inhoudelijk samen.
* Registreren deze via de Berichten API.
* Relateren berichten aan het relevante hoofdobject.

OMC/Notify:

* Abonneert zich op relevante notificaties.
* Haalt berichtgegevens op.
* Bepaalt – op basis van klantgegevens (KlantenAPI) via welk kanaal het bericht moet worden verzonden
* Verzorgt de daadwerkelijke verzending.

## Patronen in ontwikkeling

Het Platform Dienstverlening ontwikkelt zich continu. Naast de in dit onderdeel beschreven patronen kunnen nieuwe generieke interactiepatronen worden toegevoegd wanneer deze bijdragen aan een betere ontkoppeling, herbruikbaarheid of standaardisatie.

Nieuwe patronen worden ontwikkeld conform de architectuurprincipes uit dit document en maken, na vaststelling, onderdeel uit van de referentiearchitectuur van het platform. De volgende patronen zijn in 2026/27 kandidaat:

### Autorisatiepatroon (OpenFTV / AuthZEN)

Binnen het Platform Dienstverlening wordt autorisatie niet door individuele services ingericht, maar als een generieke platformvoorziening toegepast. Hiervoor wordt aangesloten op de architectuur van **OpenFTV** en de **AuthZEN-standaard**. Dit maakt het mogelijk om autorisatiebeslissingen centraal, consistent en contextafhankelijk uit te voeren.

Het uitgangspunt is dat iedere service verantwoordelijk blijft voor zijn eigen gegevens en functionaliteit, maar autorisatiebeslissingen delegeert aan de centrale autorisatievoorziening. Hierdoor worden autorisatieregels éénmaal beheerd en platformbreed toegepast.

Het patroon bestaat uit de volgende stappen:

* **Doen van een verzoek**\
  Een gebruiker of service doet een aanvraag om een bepaalde handeling uit te voeren, bijvoorbeeld het raadplegen of wijzigen van gegevens.
* **Opbouwen van de autorisatiecontext**\
  De uitvoerende service verzamelt de benodigde context, zoals:
  * De identiteit van de actor;
  * De gevraagde handeling;
  * Het betreffende object of de resource;
* **Autorisatiebeslissing**\
  De service vraagt via de AuthZEN-interface een autorisatiebeslissing op bij de centrale Policy Decision Point (PDP). Daarbij worden beleidsregels uit het Policy Administration Point (PAP) toegepast, aangevuld met gegevens uit één of meer Policy Information Points (PIP).
* **Afdwingen van de beslissing**\
  De ontvangende service fungeert als Policy Enforcement Point (PEP) en voert de beslissing uit. Alleen wanneer de beslissing _Permit_ luidt wordt de gevraagde handeling uitgevoerd.

Hierdoor ontstaat een uniforme autorisatiearchitectuur waarin beleid, uitvoering en verantwoording van elkaar zijn gescheiden.

#### Aansluiten op het patroon

Services die persoonsgegevens of andere beschermde gegevens verwerken:

* Implementeren de AuthZEN-interface voor autorisatiebeslissingen.
* Treden op als **Policy Enforcement Point (PEP)**.
* Verstrekken de benodigde context aan de centrale autorisatievoorziening.
* Respecteren de teruggegeven autorisatiebeslissing (_Permit_ of _Deny_).
* Registreren de autorisatiebeslissing als onderdeel van de ketenbrede verwerking.

### Loggingpatroon (OpenTelemetry en Logboek Dataverwerkingen)

Binnen het Platform Dienstverlening wordt logging als een generiek platformpatroon toegepast. Hierbij wordt onderscheid gemaakt tussen de technische registratie van gebeurtenissen en de juridische verantwoording van gegevensverwerkingen.

OpenTelemetry (OTel) vormt de technische standaard voor het vastleggen van logs, traces en events over de gehele keten. Het **Logboek Dataverwerkingen (LDV)** bouwt hierop voort door deze technische logging te verrijken met informatie over doelbinding, grondslag en de uitgevoerde gegevensverwerking. Hierdoor ontstaat één samenhangend beeld van een gegevensverwerking, ongeacht hoeveel services daarbij betrokken zijn.

Het patroon bestaat uit de volgende stappen:

* **Start van een verwerking**\
  Een gebruiker of service initieert een verwerking. Daarbij wordt een ketenbrede trace gestart conform de W3C Trace Context-standaard.
* **Verwerking door services**\
  Iedere service legt relevante gebeurtenissen vast volgens de OpenTelemetry-standaard. Hierbij worden onder andere de trace-id, de uitgevoerde handeling en de betrokken component geregistreerd.
* **Registratie van autorisatie en gegevensgebruik**\
  Autorisatiebeslissingen, API-aanroepen en gegevensmutaties worden als onderdeel van dezelfde trace vastgelegd. Hierdoor ontstaat een volledig beeld van de uitgevoerde verwerking.
* **Verrijking met verwerkingscontext**\
  De technische logging wordt gekoppeld aan de bijbehorende verwerkingsactiviteit uit het Verwerkingsregister. Daarbij worden onder meer doelbinding, grondslag en de aard van de gegevensverwerking vastgelegd.
* **Registratie in het Logboek Dataverwerkingen**\
  Alle relevante gebeurtenissen worden samengebracht in één platformbreed Logboek Dataverwerkingen. Hierdoor ontstaat een complete en herleidbare registratie van de uitgevoerde gegevensverwerking.

Deze werkwijze maakt het mogelijk om gegevensverwerkingen over meerdere componenten heen te reconstrueren en ondersteunt zowel operationeel beheer als wettelijke verantwoording.

#### Aansluiten op het patroon

Alle componenten binnen het Platform Dienstverlening:

* Gebruiken **OpenTelemetry** voor logging, metrics en distributed tracing.
* Propageren de **trace-id** over alle API-calls en events.
* Leggen relevante handelingen en gebeurtenissen vast conform de platformstandaard.
* Registreren autorisatiebeslissingen als onderdeel van dezelfde trace.
* Verrijken logging met de benodigde context voor het Logboek Dataverwerkingen.
* Leveren hun logging aan de centrale OTel-infrastructuur.

De centrale loggingvoorziening bestaat uit:

* **OpenTelemetry Collectors** voor het verzamelen van logs, traces en metrics;
* **OpenTelemetry Backend(s)** voor opslag en analyse;
* **Logboek Dataverwerkingen (LDV)** voor de registratie van gegevensverwerkingen;
* **Verwerkingsregister** voor de registratie van verwerkingsactiviteiten, doelbinding en grondslag.

**Uitgangspunten**

Bij de inrichting van het loggingpatroon gelden de volgende uitgangspunten:

* Iedere relevante gegevensverwerking is volledig herleidbaar over de gehele keten.
* Alle componenten gebruiken hetzelfde OpenTelemetry-formaat.
* Persoonsgegevens worden niet onnodig opgenomen in technische logging; waar mogelijk worden stabiele identifiers gebruikt.
* Het Logboek Dataverwerkingen bevat de semantische en juridische context van de verwerking en vormt de basis voor verantwoording richting inwoners, toezichthouders en auditors.
* Logging ondersteunt zowel technische observability als compliance, zonder dat hiervoor afzonderlijke loggingmechanismen per component nodig zijn.

## Implementatiepatronen (Patroon A, Patroon B)

De voorgaande paragrafen beschrijven patronen voor de samenwerking tussen services binnen het Platform Dienstverlening. In de praktijk bevindt elke gemeente zich reeds in een uitgangssituatie. Bestaande applicaties, contracten en investeringen maken dat de doelarchitectuur niet altijd in één stap kan worden gerealiseerd.

Om gemeenten hierin te ondersteunen onderscheidt het Platform Dienstverlening twee referentie-implementatiepatronen. Beide patronen streven dezelfde architectuurprincipes na en leiden uiteindelijk naar dezelfde doelarchitectuur. Het verschil zit in dat bestaande software wordt ingepast tijdens de transitie.

| **Patroon**                                       | **Beschrijving**                                                                                                                                                    | **Voorbeeld**                                                                                                                                                                         |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Patroon A – Volledig Platform Dienstverlening** | Alle lagen van het vijflagenmodel worden gerealiseerd met componenten conform de Common Ground-architectuur.                                                        | Een klachtenproces wordt volledig opgebouwd uit formulieren, procescomponenten, FSC, registraties, dataservices en omnichannelvoorzieningen.                                          |
| **Patroon B – Hybride implementatie**             | De gegevenslaag en connectiviteitslaag volgen de Common Ground-architectuur; de proceslaag wordt (tijdelijk) ingevuld door een bestaande SaaS- of legacy-oplossing. | De aanvraag van een paspoort wordt afgehandeld in een bestaande zaaksysteemcomponent, terwijl gegevens, formulieren, API's en communicatie via het Platform Dienstverlening verlopen. |

#### Duiding

Beide implementatiepatronen ondersteunen dezelfde doelarchitectuur, maar verschillen in de wijze waarop deze wordt bereikt.

* **Patroon A** realiseert de architectuur volledig volgens de uitgangspunten van Common Ground. Dit biedt maximale flexibiliteit, herbruikbaarheid en loskoppeling, maar vraagt ook de grootste organisatorische en technische verandering.
* **Patroon B** biedt een pragmatische transitiestrategie waarbij bestaande applicaties voorlopig behouden blijven, terwijl gegevens, interactie en integratie al worden georganiseerd volgens de architectuur van het Platform Dienstverlening. Hierdoor kan stapsgewijs worden toegewerkt naar Patroon A.

### Patroon A – Volledige platformimplementatie

Binnen Patroon A worden processen volledig gerealiseerd met de componenten van het Platform Dienstverlening. Zowel de interactie, procesafhandeling, connectiviteit als gegevensvoorziening volgen de architectuurprincipes uit dit document.

De implementatie bestaat doorgaans uit:

* Realiseren van de benodigde BusinessServices en procescomponenten.
* Inrichten van registraties, API's en gegevensmodellen.
* Migreren van gegevens uit bestaande systemen.
* Implementeren van de nieuwe werkwijze binnen de organisatie.

Na afronding kan de oorspronkelijke applicatie volledig worden uitgefaseerd.

* Voordelen
  * Maximale aansluiting op de doelarchitectuur.
  * Geen structurele synchronisatie tussen systemen.
  * Optimale herbruikbaarheid van services.
  * Eenvoudiger beheer op langere termijn.
* Aandachtspunten
  * Grootste implementatie-inspanning.
  * Organisatorische verandering is vaak omvangrijk.
  *   Vereist volledige migratie van processen en gegevens.

      ![Afbeelding met tekst, schermopname, diagram, Lettertype Door AI gegenereerde inhoud is mogelijk onjuist.](../.gitbook/assets/image31.png)

### Patroon B – Hybride implementatie

Patroon B is bedoeld voor situaties waarin bestaande SaaS- of legacy-oplossingen voorlopig gehandhaafd blijven. De procesuitvoering vindt daarbij plaats buiten het Platform Dienstverlening, terwijl gegevens, interactie en integratie zoveel mogelijk volgens de architectuur worden ingericht. De bestaande applicatie wordt gekoppeld aan de registraties en platformvoorzieningen, zodat de gegevenslaag al voldoet aan de uitgangspunten van Common Ground.

Hierdoor ontstaat een hybride architectuur waarin:

* Interactie plaatsvindt via de platformvoorzieningen;
* Gegevens worden beheerd in Common Ground-registraties;
* Processen voorlopig blijven draaien in de bestaande applicatie.
* Voordelen
  * Versnelt de transitie naar de doelarchitectuur.
  * Gemeenten verkrijgen regie over hun gegevens.
  * Gegevens kunnen direct worden gebruikt door andere platformvoorzieningen, zoals MijnServices en integrale klantbeelden.
  * Beperkt de impact op bestaande bedrijfsprocessen.
* Aandachtspunten
  * Tijdelijke dubbele inrichting van beheer en configuratie.
  * Extra complexiteit door gegevenssynchronisatie.
  * Hogere beheerlast zolang beide werelden naast elkaar bestaan.
  * Bedoeld als tussenstap; uiteindelijk blijft Patroon A het eindbeeld.

#### Praktische implementatiestappen

* Inrichten van de benodigde registraties binnen het Platform Dienstverlening.
* Realiseren van API-koppelingen tussen de bestaande applicatie en de platformregistraties.
* Inrichten en testen van de gegevenssynchronisatie.
* Gefaseerd overnemen van functionaliteit totdat de bestaande applicatie kan worden uitgefaseerd.

![Afbeelding met tekst, schermopname, lijn, Lettertype Door AI gegenereerde inhoud is mogelijk onjuist.](../.gitbook/assets/image32.png)

## Registratiestrategie: één bron per informatiedomein

Een belangrijk uitgangspunt binnen het Platform Dienstverlening is dat iedere organisatie voor ieder generiek informatiedomein één primaire registratie gebruikt. Voor zaakgegevens betekent dit dat binnen één gemeente wordt gestreefd naar **één centraal zaakregister**, waarop alle processervices aansluiten. Hetzelfde uitgangspunt geldt voor andere generieke registraties, zoals klanten, producten en organisaties.

* Door één registratie als bron te gebruiken ontstaat:
* Een eenduidige bron van waarheid (single source of truth);
* Uniform beheer van gegevens, typen en metadata;
* Eenvoudige ontsluiting naar MijnOmgeving, klantbeelden en andere generieke voorzieningen;
* Minder beheer- en integratiecomplexiteit;
* Grotere uitwisselbaarheid van processen en softwarecomponenten.

#### Niet gewenste situaties

De volgende implementatievormen passen niet binnen de architectuur van het Platform Dienstverlening:

* Applicaties die uitsluitend met hun **eigen registratie** kunnen samenwerken en geen gebruikmaken van de gestandaardiseerde registraties.
* Oplossingen waarbij dezelfde gegevens gelijktijdig in meerdere registraties worden beheerd.
