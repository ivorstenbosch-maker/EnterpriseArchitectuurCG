# Configuratie vs. softwareontwikkeling

Binnen het Platform Dienstverlening is het onderscheid tussen
**configuratie** en **softwareontwikkeling (code)** essentieel voor het
realiseren van hergebruik en beheersbaarheid.

Er wordt onderscheid gemaakt tussen:

- **Configuratie:** Het instellen of aanpassen van bestaande software
  door middel van opties, parameters of instellingen, zonder wijziging
  van de onderliggende broncode

- **Coderen (pro-code):** Het ontwikkelen of aanpassen van broncode om
  nieuwe functionaliteit te realiseren of bestaand gedrag te wijzigen.

#### Voorkeursrichting: configuratie boven maatwerk

Binnen services wordt variatie in processen, gegevens en gedrag bij
voorkeur gerealiseerd via configuratie en als low-code voorzieningen.
Hiermee blijft functionaliteit:

- Consistent met de capabilities van de service

- Eenvoudiger te beheren en te updaten

- Herbruikbaar binnen meerdere implementaties.

Dit volgt het **[Principe: Expliciete
bedrijfslogica](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-expliciete-bedrijfslogica):**
Bedrijfsprocessen, beslisregels en gegevens worden als afzonderlijke
architectuurelementen gemodelleerd. Beslisregels worden waar mogelijk
centraal beheerd en herbruikbaar vastgelegd, zodat zij consistent kunnen
worden toegepast in meerdere processen, BusinessServices en kanalen.

Aanvullend geeft configuratie invulling aan het [**Principe:
Beleidsruimte als basis**](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-beleidsruimte-als-basis). Door
beleidsregels, termijnen, procesvarianten en andere bestuurlijke keuzes
configureerbaar te maken, kunnen gemeenten hun wettelijke en lokale
beleidsruimte benutten zonder broncode aan te passen. Hierdoor blijft de
voorziening wendbaar bij beleids- en wetswijzigingen, terwijl
tegelijkertijd wordt voorkomen dat technische standaardisatie onbedoeld
normatieve beleidskeuzes afdwingt. Configuratie is daarmee een prima
instrument om variatie tussen gemeenten te ondersteunen binnen een
generieke oplossing.

### Toepassing van beslisregels

Beslisregels worden beschouwd als een zelfstandige capability binnen de
proceslaag van het vijf-lagenmodel. Beslisregels bepalen hoe een besluit
tot stand komt; processen bepalen wanneer een beslissing wordt genomen
en registraties leveren de gegevens waarop de beslissing wordt
gebaseerd.

Het expliciet modelleren van beslisregels draagt bij aan de kern van
Common Ground: transparantie, uitlegbaarheid, herbruikbaarheid en
scheiding van verantwoordelijkheden. Hierdoor kan voor iedere beslissing
worden herleid welke gegevens, regels en processtappen zijn toegepast.
Dit anticipeert o.a. op [RegelRecht: van wet naar digitale
werking](https://regelrecht.rijks.app/).

Beslisregels worden daarom niet in applicatiecode opgenomen wanneer zij
generiek toepasbaar zijn, maar ondergebracht in een centrale
beslisservice.

#### Decision Model and Notation (DMN)

Voor het modelleren van beslisregels wordt gebruikgemaakt van Decision
Model and Notation (DMN), de internationale OMG-standaard voor het
modelleren en uitvoeren van beslislogica.

DMN maakt het mogelijk om:

- Beslisregels begrijpelijk vast te leggen voor beleid, uitvoering en
  IT;

- Beslisregels centraal te beheren en te versioneren;

- Regels meervoudig toe te passen binnen verschillende BusinessServices;

- Besluitvorming reproduceerbaar en uitlegbaar te maken;

- Wijzigingen in wet- en regelgeving door te voeren zonder
  procesmodellen of softwarecomponenten aan te passen.

  Hierdoor ontstaat een duidelijke scheiding:

- BPMN beschrijft de proceslogica;

- DMN beschrijft de beslislogica;

- Registraties leveren de benodigde gegevens;

- BusinessServices orkestreren de samenwerking.

#### Functionele eisen

De beslisvoorziening binnen het Platform Dienstverlening voldoet
minimaal aan de volgende uitgangspunten:

- Beslisregels worden vastgelegd conform de DMN-standaard;

- Beslisregels zijn als zelfstandige service (Rules as a Service) via
  API's beschikbaar;

- Beslisregels zijn versieerbaar en historisch reproduceerbaar;

- Beslisregels zijn herbruikbaar door meerdere processen en services;

- Beslisregels zijn begrijpelijk voor domeinspecialisten en juristen en
  niet uitsluitend voor ontwikkelaars;

- Beslisregels kunnen onafhankelijk van applicaties worden beheerd en
  gepubliceerd;

- Uitgevoerde beslissingen zijn herleidbaar naar de gebruikte regelset
  en versie;

- De voorziening sluit aan op de generieke platformvoorzieningen voor
  autorisatie, logging en deployment.

#### Toepassing binnen het Platform

De centrale beslisservice kan door uiteenlopende services binnen het
Platform Dienstverlening worden aangeroepen, bijvoorbeeld voor:

- Het bepalen van de vervolgstap in een proces;

- Het toetsen van wettelijke voorwaarden;

- Het uitvoeren van gemeentelijke beleidsregels;

- Het berekenen van bedragen of tarieven;

- Het bepalen van rechten of verplichtingen;

- Het aansturen van dynamische formulieren en gebruikersinterfaces.

  Hierdoor ontstaat één centrale plaats waar beslislogica wordt beheerd,
  terwijl processen, registraties en gebruikersinterfaces hiervan
  onafhankelijk kunnen evolueren.

### Toepassing van ‘maatwerk’ (pro-code)

Wanneer configuratie onvoldoende is en maatwerk noodzakelijk blijkt,
wordt eerst beoordeeld of de functionaliteit generiek toepasbaar is en
herbruikbaar is binnen meerdere gemeenten of services. Op basis daarvan
wordt bepaald of de oplossing wordt gerealiseerd als:

- Uitbreiding van een bestaande service

- Nieuwe service of

- Plugin.

#### Plugins als extensiemechanisme

Plugins vormen een gecontroleerd mechanisme om functionaliteit uit te
breiden zonder de kern van een service aan te passen.

Een plugin is geschikt wanneer deze:

- **Functioneel afgebakend** is (klein tot middelgroot en gericht op één
  specifieke uitbreiding

- **Beperkt complex** is (aansluit op bestaande extensiepunten)

- **Herbruikbaar** is (toepasbaar binnen meerdere implementaties)

- **Beperkte impact op updates** heeft (onafhankelijk van de kern te
  ontwikkelen en te deployen).

Voor plugins geldt dat een **helder contract** noodzakelijk is, waarin
de interactie tussen plugin en service formeel is vastgelegd. Dit maakt
het mogelijk om:

- Plugins onafhankelijk te ontwikkelen

- Updates gecontroleerd door te voeren

- Functionaliteit te vervangen zonder impact op de kern.
