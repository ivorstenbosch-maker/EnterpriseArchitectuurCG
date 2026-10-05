# Samenwerking tussen services

Binnen een microservice-architectuur is de manier waarop services
samenwerken een cruciale ontwerpkeuze. De architectuur schrijft niet één
mechanisme voor, maar een set van gestandaardiseerde interactiepatronen,
die afhankelijk van de situatie worden toegepast.

### Basisvormen van samenwerking

Er zijn drie hoofdvormen van interactie tussen services:

- **Synchroon (request/response)**

  - Services communiceren direct via API’s en wachten op een antwoord.
    Toepasbaar bij:

    - directe validatie en

    - opvragen van actuele gegevens.

<!-- -->

- **Asynchroon (event-driven)**

  - Services communiceren via notificaties, berichten of events, zonder
    directe afhankelijkheid. Toepasbaar bij:

    - procesafhandeling

    - ketens van verwerking en

    - losgekoppelde samenwerking.

<!-- -->

- **API-compositie**

  - Meerdere services worden gecombineerd tot één samenhangende
    response. Toepasbaar bij:

    - Gebruikersinterfaces en

    - integrale beelden

  - Belangrijke patronen hierbij zijn:

    - API Gateway (centrale toegang, routing, beveiliging) en

    - Backend-for-Frontend (BFF) (specifieke API per frontend).

Binnen het Platform Dienstverlening ligt de nadruk op asynchrone,
eventgedreven samenwerking, aangevuld met synchrone en
compositiepatronen waar nodig.

### Toegepaste patronen binnen het platform

Binnen het platform worden verschillende patronen gecombineerd:

- Event-driven: Een service registreert data en publiceert een
  notificatie; andere services reageren hierop (bijvoorbeeld het
  Verzoekenpatroon)

- Request/response interacties: Voor directe interacties tussen services
  (bijv. GZAC ↔ OpenZaak)

- Compositiepatronen (BFF / aggregatie): Voor het samenstellen van
  gegevens voor gebruikers of systemen (bijv. IKO - Integraal Klant en
  Objectbeeld).

Deze combinatie zorgt voor:

- Losse koppeling

- Schaalbaarheid

- Flexibiliteit in procesinrichting

Net als bij services zelf zijn interactiepatronen niet statisch. Het
kiezen en ontwikkelen van patronen maakt onderdeel uit van het
architecturaal continuüm, waarbij de samenwerking tussen services wordt
verbeterd op basis van praktijkervaring. De concrete toepassing van
patronen in betekenisvolle orkestratie wordt beschreven in [Toegepaste
patronen](../11-toegepaste-patronen/README.md#toegepaste-patronen).
