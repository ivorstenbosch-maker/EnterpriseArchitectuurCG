# 2. Motivatie, strategie, uitkomst

| **Compact:** |
|----|
| De gemeentelijke informatievoorziening is in de loop der jaren complex geworden, met veel applicaties, leveranciersafhankelijkheden en historisch gegroeide oplossingen. Common Ground en het Platform Dienstverlening maken daarom de beweging naar een overheid die eenvoudiger, samenhangender en beter herbruikbaar kan werken |

## Inleiding

Dit hoofdstuk beschrijft de strategische context van het Platform
Dienstverlening en vormt de aanleiding voor de Architecture Vision zoals
bedoeld in de TOGAF Architecture Development Method (ADM). Het maakt
duidelijk waarom de architectuur is ontwikkeld, welke maatschappelijke
en organisatorische ontwikkelingen hieraan ten grondslag liggen en welke
veranderingen zij beoogt te realiseren.

Achtereenvolgens worden de ontwikkeling van de gemeentelijke
informatievoorziening, de aanleiding voor Common Ground, de
belangrijkste interne en externe drijfveren, de businesscase en de
beoogde uitkomst van de architectuur beschreven. Samen vormen deze
onderdelen de onderbouwing voor de architectuurkeuzes die in de volgende
hoofdstukken worden uitgewerkt.

## Motivatie

#### Gemeentelijke context

Gemeenten leveren zo’n 450 producten voor burgers en bedrijven, en
voeren daarnaast honderden interne processen uit voor projecten,
bedrijfsvoering en samenwerking met ketenpartners. In totaal gaat het om
ruim 1000 bedrijfsprocessen, ondersteund door circa 100
gestandaardiseerde gegevensuitwisselingen. Ondanks de inhoudelijke
verschillen tussen domeinen, zijn veel processen en benodigde
softwarefuncties generiek van aard.

De huidige gemeentelijke informatievoorziening is het resultaat van een
ontwikkeling die zich over meerdere decennia heeft voltrokken.
Oorspronkelijk werden afzonderlijke werkprocessen ondersteund met
gespecialiseerde applicaties volgens het principe *"elk proces zijn
eigen pakket"*. Toen de behoefte aan samenwerking tussen processen
toenam, ontstond een groeiend netwerk van koppelingen tussen systemen.
Als reactie daarop maakten gemeenten de overstap naar geïntegreerde
suites per domein, waarin meerdere functies werden samengebracht binnen
één leveranciersoplossing.

Deze ontwikkeling heeft gemeenten jarenlang geholpen om processen te
standaardiseren en beheersbaar te houden. Tegelijkertijd heeft zij
geleid tot een informatievoorziening waarin gegevens en functionaliteit
sterk zijn verweven met applicaties en leveranciers. Nu de behoefte aan
integrale, gegevensgedreven en proactieve dienstverlening toeneemt,
blijken deze architectuurkeuzes steeds vaker een beperking voor
wendbaarheid, samenwerking en innovatie. Een uitgebreidere beschrijving
van deze historische ontwikkeling is opgenomen in [**BIJLAGE - Korte
geschiedenis van gemeentelijke informatisering**](../15-bijlagen/README.md#bijlagen).

De behoefte aan integrale, proactieve dienstverlening – zoals één
klantbeeld, een herkenbaar digitaal loket, omnichannel-benadering en
datagedreven werken – vraagt om een andere inrichting van de
informatievoorziening. De huidige suite-architecturen sluiten
onvoldoende aan op deze ambities.

<img
src="../media/media/image3.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

#### Breder kader 

Dit probleem beperkt zich niet tot gemeenten, architectuur of software.
Informatievoorziening is een essentieel onderdeel van hoe de overheid
functioneert. Deze gedachte wordt scherp uitgewerkt in het rapport
[*Dwars door de
Orde*](https://www.open-overheid.nl/documenten/2025/04/16/dwars-door-de-orde)
van Arre Zuurmond, opgesteld in zijn rol als regeringscommissaris
Informatiehuishouding. In dit rapport analyseert hij waarom de overheid
structureel moeite heeft om publieke waarde te leveren in een
gedigitaliseerde samenleving.

Zuurmond laat zien dat informatie geen ondersteunend middel is, maar een
volwaardige productiefactor – naast bevoegdheden, geld en mensen. De
huidige inrichting van de overheid, gebaseerd op verkokering en
systemen, sluit daar onvoldoende op aan. Daardoor ontstaan problemen met
samenhang, transparantie en uitvoerbaarheid van beleid. Het rapport
maakt duidelijk dat keuzes in informatiearchitectuur direct raken aan
het functioneren van de overheid zelf.

Een concreet illustratief voorbeeld is de kinderopvangtoeslagaffaire.
Uit [onderzoek van de Inspectie
Overheidsinformatie](https://www.inspectie-oe.nl/actueel/nieuws/2021/04/22/rapport-toeslagen)
bleek dat niet alleen documenten ontbraken, maar dat de
informatiehuishouding zelf structurele tekortkomingen kende.
Dossiervorming was onvolledig, informatie was verspreid over
verschillende systemen, de sturing op informatiebeheer was beperkt en
besluiten bleken achteraf moeilijk of niet volledig te reconstrueren.
Dit had directe gevolgen voor burgers, de mogelijkheid om verantwoording
af te leggen en de informatievoorziening aan de Tweede Kamer.

Het huidige herstelproces van de affaire laat zien hoe fundamenteel deze
problematiek is. Om individuele dossiers opnieuw op te bouwen, moeten
gegevens worden verzameld uit uiteenlopende bronnen, waaronder
verschillende informatiesystemen, e-mails, telefoonnotities, scans,
interne documenten en papieren archieven. Pas door deze informatie
achteraf opnieuw samen te brengen kan worden gereconstrueerd hoe
besluiten tot stand zijn gekomen en welke informatie daarbij beschikbaar
was.

Hoewel de toeslagenaffaire zich afspeelde binnen de Belastingdienst, is
de onderliggende informatiekundige problematiek niet uniek. Binnen
gemeenten is de informatievoorziening historisch ingericht rondom
afzonderlijke processen, applicaties en organisatieonderdelen. Gegevens
worden op meerdere plaatsen vastgelegd, verschillende systemen bevatten
elk een deel van de werkelijkheid en samenhang ontstaat vaak pas
achteraf via koppelingen, rapportages of handmatige reconstructie. De
toeslagenaffaire maakt daarmee zichtbaar welke risico's ontstaan wanneer
de informatiehuishouding onvoldoende integraal is ingericht.

### Businesscase

Gemeenten zijn voor het uitvoeren van wettelijke taken nagenoeg volledig
afhankelijk van enkele honderden private eigenaren van software. De
private sector investeert risicodragend in softwareontwikkeling.
Gemeenten nemen deze software af via licenties, SaaS-diensten of
implementatieprojecten.

De huidige gemeentelijke informatievoorziening bestaat uit een groot
aantal afzonderlijke applicaties, ieder met een eigen gegevensmodel,
technische architectuur, beveiligingsmodel en beheerorganisatie. Om deze
applicaties gezamenlijk gemeentelijke dienstverlening te laten
ondersteunen, is een omvangrijk netwerk van koppelingen noodzakelijk.
Iedere koppeling vraagt om afspraken over semantiek, techniek,
beveiliging, beheer en versiebeheer. Naarmate het aantal applicaties
groeit, neemt ook de complexiteit van het totale landschap exponentieel
toe.

De kosten beperken zich daarbij niet tot softwarelicenties. Iedere
afzonderlijke applicatie vraagt gedurende haar gehele levenscyclus om
architectuur, informatiebeheer, informatiebeveiliging,
contractmanagement, implementatie, functioneel beheer, technisch beheer,
projectleiding en opleidingen. Ook wijzigingen in wet- en regelgeving
moeten per applicatie opnieuw worden ontworpen, ontwikkeld, getest en
geïmplementeerd. Hierdoor worden dezelfde werkzaamheden binnen gemeenten
en leveranciers steeds opnieuw uitgevoerd.

Daarnaast brengen aanbestedingen en leveranciersmanagement aanzienlijke
organisatorische kosten met zich mee. Voor vrijwel iedere grotere
applicatie worden afzonderlijke aanbestedingstrajecten doorlopen,
contracten beheerd en implementaties uitgevoerd. De sterke
afhankelijkheid van individuele leveranciers leidt bovendien tot vendor
lock-in: gegevens, processen en functionaliteit zijn vaak nauw verweven
met één specifieke oplossing, waardoor migratie naar een alternatief
complex, risicovol en kostbaar is. Dit beperkt de concurrentie, remt
innovatie en verzwakt de onderhandelingspositie van gemeenten.

Vanuit bedrijfseconomisch perspectief ontstaat hierdoor een situatie
waarin zowel ontwikkelcapaciteit als publieke middelen versnipperd
worden ingezet. Schaarse expertise op het gebied van architectuur,
informatievoorziening, security en softwareontwikkeling wordt verdeeld
over honderden grotendeels vergelijkbare oplossingen, terwijl veel
functionaliteit – zoals zaakafhandeling, klantregistratie, autorisatie,
berichtenverkeer, documentgeneratie en logging – in de kern generiek van
aard is.

<img
src="../media/media/image4.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Overzicht drijfveren

Bovenstaande ontwikkelingen kunnen worden samengevat in een aantal
samenhangende interne en externe drijfveren. Gezamenlijk maken zij
duidelijk waarom een fundamenteel andere inrichting van de gemeentelijke
informatievoorziening noodzakelijk is.

De onderstaande overzichten brengen deze drijfveren samen en laten zien
hoe zij leiden tot concrete architectuurkundige knelpunten. Deze vormen
gezamenlijk de onderbouwing voor de architectuurprincipes en
ontwerpkeuzes die in de volgende hoofdstukken worden uitgewerkt.

#### Interne drijfveren

De interne drijfveren komen voort uit de wijze waarop gemeenten hun
informatievoorziening en dienstverlening historisch hebben ingericht.
Versnipperde applicatielandschappen, monolithische systemen, beperkte
regie op informatie en oplopende beheerkosten leiden gezamenlijk tot een
informatievoorziening die steeds moeilijker kan inspelen op nieuwe
maatschappelijke en bestuurlijke opgaven.

De figuur laat zien hoe deze organisatorische, informatiekundige en
financiële drijfveren uiteindelijk resulteren in architectuurkundige
knelpunten, zoals beperkte datakwaliteit, verlies van regie,
fragmentatie van dienstverlening en een moeilijk beheersbare
kostenstructuur. Deze interne factoren vormen de directe aanleiding voor
de ontwikkeling van een gezamenlijk Platform Dienstverlening.

<img
src="../media/media/image5.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, schermopname, diagram, lijn Door AI gegenereerde inhoud is mogelijk onjuist." />

#### Externe drijfveren

Naast de interne ontwikkelingen worden gemeenten geconfronteerd met een
aantal externe ontwikkelingen waarop de huidige informatievoorziening
onvoldoende is ingericht. Toenemende wet- en regelgeving, een beperkte
en geconcentreerde softwaremarkt, groeiende eisen aan digitale
weerbaarheid, maatschappelijke verwachtingen en snelle technologische
ontwikkelingen vergroten de druk op de gemeentelijke
informatievoorziening.

De figuur laat zien hoe deze externe ontwikkelingen leiden tot risico's
op het gebied van continuïteit, transparantie, innovatievermogen en
bestuurlijke wendbaarheid. Zij benadrukken de noodzaak om te investeren
in een open, modulaire en toekomstbestendige architectuur die gemeenten
meer autonomie geeft en beter kan meebewegen met maatschappelijke en
technologische veranderingen.

<img
src="../media/media/image6.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, schermopname, diagram, lijn Door AI gegenereerde inhoud is mogelijk onjuist." />

## Common Ground & Platform Dienstverlening

De beschreven ontwikkelingen laten zien dat de huidige uitdagingen niet
kunnen worden opgelost door afzonderlijke applicaties te vervangen of
nieuwe koppelingen toe te voegen. De kern van het probleem ligt in de
manier waarop de gemeentelijke informatievoorziening is ingericht.
Zolang gegevens, functionaliteit en processen opgesloten blijven in
afzonderlijke systemen, zullen complexiteit, kosten en afhankelijkheden
blijven toenemen.

De informatiekundige visie Common Ground kiest daarom voor een
fundamenteel andere benadering. Niet de applicatie, maar gegevens,
dienstverlening en herbruikbare functionaliteit vormen het uitgangspunt
voor de inrichting van de informatievoorziening.

#### Van applicaties naar een platform

Het Platform Dienstverlening vormt de concrete uitwerking van deze
visie. Het is de referentie-implementatie van de Enterprisearchitectuur:
een gezamenlijk ontwikkeld platform van generieke voorzieningen waarmee
gemeenten hun dienstverlening kunnen realiseren. Gemeenten dragen actief
bij aan zowel de architectuur als de realisatie van het platform, samen
met leveranciers en landelijke partijen. Het bereidt daarmee voor op
realisatie van Common Ground in een landelijke organisatie ([Gemeenten
zetten koers naar collectieve digitalisering   \|
VNG](https://vng.nl/nieuws/gemeenten-zetten-koers-naar-collectieve-digitalisering))

Waar gemeenten vandaag investeren in honderden afzonderlijke applicaties
die grotendeels dezelfde functies bevatten, brengt het platform deze
generieke functionaliteit samen in één samenhangend ecosysteem van
herbruikbare voorzieningen. Functionaliteit zoals klantregistratie,
zaakafhandeling, berichten, formulieren en workflowhoeft daardoor niet
langer telkens opnieuw te worden ontwikkeld of aangeschaft.

Hierdoor verschuift de investering van afzonderlijke systemen naar
gezamenlijk ontwikkelde generieke voorzieningen die door meerdere
gemeenten kunnen worden hergebruikt en doorontwikkeld.

#### Kwaliteit by design

Gemeenten worden geconfronteerd met steeds hogere eisen aan de
informatievoorziening (denk aan informatiebeveiliging,
privacybescherming, informatiebeheer). Het afzonderlijk implementeren,
onderhouden en aantoonbaar borgen van deze eisen in honderden
applicaties leidt tot hoge kosten, verschillen in kwaliteit en een
toenemende beheerslast.

Binnen het Platform Dienstverlening worden deze kwaliteitseisen vanaf
het ontwerp integraal meegenomen. Gemeenten kunnen steunen op
voorzieningen die voldoen aan wet- en regelgeving, architectuurkaders en
vereiste kwaliteitsnormen. Dit vergroot niet alleen de kwaliteit en
betrouwbaarheid van de dienstverlening, maar vermindert ook de
uitvoeringslast voor individuele gemeenten.

#### Gegevens als fundament

Een derde fundamentele verandering is dat gegevens niet langer onderdeel
zijn van individuele applicaties, maar een zelfstandige plaats krijgen
binnen de architectuur.

Gegevens worden eenmalig vastgelegd bij de daarvoor aangewezen bron en
vervolgens via gestandaardiseerde services beschikbaar gesteld aan
processen, medewerkers en inwoners. Vastlegging, interpretatie en
presentatie worden daarmee van elkaar gescheiden. Hierdoor ontstaat één
gedeelde informatiebasis waarin besluiten transparant, controleerbaar en
herleidbaar zijn.

Deze benadering sluit aan bij de informatiekundige principes uit *Dwars
door de Orde*: gegevens vormen niet langer een bijproduct van processen,
maar het fundament waarop dienstverlening wordt georganiseerd.

Een belangrijk aandachtspunt daarbij is dat de scheiding tussen
brongegevens, context en presentatie niet mag leiden tot verlies van
samenhang of beheerbaarheid van informatie. Het platform borgt daarom
dat gegevens, metadata, context, proceshistorie en beslisinformatie
onlosmakelijk met elkaar verbonden blijven. Door middel van
contextregistratie, datalineage en gestandaardiseerde metadata blijft de
herkomst, betekenis, samenhang en levenscyclus van informatie
aantoonbaar en duurzaam toegankelijk. Daarmee wordt informatiebeheer
niet gezien als een activiteit achteraf, maar als een integraal
onderdeel van de informatievoorziening vanaf het moment van registratie.

#### Verandering van de softwaremarkt

De gemeentelijke softwaremarkt bestaat grofweg uit drie segmenten:

- **Gemeentespecifieke software** voor de uitvoering van gemeentelijke
  dienstverlening;

- **Standaardsoftware (commodities)**, zoals HR-, financiële en
  kantoorautomatiseringssystemen;

- **Diensten**, waaronder implementatie, beheer, consultancy en
  softwareontwikkeling.

Het Platform Dienstverlening richt zich primair op het eerste segment:
de **gemeentespecifieke software**. Juist in dit segment wordt vandaag
veel vergelijkbare functionaliteit door verschillende leveranciers
onafhankelijk van elkaar ontwikkeld, onderhouden en geïmplementeerd. Dit
leidt tot een hoge mate van duplicatie, complexe integraties en
oplopende maatschappelijke kosten.

Door generieke functionaliteit gezamenlijk te ontwikkelen en als open
bouwstenen beschikbaar te stellen, verschuift de markt van complete,
gesloten gemeentelijke suites naar een ecosysteem van herbruikbare
componenten. Leveranciers blijven een belangrijke rol spelen, maar
concurreren niet langer op generieke basisfunctionaliteit. Hun
onderscheidend vermogen verschuift naar domeinspecifieke
functionaliteit, implementatie, innovatie en dienstverlening.

Voor het segment **Diensten** betekent deze ontwikkeling eveneens een
fundamentele verandering. Waar gemeenten nu afzonderlijk investeren in
architectuur, implementaties, beheer en consultancy, ontstaat
geleidelijk een gezamenlijk ontwikkel- en beheerproces voor generieke
voorzieningen. Hierdoor kan schaarse expertise worden gebundeld,
ontstaat meer continuïteit en neemt de afhankelijkheid van externe
inhuur af.

De beoogde eindsituatie is daarmee niet een overheid die alles zelf
ontwikkelt, maar een gezonde markt waarin gemeenten gezamenlijk
investeren, terwijl leveranciers zich onderscheiden met toegevoegde
waarde boven op dat fundament.

## Resultaat

Aanvullend op bovenstaande volgt hier een voor/na schets van de
transitie Common Ground: een overzicht van de brede doelsituatie voor
gemeenten.

| **Was** | **Wordt** |
|----|----|
| Veel systemen – overwegend closed source – met overlappende functionaliteit | Enkelvoudige, overwegend transparante en herbruikbare open-sourcecomponenten, zonder overlappende functionaliteit. |
| Relatief autonome keuzes bij organisatieonderdelen voor proces- en systeeminrichting, maar beperkt door de (on)mogelijkheden van leverancierssystemen. | Verbonden organisatieonderdelen die optimaal functioneren voor de gehele organisatie, zonder verlies aan functionaliteit; lagere niveaus krijgen meer keuzevrijheid in de inrichting van processen en systemen. |
| Gegevensredundantie en gegevensvervuiling; gegevens opgeslagen in leverancierspakketten; moeizaam hergebruik van gegevens van andere bronhouders. | Geen redundante of vervuilde gegevens; gegevens eenmalig opgeslagen in de gemeentelijke gegevenslaag conform het GGM (Gemeentelijk Gegevensmodel); eenvoudig hergebruik van gegevens van andere bronhouders. |
| Beveiliging, logging, autorisatie, auditing en andere generieke voorzieningen worden per applicatie afzonderlijk ontwikkeld, ingericht en beheerd. | Generieke voorzieningen zoals beveiliging, logging, auditing en autorisatie worden éénmaal gezamenlijk ontwikkeld, beheerd en continu doorontwikkeld als herbruikbare platformdiensten. |
| Iedere gemeente voor zich; inefficiënt gebruik van gemeenschapsgeld. | Vraagharmonisatie en -bundeling; samen organiseren; efficiënt gebruik van gemeenschapsgeld. |
| Gemeenten slagen er niet in alle benodigde IV- en ICT-specialisten te werven en te behouden om goed in regie te komen. | Door samenwerking verdelen we het IV- en ICT-werk over schaarse specialisten en komen we wél goed in regie. |
| Gebrek aan transparantie over gegevensgebruik schaadt het vertrouwen in de overheid. | Common Ground maakt het mogelijk gegevens te delen met burgers en bedrijven en daarmee het vertrouwen in de overheid te vergroten. |
| Bottom-up informatiesystemen per domein (“ieder wetje een pakketje”). | Top-down generieke informatiesystemen (componenten) met domeinspecifieke aanvullingen. |
| Onvolkomen markt tussen vraag (gemeenten) en aanbod (softwareleveranciers met vaak een oligopolie). | Transparante markt met lage toetredingsdrempels. |
| Gemeente leunt op de markt. | Samenwerkende gemeenten regisseren de markt. |
| Weinig innovatie. | Snelle innovatie. |
| Hoge migratiekosten. | Lage migratiekosten dankzij standaardcomponenten en data in eigen beheer. |
| Hoog in de markt inkopen (gereed product; investering en risico bij leverancier). | Lager in de markt inkopen (diensten, expertise en capaciteit; mede-eigenaarschap en -risico in doorontwikkeling; investering en risico meer bij gemeenten). |
| Regie-, inkoop- en beheerorganisatie per gemeente. | Voortdurende ontwikkel- en doorontwikkelorganisatie. |

## Conclusie

Bovenstaand wordt context, uitdaging en doel geschetst waar de
gemeentelijke informatievoorziening voor staat. Deze analyse vormt de
aanleiding voor de architectuur die in de volgende hoofdstukken wordt
uitgewerkt.
