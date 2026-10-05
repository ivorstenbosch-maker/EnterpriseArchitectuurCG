# Data bij de bron

Het [**Principe: Data bij de bron**](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-data-bij-de-bron) is een
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
    implementatie](../../11-toegepaste-patronen/07-implementatiepatronen-patroon-a-patroon-b/README.md#patroon-b-hybride-implementatie)). De bronhouder is
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
design](../06-duurzame-toegankelijkheid-by-design/README.md#duurzame-toegankelijkheid-by-design).

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
