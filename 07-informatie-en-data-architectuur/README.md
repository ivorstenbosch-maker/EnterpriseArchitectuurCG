# 7. Informatie- en data-architectuur

| **Compact:** |
|----|
| Dit hoofdstuk beschrijft hoe informatie wordt georganiseerd vanuit de werkelijkheid die de gemeente wil registreren, met duidelijke domeinen en gestandaardiseerde ontsluiting vanuit aangewezen bronnen. Informatie moet vindbaar, beschikbaar, leesbaar, interpreteerbaar, betrouwbaar en toekomstbestendig zijn. Een bron is daarbij niet alleen een plek waar data staat, maar heeft een duidelijke verantwoordelijkheid voor de inhoud, kwaliteit, betekenis en levenscyclus van de gegevens. Gegevens worden via gestandaardiseerde diensten ontsloten. |

## Inleiding

De informatie- en dataarchitectuur beschrijft hoe gegevens binnen het
Platform Dienstverlening worden georganiseerd, beheerd en beschikbaar
gesteld. Binnen TOGAF vormt dit de brug tussen de bedrijfsarchitectuur
en de applicatiearchitectuur. Zij vertaalt de informatiebehoefte vanuit
de dienstverlening naar een samenhangende inrichting van begrippen,
gegevensmodellen, registraties en gegevensuitwisseling.

Dit onderdeel beschrijft deze architectuur op hoofdlijnen. Net als bij
de bedrijfsarchitectuur worden niet alle gemeentelijke gegevensmodellen
uitgewerkt. In plaats daarvan worden de generieke uitgangspunten,
ontwerpprincipes en methodiek beschreven waarmee project- en
solutionarchitecturen consistente informatie- en data-architecturen
kunnen ontwikkelen die aansluiten op het Platform Dienstverlening.

Dit onderdeel beschrijft ook niet de volledige inrichting van
datamanagement, informatiebeheer of recordmanagement. Daarvoor bestaan
bestaande kaders zoals de Archiefwet, DUTO, NORA, GEMMA, de
Selectielijst gemeenten en gemeentelijk informatiebeheerbeleid. Dit
hoofdstuk beschrijft uitsluitend de architectuurprincipes en
ontwerpimplicaties die volgen uit een architectuur waarin informatie
verdeeld is over zelfstandige registraties en services.

## Informatiegericht werken

Volgens de visie wordt de informatiearchitectuur niet primair opgebouwd
vanuit applicaties of processen, maar vanuit de werkelijkheid die
gemeenten administreren. Personen, organisaties, producten, zaken,
besluiten, objecten en andere bedrijfsobjecten worden als
bedrijfsobjecten gemodelleerd die op zichzelf een domein vormen, en
vervolgens via gestandaardiseerde services beschikbaar gesteld aan
BusinessServices, MijnServices en andere toepassingen. Dit volgt het
principe:

> **[Principe: Informatiegericht
> werken](../05-visie-principes-scope/README.md#principe-informatiegericht-werken):** Informatie vormt het
> verbindende element tussen dienstverlening, processen, applicaties en
> organisatie. Gegevens worden onafhankelijk van individuele processen
> en applicaties beheerd, zodat zij meervoudig kunnen worden gebruikt
> voor uitvoering, dienstverlening en besluitvorming.

Hierin zijn de volgende begrippen relevant:

- **Informatie** is de betekenis die mensen aan gegevens geven binnen
  een bepaalde context. Om deze betekenis eenduidig vast te leggen,
  wordt gebruikgemaakt van begrippen, definities en informatiemodellen.
  Hierbij vormt het datamodel
  ([MIM](https://docs.geostandaarden.nl/mim/mim/)) de richtlijn voor het
  vastleggen van de structuur van gegevens, terwijl het begrippenkader
  ([NL-SBB](https://docs.geostandaarden.nl/nl-sbb/nl-sbb/)) de betekenis
  van deze gegevens vastlegt.

- **Data (gegevens)** is de concrete vastlegging van waarnemingen of
  beweringen over objecten. Binnen het Platform Dienstverlening betreft
  dit de opslag, het beheer en de uitwisseling van gegevens via
  registraties en gestandaardiseerde dataservices. Gegevens vormen de
  basis waaruit informatie kan worden afgeleid.

**Applicaties** zijn softwarecomponenten die gegevens verwerken en
functionaliteit aanbieden ter ondersteuning van bedrijfsprocessen en
dienstverlening. Dit onderscheid zorgt ervoor dat:

- Betekenis (informatie) niet afhankelijk is van technische
  implementatie (applicatie)

<!-- -->

- Gegevens consistent en herbruikbaar kunnen worden toegepast over
  verschillende processen en systemen

- Wijzigingen in één laag (bijvoorbeeld applicaties) beperkt effect
  hebben op andere lagen

- Een gemeenschappelijk begrip ontstaat tussen verschillende
  stakeholders en rollen, zoals business, architectuur en development,
  doordat zij vanuit dezelfde begrippen en modellen werken

## Expliciete bedrijfslogica

De informatiearchitectuur geeft ook uitdrukking aan het [**Principe:
Expliciete bedrijfslogica**](../05-visie-principes-scope/README.md#principe-expliciete-bedrijfslogica):
Bedrijfslogica wordt expliciet gemodelleerd en losgekoppeld van
processen, gegevens en softwarecomponenten. Regels die voortkomen uit
wetgeving, beleid of gemeentelijke afspraken worden éénmalig vastgelegd,
centraal beheerd en meervoudig toegepast.

Beslisregels vormen een zelfstandig bedrijfsobject binnen deze
architectuur. Zij beschrijven de formele vertaling van wet- en
regelgeving of beleid naar uitvoerbare logica. Beslisregels kennen een
eigen levenscyclus, versiebeheer, geldigheidsperiode en metadata. Dat
heeft de volgende implicaties:

- Beslisregels vormen een expliciet onderdeel van de dienstverlening en
  beschrijven hoe wetgeving en beleid worden toegepast.

- Beslisregels zijn versieerbaar en historisch reproduceerbaar.

- Beslisregels zijn begrijpelijk voor beleidsmedewerkers, juristen en
  uitvoerende professionals.

## Data-autonomie

Autonomie wordt door
[DICTU](https://www.dictu.nl/sites/default/files/bestanden/website/DICTU%20Toetsingsinstrument%20Soevereiniteit%20Clouddiensten%20v1.0.1.pdf)
gedefinieerd als de combinatie van zelfbeschikking en onafhankelijkheid.
Voor data-autonomie betekent dit dat zowel gemeenten als inwoners
zeggenschap behouden over hun gegevens en kunnen bepalen hoe deze worden
vastgelegd, gebruikt, gedeeld en beheerd. Dit is vastgelegd in **het
[Principe: Data-autonomie](../05-visie-principes-scope/README.md#principe-data-autonomie)**, en dit wordt
hier uitgewerkt.

Data-autonomie kent drie samenhangende aspecten:

- **Zelfbeschikking**  
  Zowel gemeenten als inwoners behouden invloed op het gebruik van
  gegevens binnen de kaders van wet- en regelgeving. Inwoners kunnen
  inzicht krijgen in het gebruik van hun gegevens en waar mogelijk
  invloed uitoefenen op de inhoud en de wijze waarop gegevens worden
  verwerkt.

- **Duurzame zeggenschap**  
  Gemeenten behouden duurzame zeggenschap over hun gegevens. Zij bepalen
  hoe gegevens worden vastgelegd, gebruikt, gedeeld en beheerd, ook
  wanneer de technische uitvoering door leveranciers of andere partijen
  wordt verzorgd. Regie gaat daarmee verder dan eigenaarschap of beheer;
  het betreft het vermogen om richting te geven aan de gehele
  levenscyclus van gegevens.

<!-- -->

- **Onafhankelijkheid**  
  Gegevens blijven beschikbaar, overdraagbaar en toegankelijk,
  onafhankelijk van een specifieke leverancier, applicatie of technische
  implementatie.

  Deze aspecten kennen zowel een dimensie van **weerbaarheid** als van
  **regie**. Enerzijds betekent data-autonomie dat gemeenten en inwoners
  beschermd zijn tegen ongewenste afhankelijkheden van leveranciers,
  technologie of organisaties. Anderzijds betekent data-autonomie dat
  gemeenten daadwerkelijk in staat zijn om zélf richting te geven aan
  hun informatievoorziening: door afspraken te maken over gegevens,
  standaarden en architectuur en deze gezamenlijk te ontwikkelen en toe
  te passen. Autonomie is daarmee niet alleen een vorm van
  onafhankelijkheid, maar ook een de kracht om dienstverlening en
  informatievoorziening actief te kunnen sturen.

Om deze autonomie daadwerkelijk te kunnen realiseren, zijn op
verschillende niveaus architectuurkeuzes en standaarden noodzakelijk.
Binnen het Platform Dienstverlening krijgt data-autonomie daarom
invulling op de volgende niveaus:

- **Semantisch niveau** (standaardisatie van betekenis)

  - Bijvoorbeeld: begrippen als “zaak”, “verzoek” of “bericht” hebben
    een eenduidige definitie en worden overal op dezelfde manier
    geïnterpreteerd, ongeacht welk systeem of domein deze gebruikt.

- **Logisch en functioneel niveau** (inrichting van dataservices en
  registraties)

  - Bijvoorbeeld: gegevens over zaken of klanten worden niet in meerdere
    applicaties opgeslagen, maar centraal ontsloten via registraties en
    API’s, zodat verschillende processen dezelfde bron gebruiken.

<!-- -->

- **Technisch en infrastructureel niveau** (hosting en beheer van
  componenten)

  - Bijvoorbeeld: de gemeente heeft regie over waar en hoe data en
    services draaien, door gebruik te maken van open en overdraagbare
    infrastructuur. Denk hierbij aan inzet van Kubernetes en open-source
    beheertools. Hierdoor kunnen componenten relatief eenvoudig worden
    verplaatst tussen omgevingen of leveranciers

  - Dit maakt het mogelijk om bewust om te gaan met het gebruik van
    cloudleveranciers en waar nodig onafhankelijk te blijven van
    (niet-Europese) hyperscalers, of deze gecontroleerd en uitwisselbaar
    in te zetten.

#### Eigenaarschap

Hoewel vaak wordt gesproken over "data van de gemeente", wordt daarmee
geen goederenrechtelijk eigendom bedoeld. Naar [Nederlands
recht](https://uitspraken.rechtspraak.nl/details?id=ECLI:NL:RBAMS:2023:2540&showbutton=true&keyword=ECLI%253aNL%253aRBAMS%253a2023%253a2540&idx=1)
zijn digitale gegevens in beginsel geen zaken in de zin van het
Burgerlijk Wetboek en kunnen zij daarom niet als zodanig in eigendom
toebehoren. Rechten, plichten en bevoegdheden ten aanzien van gegevens
vloeien voort uit wet- en regelgeving, contractuele afspraken en de
verantwoordelijkheid die organisaties hebben als bronhouder,
verwerkingsverantwoordelijke of beheerder. De term *eigenaarschap* moet
daarom worden gebruikt in de betekenis van bestuurlijke en
organisatorische verantwoordelijkheid, niet als civielrechtelijk
eigendom. Dit volgt [GIBIT Artikel
21](https://vng.nl/sites/default/files/2026-03/gibit-2025-artikelen.pdf)
(‘Intellectueel eigendom’).

### Implicaties voor de architectuur

In de huidige situatie ligt de regie over gegevens vaak impliciet bij
leveranciers, doordat gegevens en functionaliteit zijn opgesloten in
afzonderlijke applicaties en ontsluiting of migratie beperkt mogelijk
is. Daarnaast voeren gemeenten beperkt regie op de inrichting en het
beheer van gegevens.

Dit verandert in deze architectuur en data-autonomie wordt gerealiseerd
langs de volgende samenhangende dimensies:

- **Gestandaardiseerde semantiek**

  Gegevens worden gemodelleerd volgens gemeenschappelijke begrippen,
  definities en informatiemodellen.

- **Brongericht gegevensbeheer**

  Gegevens worden beheerd bij de aangewezen bron of de daarvoor bestemde
  registratie. Duplicatie wordt voorkomen.

- **Gestandaardiseerde gegevensuitwisseling**

  Gegevens worden ontsloten via open API's, events en andere
  interoperabele mechanismen.

- **Portabiliteit**

  Gegevens zijn beschikbaar in open, gedocumenteerde formaten en kunnen
  onafhankelijk van leveranciers worden geëxporteerd, gemigreerd en
  hergebruikt.

- **Transparantie en controleerbaarheid**

  Gegevensgebruik is inzichtelijk en herleidbaar door logging, auditing
  en metadata.

- **Governance en contractuele borging**

  Governance en contractuele afspraken waarborgen dat gemeenten blijvend
  regie houden over gegevens, standaarden, interfaces en
  overdraagbaarheid.

### Uitwerking voor registraties en dataservices

De bovenstaande uitgangspunten leiden tot de volgende architectuureisen
voor registraties en dataservices:

- Iedere registratie heeft een expliciet aangewezen bronhouder;

- Iedere registratie vormt de autoritatieve bron voor de gegevens
  waarvoor zij verantwoordelijk is;

- Gegevens worden vastgelegd conform het gemeentelijke begrippenkader en
  informatiemodel;

- Registraties zijn onafhankelijk van proceslogica en kunnen door
  meerdere BusinessServices worden gebruikt;

- Gegevens worden uitsluitend ontsloten via gestandaardiseerde
  dataservices;

- Dataservices valideren, autoriseren en registreren iedere mutatie;

- Registraties ondersteunen versiebeheer, logging en volledige
  herleidbaarheid;

- Registraties voldoen aan de generieke platformvoorzieningen voor
  authenticatie, autorisatie, logging en beveiliging;

- Gegevens blijven overdraagbaar en leverancier-onafhankelijk.

Bovenstaande wordt verder uitgewerkt in het onderdeel Architectuur van
API’s en registraties.

### Borging buiten de architectuur

Architectuur alleen is onvoldoende om data-autonomie te realiseren. Een
belangrijk deel wordt organisatorisch en juridisch geborgd.

Daaronder vallen onder andere:

- Aanwijzing van bronhouders, data-eigenaren en gegevensbeheerders;

- Afspraken over gegevenskwaliteit en gegevensbeheer;

- Classificatie van gegevens en privacybeleid;

- Autorisatiebeleid en wettelijke grondslagen voor gegevensgebruik;

- Bewaartermijnen, archivering en vernietiging;

- Contractuele afspraken over Open Source, overdraagbaarheid,
  continuïteit en exit;

- Toezicht, auditing en periodieke evaluatie.

## Data bij de bron

Het [**Principe: Data bij de bron**](../05-visie-principes-scope/README.md#principe-data-bij-de-bron) is een
fundamenteel uitgangspunt van zowel Common Ground als de overheidsbrede
[Domeinarchitectuur
Gegevensuitwisseling](https://www.noraonline.nl/wiki/Domeinarchitectuur_Gegevensuitwisseling).
Gegevens worden beheerd door de (door de bronhouder) daarvoor aangewezen
bron en vanuit een (eveneens door de bronhouder aangewezen) bron
beschikbaar gesteld aan afnemers. Processen, BusinessServices en
applicaties gebruiken deze gegevens, maar worden daarvan geen eigenaar.
Hiermee wordt uitvoering gegeven aan architectuurprincipe 4.4.8 – Data
bij de bron.

> **Principe: Data bij de bron:** Gegevens worden beheerd door de
> daarvoor aangewezen bronhouder en worden vanuit die bron beschikbaar
> gesteld. Processen en proces-services/applicaties gebruiken gegevens,
> maar zijn daarvan geen eigenaar.

### De bron

Binnen deze architectuur wordt onder een **bron** verstaan:

*De registratie of gegevensdienst die door de bronhouder als leidende
voorziening is aangewezen voor het beschikbaar stellen van een bepaald
type gegevens.*

Deze definitie sluit aan bij de Domeinarchitectuur Gegevensuitwisseling,
waarin het onderscheid wordt gemaakt tussen het beheren van gegevens
(bronhouder) en het beschikbaar stellen daarvan (aanbieder). Beide
rollen kunnen door dezelfde organisatie worden ingevuld, maar hoeven dat
niet te zijn.

### Rollen en verantwoordelijkheden

Binnen deze architectuur wordt aangesloten bij de terminologie uit de
Domeinarchitectuur Gegevensuitwisseling, waarin de rollen bronhouder,
aanbieder en afnemer centraal staan. Deze rollen beschrijven de
verantwoordelijkheden voor het beheren en beschikbaar stellen van
gegevens binnen een gegevensuitwisseling.

Binnen Data Governance wordt vaak gesproken over een data-eigenaar. Deze
rol heeft een bredere organisatorische verantwoordelijkheid voor de
kwaliteit, het gebruik en de governance van een gegevensdomein. In veel
gevallen zal de data-eigenaar tevens optreden als bronhouder, maar beide
begrippen zijn niet volledig uitwisselbaar:

- Data-eigenaar beschrijft de persoon binnen de organisatie die
  eindverantwoordelijk is voor de definitie, kwaliteit, waarde en het
  correct beschikbaar stellen van een specifieke dataset of data-domein
  ([DAMA](https://dama-nl.org/wp-content/uploads/2022/09/Two-pager-Data-Governance-2-DAMA-NL.pdf))

- [Bronhouder](https://www.noraonline.nl/wiki/Rollen_Domeinarchitectuur_Gegevensuitwisseling)
  beschrijft een [rol](javascript:void(0);) van een partij die
  verantwoordelijk is voor de inhoud en kwaliteit van een registratie
  die als bron is aangewezen.

In deze Enterprise Architectuur wordt het begrip bronhouder gebruikt,
omdat dit aansluit bij de landelijke terminologie rond
gegevensuitwisseling. Gemeenten kunnen deze rol intern beleggen bij de
data-eigenaar of een andere daarvoor aangewezen functionaris.

### Toepassing binnen Platform Dienstverlening

Binnen het Platform Dienstverlening worden verschillende typen bronnen
onderscheiden.

- **Landelijke bronnen**, zoals basisregistraties, zijn de bron voor
  wettelijk aangewezen gegevens.

  - In de praktijk vallen de plaats waar gegevens worden beheerd en de
    plaats waar zij beschikbaar worden gesteld dus niet altijd samen
    (zie de optionele scheiding tussen bronhouder en aanbieder). Een
    bekend voorbeeld is de Basisregistratie Personen (BRP). Gemeenten
    zijn bronhouder voor persoonsgegevens van ingezetenen, terwijl
    landelijke voorzieningen deze gegevens beschikbaar stellen aan
    afnemers. Voor gebruikers vormt deze gegevensdienst de bron, terwijl
    de verantwoordelijkheid voor de gegevens bij de bronhouder blijft.

- **Gemeentelijke registraties** vormen de bron voor lokale en
  domeinspecifieke gegevens waarvoor de gemeente de bronhouder is.

  - Ook binnen de gemeentelijke context kunnen de rollen van
    **bronhouder** en **aanbieder** worden gescheiden. Dit gebeurt
    bijvoorbeeld bij Patroon B-implementaties (zie [Patroon B – Hybride
    implementatie](../11-toegepaste-patronen/README.md#patroon-b-hybride-implementatie)). De bronhouder is
    verantwoordelijk voor de inhoud, kwaliteit en betekenis van de
    gegevens in de registratie. De aanbieder verzorgt de ontsluiting van
    deze gegevens via gestandaardiseerde gegevensdiensten, inclusief
    metadata, autorisatie, notificaties en eventuele intermediaire
    voorzieningen.

- **Domeinregistraties** zijn gemeentelijke registraties, maar bevatten
  gegevens die specifiek zijn voor een bepaald beleidsdomeinOngeacht het
  type bron geldt dat gegevens uitsluitend beschikbaar worden gesteld
  via gestandaardiseerde gegevensdiensten. Hierdoor kunnen meerdere
  BusinessServices dezelfde gegevens gebruiken zonder deze te
  dupliceren.

### De eindigheid van bronnen en brongegevens

Het principe Data bij de bron betekent niet dat data in een bron of
registratie onbeperkt blijft bestaan of dat gegevens onbeperkt
beschikbaar blijven. Elk gegeven kent een eigen levenscyclus, die wordt
bepaald door wet- en regelgeving en de doelbinding waarvoor gegevens
zijn verzameld.

Voor registraties binnen het Platform Dienstverlening betekent dit dat
gegevens gedurende hun levenscyclus beschikbaar worden gesteld via de
bron, maar uiteindelijk:

- Worden vernietigd wanneer daarvoor een wettelijke grondslag bestaat;

- Of, indien de Archiefwet dit voorschrijft, worden overgebracht naar
  een archiefbewaarplaats voor duurzame bewaring.

Daarnaast geldt dat het beschikbaar stellen van gegevens altijd
plaatsvindt binnen de geldende autorisaties, doelbinding en
informatieclassificatie. Dat gegevens bij de bron beschikbaar zijn,
betekent nadrukkelijk niet dat iedere afnemer toegang heeft tot alle
gegevens.

Hieruit volgt dat Data bij de bron niet alleen vraagt om een duidelijke
bronregistratie, maar ook om ondersteuning van de volledige
informatielevenscyclus, inclusief autorisatie, bewaartermijnen,
vernietiging en – waar wettelijk vereist – overbrenging naar een
archiefbewaarplaats. De architectuurimplicaties hiervan worden verder
uitgewerkt in [Duurzame toegankelijkheid by
design](README.md#duurzame-toegankelijkheid-by-design).

### Implicaties voor ontwerp

Het principe **Data bij de bron** heeft directe gevolgen voor de
inrichting van bedrijfsprocessen, BusinessServices en applicaties. Bij
de ontwikkeling van nieuwe functionaliteit geldt daarom het volgende:

- Bestaande registraties zijn het uitgangspunt voor gegevensgebruik;

- Nieuwe processen introduceren geen eigen gegevensdefinities of
  gegevensopslag wanneer hiervoor reeds een bronregistratie bestaat;

- Nieuwe gegevensdefinities worden gerealiseerd conform het
  gemeentelijke begrippenkader en de informatiearchitectuur;

- BusinessServices gebruiken gegevens via de daarvoor aangewezen
  registraties en dataservices;

- Alleen wanneer bestaande registraties aantoonbaar onvoldoende zijn,
  wordt een nieuwe registratie geïntroduceerd.

Processen en BusinessServices zijn afnemers van gegevens; registraties
zorgen voor het voor het duurzaam beheer daarvan.

### Bronnen buiten de scope van het Platform

Niet alle gemeentelijke gegevens bevinden zich binnen het Platform
Dienstverlening. Voor voorzieningen zoals HR-, financiële of andere
bedrijfsvoeringssystemen blijft het betreffende systeem de bron voor de
gegevens waarvoor het verantwoordelijk is.

Het Platform Dienstverlening neemt deze gegevens niet over, maar
gebruikt ze via gestandaardiseerde gegevensdiensten. Daarbij gelden de
volgende uitgangspunten:

- De externe registratie blijft de leidende bron;

- Gegevens worden ontsloten via gestandaardiseerde API's of
  gegevensdiensten;

- BusinessServices gebruiken gegevens via referenties of raadplegingen
  en voorkomen onnodige duplicatie.

Alleen wanneer synchronisatie noodzakelijk is, bijvoorbeeld vanwege
prestaties, beschikbaarheid of wettelijke eisen, mag hiervan worden
afgeweken. Daarbij geldt altijd dat:

- De bronrelatie expliciet blijft vastgelegd;

- De externe registratie leidend blijft;

- Geen nieuw bronhouderschap binnen het platform ontstaat;

- Verantwoordelijkheden voor actualiteit, synchronisatie en
  gegevenskwaliteit expliciet zijn belegd.

## Duurzame toegankelijkheid by design

In traditionele (zaak)systemen bevinden gegevens zich veelal binnen één
applicatie. In een Common Ground-architectuur zijn informatieobjecten
verdeeld over meerdere zelfstandige registraties en services. Hierdoor
verschuift de uitdaging van het archiveren van één applicatie naar het
duurzaam toegankelijk houden van een samenhangend netwerk van
informatieobjecten.

Een van de architectuurprincipes is [**Principe: Kwaliteit by
Design**](../05-visie-principes-scope/README.md#principe-kwaliteit-by-design):

> Niet-functionele kwaliteitseisen worden vanaf het ontwerp integraal
> meegenomen in architectuur, software en dienstverlening. Aspecten
> zoals informatiebeveiliging, privacy, toegankelijkheid,
> informatiebeheer, logging, auditing en beheerbaarheid zijn geen
> afzonderlijke voorzieningen achteraf, maar vormen een integraal
> onderdeel van iedere platformvoorziening.

Dit sluit aan bij de visie op de digitale overheid, waarin de overheid
duurzaam regie moet houden op haar informatie en digitale
infrastructuur. Publieke waarden zoals transparantie, uitlegbaarheid,
toegankelijkheid en duurzame beschikbaarheid van overheidsinformatie
moeten niet afhankelijk zijn van individuele applicaties of
leveranciers, maar structureel worden geborgd in de inrichting van het
informatiestelsel.

Voor de uitwerking van duurzame toegankelijkheid sluit deze architectuur
aan bij het
[DUTO-raamwerk](https://www.nationaalarchief.nl/archiveren/kennisbank/duto-raamwerk)
van het Nationaal Archief. DUTO beschrijft geen afzonderlijke
archiefvoorziening, maar een ontwerpbenadering waarbij
informatiesystemen vanaf het ontwerp zodanig worden ingericht dat
overheidsinformatie gedurende haar gehele levenscyclus duurzaam
toegankelijk blijft. Het raamwerk onderscheidt daarbij de
kwaliteitskenmerken vindbaar, beschikbaar, leesbaar, interpreteerbaar,
betrouwbaar en toekomstbestendig en werkt deze uit in concrete
ontwerpmaatregelen voor informatiesystemen.

Dit onderdeel beperkt zich tot de architectuurimplicaties van duurzame
toegankelijkheid binnen een Common Ground-architectuur en onderscheidt
daarbij de **architectuur** en de **implementatie**.

### Duurzame toegankelijkheid vanuit de architectuur

Het DUTO-raamwerk onderscheidt vijf informatiebeheerprocessen die
gezamenlijk invulling geven aan duurzame toegankelijkheid:

- Registreren;

- Bewaren;

- Migreren;

- Vernietigen;

- Ter beschikking stellen.

Binnen het Platform Dienstverlening worden deze processen niet door één
component uitgevoerd, maar verdeeld over meerdere
architectuurbouwblokken. Daarmee sluit de architectuur aan op het
uitgangspunt dat iedere component verantwoordelijk is voor zijn eigen
gegevens en functionaliteit.

De relevante bouwblokken zijn uitgewerkt in de
[applicatiearchitectuur](../08-applicatiearchitectuur/README.md#architectural-building-blocks-abbs-en-clusters):

- **ABB Registraties** (laag 1) en **ABB Diensten** (laag 2) zijn
  verantwoordelijk voor het vastleggen, beheren en ontsluiten van
  informatieobjecten.

- De doorsnijdende **ABB Duurzame toegankelijkheid** ondersteunt de
  platformbrede informatiebeheerprocessen, zoals lifecyclebeheer,
  archivering, overbrenging en vernietiging.

  De (applicatie)architectuur van
  [registraties](../08-applicatiearchitectuur/README.md#architectuur-van-registraties) en
  [API’s](../08-applicatiearchitectuur/README.md#architectuur-van-apis) geeft invulling aan een belangrijk
  deel van de eisen voor duurzame toegankelijkheid. Registraties leggen
  informatie duurzaam vast, inclusief historie, metadata en
  gebeurtenissen, terwijl handelingsgedreven API's zorgen voor
  gecontroleerde mutaties en volledige herleidbaarheid van wijzigingen.

  Maar een gedistribueerde architectuur vraagt om aanvullende
  functionaliteit en afspraken die in deze versie van de architectuur
  verder worden uitgewerkt aan de hand van het DUTO-functiemodel.

### Implementatie & DUTO-functiemodel

De DUTO-processen worden verdiept met het
[DUTO-functiemodel](https://www.nationaalarchief.nl/archiveren/kennisbank/duto-functiemodel).
Dit geeft een handvat om te controleren in hoeverre, en op welke manier,
het Platform voldoet aan de gestelde eisen.

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 24%" />
<col style="width: 51%" />
</colgroup>
<thead>
<tr>
<th><strong>DUTO-functie</strong></th>
<th><strong>Primaire ABB</strong></th>
<th><strong>Toelichting</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>F01 Bevriezing</strong></td>
<td>ABB Registraties</td>
<td>API’s op registraties dwingen af dat gegevens volgens bedrijfsregels
worden vastgezet zodat ze niet meer kunnen worden gewijzigd. De interne
logica van Registraties dwingt af dat de registratie van data niet
aanpasbaar is, maar dat een mutatie een nieuwe registratie is.</td>
</tr>
<tr>
<td><strong>F02 Conversie</strong></td>
<td><strong>Niet ingevuld</strong></td>
<td><p>In de registraties worden informatie-objecten zo opgeslagen dat
ze op diverse wijzen kunnen worden gerepresenteerd, conform doel en
doelbinding.</p>
<p>In de periferie van het platform (zaakbruggen, koppelvlakken) worden
door leveranciers wel degelijk conversiefunctionaliteit gerealiseerd om
legacy-dataformaten om te zetten naar de standaarden (data <em>in</em>
het platform te krijgen). Maar andersom nog niet. Een usecase daarvoor
zou overbrenging naar het E-Depot kunnen zijn.</p></td>
</tr>
<tr>
<td><strong>F03 Creatie</strong></td>
<td>ABB Processervice, ABB Diensten + ABB Registraties</td>
<td>Creatie speelt over het hele platform een rol: vanaf formulieren
(bepaling van velden, validatie), tot processervices (datamodellen,
validatie, procesinrichting; Diensten(API’s) dwingen validatie en
constraints af; registraties nemen informatieobjecten duurzaam op.</td>
</tr>
<tr>
<td><strong>F04 Inwinning</strong></td>
<td>ABB Processervices</td>
<td>In de proceslaag worden gegevens opgehaald via gestandaardiseerde
API’s van externe bronnen. Ze worden daar gevalideerd; via API’s en
configuratie worden de gegevens met de juiste metadata (bron) verwerkt
in registraties.</td>
</tr>
<tr>
<td><strong>F05 Maskering</strong></td>
<td><strong>Niet ingevuld</strong></td>
<td>In het huidige platform is geen generieke maskeringsfunctionaliteit
gerealiseerd. Dat is voor verschillende doeleinden wel nodig.</td>
</tr>
<tr>
<td><strong>F06 Metagegevensbeheer</strong></td>
<td>ABB Registraties</td>
<td>Registraties beheren objectmetadata; Hiervoor worden standaarden
gevolgd</td>
</tr>
<tr>
<td><strong>F07 Opname</strong></td>
<td>ABB Registraties</td>
<td>Registraties nemen informatieobjecten duurzaam in beheer.</td>
</tr>
<tr>
<td><strong>F08 Opslag</strong></td>
<td>ABB Registraties</td>
<td>Registraties zijn verantwoordelijk voor duurzame opslag van
informatieobjecten. Hier is een vast patroon voor (URN’s)</td>
</tr>
<tr>
<td><strong>F09 Publicatie</strong></td>
<td>ABB Diensten</td>
<td>Informatie wordt beschikbaar gesteld via gestandaardiseerde
dataservices en API's.</td>
</tr>
<tr>
<td><strong>F10 Representatie</strong></td>
<td>ABB Interactieservices</td>
<td>Portalen en gebruikersinterfaces tonen informatie aan gebruikers.
Dit gaat om diverse services, conform doel(groep) en doelbinding.</td>
</tr>
<tr>
<td><strong>F11 Toegangsbeheer</strong></td>
<td>ABB Autorisatie (AuthZEN/OpenFTV)</td>
<td>Platformbrede autorisatie op basis van beleid, attributen en
context.</td>
</tr>
<tr>
<td><strong>F12 Uitwisseling</strong></td>
<td>ABB Dataservices + ABB Connectiviteit</td>
<td>Machine-to-machine-uitwisseling via API's en FSC.</td>
</tr>
<tr>
<td><strong>F13 Validatie</strong></td>
<td>Crossfunctioneel</td>
<td>Zie F03 – Creatie.</td>
</tr>
<tr>
<td><strong>F14 Verantwoording</strong></td>
<td>(o.a.) ABB Logging Dataverwerkingen, ABB Registraties</td>
<td>Verantwoording ontstaat uit de samenhang tussen registraties
(states, events en metadata), het Logboek Dataverwerkingen en de
autorisatievoorziening. Samen maken deze bouwblokken beheer en gebruik
van informatieobjecten volledig herleidbaar.</td>
</tr>
<tr>
<td><strong>F15 Vernietiging</strong></td>
<td>ABB Duurzame toegankelijkheid + ABB Registraties</td>
<td>De ABB Duurzame toegankelijkheid stelt de recordmanager in staat
regie te voeren op vernietiging; registraties voeren de feitelijke
verwijdering uit.</td>
</tr>
<tr>
<td><strong>F16 Zoeken</strong></td>
<td>ABB Dataservices + ABB Interactieservices</td>
<td>Registraties bieden zoekfunctionaliteit via API's;
interactieservices ondersteunen gebruikers bij het vinden van
informatie.</td>
</tr>
</tbody>
</table>

De mapping laat zien dat een belangrijk deel van de DUTO-functies geheel
of gedeeltelijk wordt ingevuld door de referentie-architectuur van het
Platform Dienstverlening. Registraties vormen daarbij de primaire
bouwsteen voor het duurzaam beheren van informatieobjecten, terwijl
diensten, dataservices, autorisatie, logging en connectiviteit
gezamenlijk invulling geven aan de overige functies. Duurzame
toegankelijkheid wordt daarmee niet gerealiseerd door één afzonderlijke
archiefcomponent, maar als een integrale eigenschap van het gehele
platform.

Daarbij moet worden opgemerkt dat niet alle architectuurbouwblokken
(ABB's) in de huidige referentie-implementatie zijn gerealiseerd.
Voorbeelden hiervan zijn de verdere doorontwikkeling van de
registraties, de volledige implementatie van het Logboek
Dataverwerkingen (LDV) en de realisatie van de
OpenFTV/AuthZEN-voorziening.

De volgende capabilities zijn (architectureel) nog geheel of
gedeeltelijk uit te werken:

- **Platformbrede maskeringsfunctionaliteit (F05)**  
  Het platform kent nog geen generieke capability voor het dynamisch
  maskeren of pseudonimiseren van gegevens op basis van doel, context of
  gebruikersrol.

- **Lifecyclebeheer van informatieobjecten**  
  Platformbrede ondersteuning voor lifecycle-overgangen, zoals
  archiefstatussen, overbrenging en vernietiging, vraagt verdere
  standaardisatie. Daarbij moet – waarschijnlijk – ook invulling worden
  gegeven aan de eisen uit de Archiefwet voor de overbrenging van
  blijvend te bewaren informatie naar een archiefbewaarplaats (e-depot).
  De wijze waarop deze overbrenging plaatsvindt, is niet uitgewerkt.
  Daarbij spelen onder meer vragen over de
  verantwoordelijkheidsverdeling tussen registraties en
  archiefvoorzieningen, de benodigde metadata en de vraag of
  informatieobjecten vóór overbrenging moeten worden geconverteerd, en
  welke service dat moet doen.

- **Platformbreed metagegevensbeheer**  
  Registraties beheren hun eigen metadata. Verdere uitwerking is nodig
  voor uniforme archiefmetadata, classificaties, bewaartermijnen en
  andere lifecyclemetadata conform landelijke standaarden zoals MDTO.
  Dit wordt ten dele ondervangen in de architectuur van registraties.

- **Duurzame reconstructie van dossiers**  
  Omdat informatieobjecten verspreid zijn over meerdere registraties, is
  een architectuur nodig waarmee dossiers en andere samenhangende
  informatie ook op langere termijn volledig en reproduceerbaar kunnen
  worden samengesteld.

- **Referentie-implementatie van de ABB Duurzame toegankelijkheid**  
  Binnen de huidige referentie-implementatie van het Platform
  Dienstverlening wordt de ABB Duurzame toegankelijkheid gedeeltelijk
  ingevuld door de Open Archiefbeheer Beheercomponent (OAB). Deze
  component richt zich primair op de vernietiging van informatie. OAB
  geeft slechts een eerste invulling van de ABB Duurzame
  toegankelijkheid. Verdere doorontwikkeling is noodzakelijk.

De nadruk van bovenstaande inventarisatie ligt nadrukkelijk op de
ontwikkeling van architectuurcapabilities. De *organisatorische*
inrichting van informatiebeheer, recordmanagement en archiefprocessen
valt buiten de scope van deze Enterprise Architectuur en wordt
uitgewerkt binnen de daarvoor geldende vakinhoudelijke kaders.

De concrete doorontwikkeling van services (zoals registraties, en OAB)
vindt iteratief plaats in samenwerking met de betrokken vakexperts.
Hierbij worden de architectuurprincipes uit deze Enterprise Architectuur
verfijnd en vertaald naar concrete services, API's, informatiepatronen
en implementaties.

### Openbaarheid van overheidsinformatie (Woo)

De [Wet open overheid
(Woo)](https://www.rijksoverheid.nl/themas/overheid-en-democratie/wet-open-overheid-woo/hoofdlijnen-woo)
heeft als doel de transparantie van de overheid te vergroten door
overheidsinformatie actief en passief openbaar te maken. De wet gaat uit
van het principe dat overheidsinformatie openbaar is, tenzij een
wettelijke uitzonderingsgrond van toepassing is. Daarnaast stelt de Woo
eisen aan de digitale informatiehuishouding van overheidsorganisaties,
zodat informatie vindbaar, toegankelijk en duurzaam beschikbaar is.

De (informatie)architectuur van het Platform Dienstverlening vormt een
belangrijke randvoorwaarde voor de uitvoering van de Woo. De Woo vereist
aanvullende functionaliteit, denk hierbij aan het selecteren van
openbaar te maken informatie, het toepassen van uitzonderingsgronden,
anonimisering of pseudonimisering, publicatie naar landelijke
voorzieningen en het ondersteunen van de processen rondom actieve en
passieve openbaarmaking.

Binnen de huidige referentiearchitectuur is hiervoor nog geen oplossing
aangewezen. Hoewel binnen de Common Ground-gemeenschap voorzieningen
zijn ontwikkeld, zoals
[OpenWoo](https://www.conduction.nl/solutions/openwoo/) en [de Generieke
Publicatievoorziening Woo (GPP-Woo)](https://www.gpp-woo.nl/), maken
deze op dit moment nog geen integraal onderdeel uit van het Platform
Dienstverlening en bestaat er nog geen gestandaardiseerd
integratiepatroon met de overige platformvoorzieningen. Tegelijkertijd
wordt landelijk gewerkt aan de [Generieke Woo-voorziening
(GWV)](https://www.koopoverheid.nl/voor-overheden/rijksoverheid/open-overheid)
voor de gefaseerde invoering van de actieve openbaarmakingsplicht.

De verdere uitwerking van Woo-ondersteuning valt buiten de scope van
deze versie van de Enterprise Architectuur. Wel worden de volgende
architectuurcapabilities voorzien voor toekomstige ontwikkeling:

- **Platformbrede Woo-capability**, inclusief een architectuurbouwblok
  voor actieve en passieve openbaarmaking.

- **Gestandaardiseerde koppeling tussen registraties en
  Woo-voorzieningen**, zodat informatieobjecten inclusief metadata,
  relaties en context beschikbaar kunnen worden gesteld voor
  openbaarmaking.

- **Ondersteuning van openbaarmakingsprocessen**, waaronder selectie,
  beoordeling, anonimisering, publicatie en intrekking.

- **Platformbrede maskeringsfunctionaliteit**, waarmee persoonsgegevens
  en andere beschermde informatie op basis van wet- en regelgeving,
  autorisatie en doelbinding automatisch kunnen worden afgeschermd of
  geanonimiseerd. Deze capability sluit aan op de ABB **Duurzame
  toegankelijkheid**, waarin generieke ondersteuning voor maskering als
  ontbrekende functie is geïdentificeerd.

- **Integratie met landelijke Woo-voorzieningen**, waaronder de
  Generieke Woo-voorziening (GWV) en eventuele opvolgende landelijke
  publicatievoorzieningen.

- **Samenhang met duurzame toegankelijkheid**, zodat informatie
  gedurende de gehele levenscyclus zowel archiefwaardig als
  openbaarmaakbaar blijft.

## Security by Design

Informatiebeveiliging is een randvoorwaarde voor het Platform
Dienstverlening. Gemeenten zijn verantwoordelijk voor het voldoen aan de
[Baseline Informatiebeveiliging Overheid
(BIO)](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/cybersecurity/bio-en-ensia/baseline-informatiebeveiliging-overheid/)
en de daarop gebaseerde normen, processen en risicobeheersing. Een
volledige toetsing aan de BIO of ISO/NEN 27001 vindt plaats op het
niveau van de ingerichte organisatie, de operationele beheerprocessen en
de daadwerkelijk geïmplementeerde ICT-omgeving, en valt daarmee buiten
de scope van deze Enterprise Architectuur.

Deze architectuur beschrijft uitsluitend de architectonische
uitgangspunten voor *Security by Design*: de wijze waarop beveiliging
vanaf het ontwerp integraal onderdeel vormt van het Platform
Dienstverlening. Hiermee wordt invulling gegeven aan [**Principe:
Kwaliteit by Design**](../05-visie-principes-scope/README.md#principe-kwaliteit-by-design):

> Niet-functionele kwaliteitseisen worden vanaf het ontwerp integraal
> meegenomen in architectuur, software en dienstverlening. Aspecten
> zoals informatiebeveiliging, privacy, toegankelijkheid,
> informatiebeheer, logging, auditing en beheerbaarheid zijn geen
> afzonderlijke voorzieningen achteraf, maar vormen een integraal
> onderdeel van iedere platformvoorziening.

### Platformverantwoordelijkheid security

Het Platform Dienstverlening realiseert een belangrijk deel van de
generieke technische beveiligingsvoorzieningen als gemeenschappelijke
platformcapabilities. Hierdoor hoeven individuele services deze
voorzieningen niet telkens opnieuw te implementeren en ontstaat een
uniforme beveiligingsbasis voor het gehele platform.

Deze generieke capabilities worden grotendeels gerealiseerd door de
Haven+ infrastructuur, zie onder meer het principe [*Security by
default* in de Haven+
architectuur](https://havenplus.commonground.nl/docs/haven-plus-architecture-principles/#ap-06--security-by-default).
Hierdoor kunnen ontwikkelteams zich concentreren op de functionele
beveiliging van hun eigen services.

### Verantwoordelijkheid van services

De beschikbaarheid van generieke platformvoorzieningen ontslaat de
proceseigenaar niet van de eigen verantwoordelijkheid voor de inrichting
van de service. Bij iedere implementatie blijft de proceseigenaar
verantwoordelijk voor onder andere:

- Correcte autorisatie van bedrijfsfunctionaliteit;

- Rechtmatige verwerking van gegevens;

- Invoervalidatie en bescherming tegen kwetsbaarheden;

- Correcte toepassing van privacy- en informatiebeveiligingsmaatregelen;

- Veilige softwareontwikkeling en onderhoud.

Platformbeveiliging en applicatiebeveiliging vullen elkaar daarmee aan;
maar ook bij de uitbesteding van ontwikkeling of beheer blijft de
proceseigenaar eindverantwoordelijk.

### Verdere uitwerking

De concrete implementatie van Security by Design wordt in deze
Enterprise Architectuur niet verder uitgewerkt. Hiervoor wordt verwezen
naar:

- De **Technologiearchitectuur** (Haven+ en platformvoorzieningen);

- De **Aansluitvoorwaarden Platform Dienstverlening**, waarin de
  technische beveiligings- en ontwikkelvereisten voor platformservices
  en aangesloten applicaties zijn opgenomen, waaronder eisen aan
  identity, autorisatie, OpenTelemetry, GitOps, Kubernetes, CI/CD,
  containerbeveiliging, softwarekwaliteit en releasebeheer;

- De gemeentelijke BIO-governance, waarin risicomanagement,
  classificatie, incidentmanagement, leveranciersmanagement, auditing en
  compliance zijn belegd.

- Een Security Handboek waarin de BIO2-beheersmaatregelen voor de
  relevante domeinen worden uitgewerkt tot concrete
  beveiligingsstandaarden voor het platform en services. Dit document is
  in ontwikkeling. Publicatie volgt.

## Data-architectuur

De voorgaande paragrafen beschrijven de informatiekundige uitgangspunten
van het Platform Dienstverlening. Zij geven antwoord op vragen als:
welke gegevens zijn leidend, wie is verantwoordelijk voor de kwaliteit
ervan en hoe blijven gegevens duurzaam toegankelijk?

De data-architectuur bouwt hierop voort en beschrijft de logische
inrichting van de gemeentelijke gegevenslaag. Centraal staan de gegevens
zelf: de businessobjecten, hun onderlinge relaties, de verdeling over
generieke en domeinspecifieke registraties en de aansluiting op het
Gemeentelijk Gegevensmodel (GGM). De nadruk ligt daarbij op de structuur
en samenhang van gegevens, onafhankelijk van de wijze waarop deze
technisch worden geïmplementeerd of ontsloten.

De concrete realisatie van registraties, dataservices, API's en andere
softwarecomponenten wordt in het hoofdstuk Applicatiearchitectuur
uitgewerkt.

### Scheiding van data en proces

Een fundamenteel uitgangspunt binnen de data-architectuur is de
scheiding tussen **gegevens** en **processen**. Gegevens beschrijven de
werkelijkheid en hebben een zelfstandige betekenis, onafhankelijk van de
processen waarin zij worden gebruikt. Voor duurzame toegankelijkheid
blijft de procescontext wel essentieel. Om de herkomst, betekenis en
totstandkoming van gegevens te kunnen reconstrueren, moeten de processen
waarin gegevens zijn ontstaan, gewijzigd of geraadpleegd expliciet
worden vastgelegd en raadpleegbaar blijven.

Hiermee wordt uitvoering gegeven aan het architectuurprincipe
[**Principe: Data bij de bron**](../05-visie-principes-scope/README.md#principe-data-bij-de-bron).

Deze scheiding kent twee complementaire dimensies.

- **Verticale scheiding tussen proces en data**

  - BusinessServices en processen gebruiken gegevens uit de daarvoor
    aangewezen registraties. Gegevens worden niet beheerd binnen
    processen of applicaties, maar uitsluitend binnen de registraties
    die daarvoor verantwoordelijk zijn. Hierdoor kunnen dezelfde
    gegevens door meerdere processen worden gebruikt zonder duplicatie
    of inconsistentie.

- **Horizontale scheiding tussen registraties**

  - Gemeenschappelijke bedrijfsobjecten, zoals **Klant**, **Zaak**,
    **Product** en **Plan**, overstijgen individuele processen en
    beleidsdomeinen. Deze worden daarom ondergebracht in generieke
    registraties die door meerdere BusinessServices kunnen worden
    gebruikt.

<img
src="../media/media/image20.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Daarnaast bestaan domeinspecifieke registraties voor gegevens die
uitsluitend binnen een bepaald beleidsdomein relevant zijn. Ook deze
registraties worden onafhankelijk van processen beheerd en kunnen door
meerdere toepassingen worden hergebruikt, binnen de daarvoor geldende
autorisatie- en validatieregels.

Deze inrichting zorgt ervoor dat:

- Gegevens éénmaal en eenduidig worden vastgelegd;

- Semantiek onafhankelijk van processen wordt beheerd;

- BusinessServices en processen onafhankelijk van de gegevensstructuur
  kunnen evolueren;

- Generieke en domeinspecifieke gegevens op consistente wijze kunnen
  worden gecombineerd.

De verzameling van generieke registraties, domeinregistraties en hun
onderlinge relaties vormt de **gemeentelijke gegevenslaag** van het
Platform Dienstverlening.

De concrete realisatie van deze registraties, de ontsluiting via
dataservices, API's en events en de onderlinge communicatie tussen
softwarecomponenten worden uitgewerkt in de **Applicatiearchitectuur**.

## Soorten data en positionering in de architectuur

Hoewel registraties de gegevensbasis vormen in de architectuur, betekent
dit niet dat *alle* data binnen het platform in deze laag thuishoort (en
dat is ook niet mogelijk). De volgende vorm van data zijn te
onderscheiden.

#### Duurzame gegevens (registratiedata)

Dit zijn gegevens die een duurzame representatie van de werkelijkheid
vormen en door meerdere processen en services worden gebruikt. Het gaat
om gegevens met een duidelijke betekenis buiten één specifiek proces,
die consistent en eenduidig moeten worden beheerd.

- Voorbeelden: personen, zaken, producten, beschikkingen

- Kenmerken: herbruikbaar en leidend voor besluitvorming

- Positionering: vastgelegd in registraties (dataservices) en ontsloten
  via API’s

Deze gegevens vormen de kern van de gegevenslaag en zijn de primaire
bron voor dienstverlening. De informatie over een inwoner en diens
situatie is daarbij niet geconcentreerd in één plek, maar verdeeld over
meerdere registraties. Zo worden verschillende aspecten van de
werkelijkheid afzonderlijk vastgelegd, elk vanuit hun eigen domein:

- Gegevens over de persoon in een klant- of basisregistratie

- Gegevens over producten in de productregistratie

- Gegevens over de voortgang van een zaak in de zaakregistratie

Dit betekent dat de “toestand” van een inwoner of een casus altijd een
samenspel is van meerdere gegevensbronnen. Door deze gegevens centraal
en per domein te beheren, blijft de informatie onafhankelijk van
specifieke applicaties of workflows. Hoe deze data duurzaam wordt
geregistreerd is beschreven in [Architectuur van
registraties](../08-applicatiearchitectuur/README.md#architectuur-van-registraties).

#### Procesdata (workflow- en uitvoeringsdata)

Dit betreft gegevens die nodig zijn om processen uit te voeren, maar die
geen zelfstandige betekenis hebben buiten dat proces. Dit gaat
bijvoorbeeld om:

- De toestand van het proces zelf: waar zit een case in de workflow,
  welke stap is actief, welke paden zijn doorlopen.

- Voorbeelden: actieve taak, processtap, wachttijd, routingbeslissing.

Deze data hoort niet in de gegevenslaag thuis en blijft gekoppeld aan de
uitvoering van processen, en wordt beheerd binnen proces- of
orkestratieservices (bijv. GZAC/Valtimo). Belangrijk is dat bij de
configuratie van deze services wordt ingebouwd dat die data vernietigd
wordt als het proces stopt.

#### Afgeleide en analytische data

Dit betreft data die wordt samengesteld of afgeleid uit andere gegevens,
bijvoorbeeld voor analyse, sturing of rapportage.

- Voorbeelden: dashboards, rapportages, beleidsinformatie, statistieken

- Kenmerken: afgeleid, niet leidend voor operationele processen, vaak
  gecombineerd uit meerdere bronnen; de informatie kan wel essentieel
  zijn voor sturing op operationele processen.

- Positionering: beheerd in aparte analyse- of rapportagevoorzieningen

Deze data ondersteunt inzicht en besluitvorming, maar is geen directe
bron voor operationele dienstverlening.

#### Positionering van DMN-regels in de architectuur

De inhoud van een DMN-engine (beslisregels, decision tables) moet worden
gezien als:

- Herbruikbare, expliciete beslislogica die onderdeel is van de
  dienstverlening, maar geen representatie van de werkelijkheid zelf.

Om die herbruikbaarheid en consistentie te borgen, worden deze regels
ondergebracht in een losstaande rule-engine, die door meerdere services
wordt gebruikt. Dit voorkomt dat dezelfde regels op meerdere plekken
worden geïmplementeerd en uiteen gaan lopen, en maakt het mogelijk om
wijzigingen in beleid of wetgeving gecontroleerd en uniform door te
voeren. Zie verder de applicatiearchitectuur.

### Datakwaliteit

Datakwaliteit bepaalt in hoeverre gegevens geschikt zijn voor het doel
waarvoor ze worden gebruikt. Het is daarmee geen absolute eigenschap,
maar afhankelijk van context: dezelfde data kan voor het ene doel
bruikbaar zijn en voor het andere niet.

[ISO/IEC
25012](https://mail.iso25000.com/index.php/en/iso-25000-standards/iso-25012)
onderscheidt twee perspectieven: **inherente datakwaliteit** en
**systeemafhankelijke datakwaliteit**.

#### Inherente datakwaliteit

Dit betreft de kwaliteit van de data zelf, los van systemen. Deze wordt
bepaald bij het modelleren en vastleggen van gegevens.

- Kenmerken: juistheid, volledigheid, consistentie, geloofwaardigheid,
  actualiteit

- Ontstaat bij: datamodel, definities en keuzes wat wel en niet wordt
  vastgelegd.

De belangrijkste consequentie is dat datakwaliteit hier begint: gegevens
die niet worden gemodelleerd of onjuist worden vastgelegd, kunnen later
niet of slechts beperkt worden gecorrigeerd. De kwaliteit hier wordt
bepaald door de modellering van proces- en dataservices, die wordt
beschreven in [Bedrijfsarchitectuur als schakel tussen platform, inwoner
en
organisatie](../06-businessarchitectuur/README.md#bedrijfsarchitectuur-als-schakel-tussen-platform-inwoner-en-organisatie).

#### Systeemafhankelijke (borging van) datakwaliteit

Systeemafhankelijke datakwaliteit betreft de mate waarin systemen de
kwaliteit van data borgen tijdens gebruik. Een service-architectuur
betekent dat datakwaliteit niet beperkt is tot één service of component,
maar het resultaat is van het samenspel tussen services, API’s en
registraties tijdens invoer, verwerking en ontsluiting van gegevens:

- **Interactieservices** vormen het eerste punt waar datakwaliteit wordt
  beïnvloed. Zij begeleiden inwoners en medewerkers bij het invoeren van
  gegevens, voeren vroegtijdige validaties uit en voorkomen dat onjuiste
  of onvolledige informatie het systeem binnenkomt.

- **Proces- en businessservices** zorgen vervolgens voor het correcte
  gebruik en de toepassing van gegevens. Zij combineren informatie uit
  verschillende bronnen, passen beslislogica toe en waarborgen dat
  gegevens in de juiste context worden geïnterpreteerd en gebruikt.

- **Registraties (dataservices)** vormen tenslotte de bron van waarheid
  en borgen de structurele kwaliteit. Zij valideren gegevens bij opslag
  en mutatie, bewaken consistentie en zorgen voor integriteit binnen het
  domein.

## Rapportage, datawarehousing & Platform Dienstverlening

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
src="../media/media/image21.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />
