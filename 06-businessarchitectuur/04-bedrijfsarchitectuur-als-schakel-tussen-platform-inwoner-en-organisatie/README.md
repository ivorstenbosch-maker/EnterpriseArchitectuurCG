# Bedrijfsarchitectuur als schakel tussen platform, inwoner en organisatie

De bedrijfsarchitectuur vormt de eerste concrete uitwerking van de
overkoepelende architectuurprincipes uit de visie. Waar deze principes
richting geven aan de architectuur als geheel, beschrijft dit hoofdstuk
hoe zij worden toegepast bij het ontwerpen van gemeentelijke
dienstverlening.

In het bijzonder worden de volgende principes uitgewerkt:

- **[Principe: Architectuurgedreven
  vernieuwing](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-architectuurgedreven-vernieuwing):** nieuwe
  dienstverlening wordt ontworpen vanuit de gewenste waardestroom,
  businesscapabilities en architectuur, niet vanuit bestaande
  applicaties.

- **[Principe: Expliciete
  bedrijfslogica](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-expliciete-bedrijfslogica):**
  Bedrijfsprocessen, beslisregels en gegevens worden als afzonderlijke
  architectuurelementen gemodelleerd. Beslisregels worden waar mogelijk
  centraal beheerd en herbruikbaar vastgelegd, zodat zij consistent
  kunnen worden toegepast in meerdere processen, BusinessServices en
  kanalen.

- **[Principe: Generiek vóór
  specifiek](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-generiek-vóór-specifiek):** generieke
  BusinessServices, procesfragmenten en voorzieningen worden eerst
  hergebruikt voordat domeinspecifieke oplossingen worden ontwikkeld.

- **[Principe: Beleidsruimte als
  basis](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-beleidsruimte-als-basis):** waar de gemeentelijke
  verantwoordelijkheid aantoonbaar lokale keuzes vraagt, moet de
  generieke functionaliteit die keuzes tijdig en uitvoerbaar kunnen
  ondersteunen.

- **[Principe: Hergebruik](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-hergebruik):** zowel software,
  gegevens, procesinrichting als bedrijfslogica worden ontworpen voor
  meervoudig gebruik binnen verschillende processen, domeinen en
  gemeenten.

Het Platform Dienstverlening biedt de technische mogelijkheden om
gemeentelijke dienstverlening fundamenteel anders in te richten.
Centrale gegevensopslag, herbruikbare services, expliciete beslisregels
en fijnmazige autorisatie maken het mogelijk om dienstverlening
domeinoverstijgend te organiseren. Deze mogelijkheden leiden echter niet
vanzelf tot betere dienstverlening. Zij vragen om een
bedrijfsarchitectuur die de inrichting van processen, rollen en
verantwoordelijkheden afstemt op de mogelijkheden van het platform.

Dit betekent onder meer dat:

- Processen worden ontworpen rondom gedeelde gegevens en
  dienstverlening, in plaats van rondom teams of applicaties;

- Verantwoordelijkheden verschuiven van eigenaarschap van systemen naar
  regie op gegevens, besluiten en dienstverlening;

- Samenwerking over domeinen heen de norm wordt, omdat dezelfde
  informatiebasis wordt gebruikt;

- Autorisatie wordt gebaseerd op de grondslag voor het gebruik van
  informatie en niet uitsluitend op de applicatie of de organisatorische
  rol of functie van een medewerker.

De bedrijfsarchitectuur vormt daarmee de verbinding tussen de
informatiearchitectuur en de dagelijkse uitvoering. Zij vertaalt de
mogelijkheden van het platform naar samenhangende dienstverlening,
eenduidige verantwoordelijkheden en consistente werkprocessen.

### MijnServices

[MijnServices](https://vng.nl/MijnServices) is een initiatief binnen VNG
dat zich richt op het ontwikkelen van herbruikbare servicedesigns. Een
servicedesign
([voorbeeld](https://nl-design-system.github.io/mijn-services/?path=/story/mijn-profiel-1--default))
is de gestandaardiseerde beschrijving van de gewenste gebruikerservaring
en interacties rondom een overheidsdienst. De bron voor de MijnServices
is de implementatie van het Platform Dienstverlening in de Gemeente Den
Haag. Dit is in een landelijk programma opgeschaald naar overheidsbrede
servicedesigns.

Voorbeelden zijn MijnZaken, MijnTaken, MijnBerichten,
MijnContactmomenten en MijnProfiel. Gezamenlijk bieden zij een
consistente manier waarop inwoners hun zaken met de overheid kunnen
regelen, ongeacht de onderliggende organisatie of het beleidsdomein.

MijnServices zijn nadrukkelijk ontwikkeld vanuit het perspectief van de
inwoner. Zij standaardiseren de **buitenkant** van de dienstverlening:
de manier waarop informatie wordt aangeboden, aanvragen worden ingediend
en de voortgang van dienstverlening inzichtelijk wordt gemaakt. Daarmee
leveren zij een belangrijke bijdrage aan één herkenbare digitale
overheid.

Voor de bedrijfsarchitectuur zijn MijnServices echter niet voldoende.
Zij beschrijven wat een inwoner ziet en ervaart, maar niet hoe de
dienstverlening intern wordt georganiseerd en uitgevoerd. Aspecten zoals
proceslogica, besluitvorming, taakverdeling, gegevensgebruik en
samenwerking tussen medewerkers en domeinen vallen buiten de scope van
MijnServices.

Om ook deze interne samenhang te kunnen modelleren introduceert het
Platform Dienstverlening het concept **BusinessService**. Waar
MijnServices de interactie met inwoners standaardiseren, structureren
BusinessServices de uitvoering van het werk. Samen vormen zij de
verbinding tussen de buitenwereld en de interne bedrijfsvoering.

<img
src="../../media/media/image17.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### BusinessServices als ontwerpprincipe

Om samenhang tussen het interne proces en de presentatie ervan aan de
inwoner te realiseren introduceert het Platform Dienstverlening het
concept **BusinessService**. Een BusinessService vormt de herbruikbare
functionele bouwsteen waaruit gemeentelijke dienstverlening wordt
samengesteld. Het wordt hier met twee hoofdletters geschreven om het te
onderscheiden van – bijvoorbeeld – het businessserviceconcept in
Archimate. Het concept wordt verder concreet gemaakt in de bijlage
[BusinessServices](#bijlage---businessservices).

Een BusinessService omvat een logisch samenhangend geheel van gegevens,
beslisregels, proceslogica en interactie rondom één processtap. Zij
verbindt de verschillende architectuurlagen: gegevens uit registraties,
proces- en beslislogica, interactie met inwoners en medewerkers en de
uiteindelijke vastlegging van resultaten

Op de interactielaag verzorgt zij bijvoorbeeld formulieren of
klantinteractie, op de proceslaag workflow en beslislogica, op de
servicelaag API's en validaties en op de gegevenslaag de consistente
vastlegging in generieke registraties en domeinregistraties.

Hierdoor verschuift het ontwerp van de bedrijfsarchitectuur van
end-to-end processen naar een verzameling herbruikbare bouwblokken die
in verschillende processen kunnen worden toegepast. Processen worden
niet langer volledig op maat ontworpen, maar samengesteld uit
BusinessServices die ieder een duidelijke verantwoordelijkheid hebben.

Dit betekent onder andere dat:

- Processen worden samengesteld uit BusinessServices;

- Iedere BusinessService expliciet vastlegt welke gegevens worden
  gebruikt, gewijzigd en geregistreerd;

- Beslisregels, validaties en interacties éénmaal worden ingericht en
  vervolgens breed worden hergebruikt;

  - Beslisregels vormen een expliciet onderdeel van de dienstverlening
    en beschrijven hoe wetgeving en beleid worden toegepast. Door
    beslisregels los van processen vast te leggen, kunnen zij
    onafhankelijk worden beheerd, hergebruikt en gewijzigd;

- Dezelfde BusinessService in meerdere processen, domeinen en vormen van
  dienstverlening kan worden toegepast.

### BusinessServices als herbruikbare bouwstenen

BusinessServices zijn nadrukkelijk bedoeld als **herbruikbare
bouwstenen**. Niet alleen de onderliggende softwarecomponenten worden
gezamenlijk ontwikkeld, maar ook de inrichting daarvan. Gemeenten hoeven
veel voorkomende dienstverleningsprocessen daardoor niet telkens opnieuw
te ontwerpen.

Een BusinessService kan bestaan uit een combinatie van:

- Procesblauwdrukken (Process Blueprints);

- Herbruikbare bouwblokken, zoals formulieren, subprocessen, zaaktypen
  of configuraties;

- Beslisregels;

- Plugins voor generieke uitbreidingen en koppelingen;

- Document- en archiefconfiguraties.

Deze artefacten kunnen tussen gemeenten worden gedeeld via voorzieningen
zoals **Samen Delen** en de **GZAC Exchange**. Gemeenten kunnen
bestaande inrichting hergebruiken, lokaal configureren en waar nodig
uitbreiden met eigen functionaliteit. Hierdoor ontstaat niet alleen
hergebruik van software, maar ook van kennis, procesontwerpen en bewezen
implementaties.

Hiermee krijgt het principe **Hergebruik** een bredere betekenis dan
uitsluitend softwarehergebruik. Gemeenten delen niet alleen broncode,
maar ook de inrichting van processen, formulieren, beslisregels,
configuraties en businessservices. De bedrijfsarchitectuur ontwikkelt
zich daardoor tot een gezamenlijke, levende bibliotheek van herbruikbare
dienstverleningspatronen die continu wordt verbeterd op basis van
implementaties in de praktijk.
