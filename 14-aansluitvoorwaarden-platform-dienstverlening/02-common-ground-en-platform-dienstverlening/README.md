# Common Ground en Platform Dienstverlening

Het [Platform
Dienstverlening](https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/introductie/enterprise-architectuur)
is de implementatie van Common Ground binnen de G4-gemeenten. Het vormt
de referentiearchitectuur voor de gemeentelijke informatievoorziening en
biedt een samenhangend geheel van software (generieke registraties,
dataservices, integratievoorzieningen en procesapplicaties) waarmee de
gemeentelijke dienstverlening op een generieke manier kan worden
gerealiseerd. Het volgt een [Enterprise
architectuur](https://dienstverleningsplatform.gitbook.io/platform-generieke-dienstverlening-public/introductie/enterprise-architectuur)
en realiseert een ontkoppeld landschap van (micro)services volgens het
model van Common Ground:

<img
src="../../media/media/image35.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Bij een nieuwe functionele behoefte (of een bestaande die ingevuld
wordt, maar waarvan de software niet langer voldoet of contractueel
eindigt) wordt eerst onderzocht of deze kan worden ingevuld met de
bestaande voorzieningen van het Platform Dienstverlening. Het platform
wordt maximaal benut voordat wordt besloten nieuwe software te
ontwikkelen of een SaaS-oplossing aan te schaffen. Dit proces volgt een
beslisboom waarin twee patronen worden onderscheiden, die hieronder
worden toegelicht.

<img
src="../../media/media/image36.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Patroon A: Realisatie in Platform Dienstverlening

Er wordt eerst vastgesteld of de gevraagde functionaliteit reeds
beschikbaar is binnen het Platform Dienstverlening of met beperkte
uitbreiding van bestaande platformservices kan worden gerealiseerd.

Wanneer de benodigde functionaliteit nog niet beschikbaar is, wordt
beoordeeld of deze als nieuwe generieke platformservice kan worden
ontwikkeld en opgenomen in het Platform Dienstverlening. Daarbij wordt
onder meer gekeken naar de generieke toepasbaarheid, de bijdrage aan de
referentiearchitectuur, de verwachte herbruikbaarheid door meerdere
gemeenten en de aansluiting op de roadmap van het Platform
Dienstverlening.

Een platformservice wordt onderdeel van het Platform Dienstverlening
zelf. De component:

- Levert generieke functionaliteit;

- Wordt opgenomen in de platformarchitectuur;

- Valt onder de architectuurgovernance van het platform;

- Wordt gezamenlijk beheerd;

- Maakt onderdeel uit van de referentie-implementatie zoals die door G4
  wordt vastgesteld.

Voor platformservices gelden zowel de [(niet-)functionele
aansluitvoorwaarden Common Ground](../04-aansluitvoorwaarden-patroon-b/README.md#aansluitvoorwaarden-patroon-b) als
[aanvullende platformeisen](../05-aanvullende-eisen-voor-platformservices/README.md#aanvullende-eisen-voor-platformservices).

### Patroon B: Aansluiten van een (SaaS-)oplossing

Alleen wanneer ontwikkeling als platformservice niet doelmatig of
haalbaar is, bijvoorbeeld vanwege de complexiteit, beperkte generieke
toepasbaarheid, beschikbare ontwikkelcapaciteit of gewenste
implementatiesnelheid, wordt – tijdelijk – gekozen voor een
SaaS-oplossing. Het is van belang dat deze ontwikkeling wordt
geadresseerd bij de PO’s van het Platform, zodat parallel gewerkt wordt
aan doorontwikkeling en de capabilities beschikbaar komen.

Als gekozen wordt voor een SaaS-oplossing is het vereist dat deze
integreert met het Platform Dienstverlening. Dat betekent voldoen aan de
aansluitvoorwaarden van het Platform Dienstverlening en gebruik maken
van de generieke registraties, API's en integratievoorzieningen.

Een aangesloten applicatie blijft eigendom en verantwoordelijkheid van
de leverancier (of community) en maakt geen onderdeel uit van het
Platform Dienstverlening. De applicatie maakt gebruik van de generieke
voorzieningen van het platform, zoals registraties, dataservices, API's
en integratievoorzieningen. Het Platform biedt hier ruimte voor in de
vorm van generieke aansluitingen (“stekkers”) op de gegevenslaag.

<img
src="../../media/media/image37.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

Leveranciers en communities behouden vrijheid in de inrichting en
implementatie van hun software, voor zover de applicatie voldoet aan de
aansluitvoorwaarden van het Platform Dienstverlening.
