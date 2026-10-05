# Soorten data en positionering in de architectuur

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
registraties](../../08-applicatiearchitectuur/10-architectuur-van-registraties/README.md#architectuur-van-registraties).

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
organisatie](../../06-businessarchitectuur/04-bedrijfsarchitectuur-als-schakel-tussen-platform-inwoner-en-organisatie/README.md#bedrijfsarchitectuur-als-schakel-tussen-platform-inwoner-en-organisatie).

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
