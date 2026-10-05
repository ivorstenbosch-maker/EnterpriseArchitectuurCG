# Architectuur van API's

API's vormen de gestandaardiseerde contractlaag tussen services binnen
het Platform Dienstverlening. Zij bepalen hoe gegevens en
functionaliteit beschikbaar worden gesteld aan processen,
gebruikersinterfaces en externe afnemers.

### Typen API's

Binnen de literatuur worden verschillende typen API's onderscheiden. De
terminologie verschilt enigszins tussen leveranciers en
architectuurmethoden, maar de gehanteerde indeling is grotendeels
vergelijkbaar. Binnen het Platform Dienstverlening worden de volgende
typen onderscheiden.

- **System API**

  - Een System API ontsluit één registratie of bronvoorziening. Zij
    vormt de gestandaardiseerde toegang tot gegevens binnen één
    afgebakend domein.

  - Binnen deze architectuur worden twee varianten onderscheiden:

    - CRUD API's;

    - Handelingsgedreven API's.

- **Process API**

  - Een Process API combineert meerdere bronnen of registraties om
    processtappen of samengestelde gegevens aan te bieden.

  - Binnen het Platform Dienstverlening wordt deze architectuurstijl
    niet toegepast. Procesorkestratie behoort tot de proceslaag
    (BusinessServices, BPMN en DMN) en niet tot de API-laag. Hierdoor
    blijft de scheiding tussen data, handelingen en processen behouden.

- **Experience API**

  - Een Experience API presenteert gegevens in een vorm die aansluit op
    een specifiek kanaal of gebruikersgroep. Zij combineert bestaande
    API's zonder eigenaar te worden van gegevens of proceslogica.

  - Er is – vooralsnog – geen usecase voor experience API’s op
    registraties; via IKO (Integraal Klant- en Objectbeeld) kan via de
    BFF wel een experience-API opgebouwd worden.

### Handelingsgedreven API's

Het Platform Dienstverlening kiest voor **handelingsgedreven API's** als
standaard voor mutaties op registraties. Waar traditionele CRUD-API's
zich richten op technische operaties (*Create*, *Read*, *Update*,
*Delete*), beschrijven handelingsgedreven API's expliciet de
betekenisvolle handeling die binnen het domein wordt uitgevoerd.

Voorbeelden zijn:

- Registreer contactmoment

- Start zaak

- Publiceer document

- Sluit zaak

Hierdoor sluit het contract van de API aan op de taal van de business en
niet op de interne structuur van het datamodel. Deze architectuurkeuze
ondersteunt meerdere uitgangspunten van het Platform Dienstverlening.
Handelingsgedreven API's:

- Maken de businessintentie expliciet.

- Centraliseren validaties, statustransities en businessregels binnen
  één handeling.

- Verminderen het aantal technische interacties tussen afnemer en
  platform.

- Ondersteunen fijnmazige autorisatie op betekenisvolle handelingen.

- Sluiten direct aan op BusinessServices uit de bedrijfsarchitectuur.

- Leveren betere auditbaarheid en verwerkingsverantwoording op.
