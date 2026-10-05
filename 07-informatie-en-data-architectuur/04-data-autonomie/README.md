# Data-autonomie

Autonomie wordt door
[DICTU](https://www.dictu.nl/sites/default/files/bestanden/website/DICTU%20Toetsingsinstrument%20Soevereiniteit%20Clouddiensten%20v1.0.1.pdf)
gedefinieerd als de combinatie van zelfbeschikking en onafhankelijkheid.
Voor data-autonomie betekent dit dat zowel gemeenten als inwoners
zeggenschap behouden over hun gegevens en kunnen bepalen hoe deze worden
vastgelegd, gebruikt, gedeeld en beheerd. Dit is vastgelegd in **het
[Principe: Data-autonomie](../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-data-autonomie)**, en dit wordt
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
