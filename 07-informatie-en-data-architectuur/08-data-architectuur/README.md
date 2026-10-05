# Data-architectuur

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
[**Principe: Data bij de bron**](../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-data-bij-de-bron).

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
src="../../media/media/image19.png"
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
