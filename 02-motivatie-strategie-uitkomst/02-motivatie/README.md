# Motivatie

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
geschiedenis van gemeentelijke
informatisering**](#bijlage---korte-geschiedenis-van-gemeentelijke-informatisering).

De behoefte aan integrale, proactieve dienstverlening – zoals één
klantbeeld, een herkenbaar digitaal loket, omnichannel-benadering en
datagedreven werken – vraagt om een andere inrichting van de
informatievoorziening. De huidige suite-architecturen sluiten
onvoldoende aan op deze ambities.

<img
src="../../media/media/image3.png"
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
src="../../media/media/image4.png"
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
src="../../media/media/image5.png"
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
src="../../media/media/image6.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, schermopname, diagram, lijn Door AI gegenereerde inhoud is mogelijk onjuist." />
