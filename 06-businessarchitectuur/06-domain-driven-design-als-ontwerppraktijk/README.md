# Domain-Driven Design als ontwerppraktijk

*[Domain-Driven
Design](https://www.bol.com/nl/nl/f/domain-driven-design/9200000002151217/)
(DDD)* vormt binnen het Platform Dienstverlening de
**voorkeursontwerppraktijk** voor het toepassen van het
architectuurprincipe **Architectuurgedreven vernieuwing (4.4.1)**. Waar
het architectuurprincipe richting geeft aan het *wat*, biedt DDD de
methodiek voor het *hoe*: het identificeren, afbakenen en ontwerpen van
BusinessServices vanuit de werkelijkheid van het domein.

DDD wordt niet alleen gebruikt om grenzen tussen services te ontdekken,
maar ook om onderscheid te maken tussen generieke, domeinoverstijgende
concepten en domeinspecifieke verantwoordelijkheden. Dit voorkomt dat
ieder domein eigen varianten van dezelfde dienstverleningsconcepten
introduceert en bevordert hergebruik, interoperabiliteit en een
consistente gebruikerservaring binnen het platform.

Het dienstverleningsdomein, met concepten zoals **klant**, **zaak**,
**taak** **en** **bericht**, vormt zo'n metadomein. Deze concepten
behoren niet tot één specifiek beleids- of uitvoeringsdomein, maar
ondersteunen dienstverlening in brede zin.

De afbakening van deze metadomeinen geldt als uitgangspunt voor de
inrichting van het platform. Binnen die kaders behouden domeinspecifieke
implementaties de vrijheid om eigen bounded contexts, domeinmodellen en
bedrijfsobjecten te definiëren die aansluiten bij de behoeften van het
betreffende vakgebied.

Centraal daarin staat het ontwikkelen van een **gedeelde taal
(ubiquitous language)** tussen beleid, uitvoering en IT. Dit sluit
direct aan op het uitgangspunt van Common Ground: dat feiten, begrippen
en beslissingen eenduidig en herleidbaar moeten zijn. Door deze gedeelde
taal te hanteren in zowel processen, gegevensmodellen als services,
ontstaat consistentie over de gehele keten.

DDD helpt om BusinessServices op een natuurlijke en samenhangende manier
te identificeren en af te bakenen. Door het domein op te delen in
*bounded contexts* wordt duidelijk:

- Welke concepten bij elkaar horen,

- Waar verantwoordelijkheden liggen, en

- Waar logische grenzen tussen services moeten worden getrokken.

Deze afbakening voorkomt dat services te groot, te klein of te
afhankelijk worden. Het ondersteunt daarmee direct de principes uit de
BusinessService-benadering, zoals cohesie, herbruikbaarheid en
duidelijke verantwoordelijkheid.

<img
src="../../media/media/image18.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />
