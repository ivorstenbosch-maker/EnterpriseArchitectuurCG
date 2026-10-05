# Relatie met Policy Based Access Control

Met de ontwikkeling van **PBAC (Policy Based Access Control)** en
**OpenFTV** (zie onderdeel **8. Identificatie, authenticatie en
autorisatie**) wordt een stap gezet in het platform naar een meer
samenhangende manier van toegang en logging.

Deze voorziening maakt het mogelijk om:

- Gegevensverwerkingen expliciet te koppelen aan beleid, doelbinding en
  autorisatie

- Toegang tot gegevens en het gebruik daarvan centraal en uniform te
  sturen en

- Deze handelingen structureel en herleidbaar vast te leggen

PBAC bepaalt of een gevraagde handeling is toegestaan op basis van
beleid en context. Het logboek van OpenFTV vormt geen zelfstandig
vervangend logboek voor dataverwerkingen, maar is een onderdeel van de
totale verantwoording.

Autorisatiebeslissingen worden als events opgenomen binnen de bredere
trace van een dataverwerking. Het Logboek Dataverwerkingen fungeert als
overkoepelend log, waarin:

- De autorisatiebeslissing (permit/deny) wordt vastgelegd als stap in de
  keten

- De feitelijke uitvoering van de verwerking wordt geregistreerd.

Logging van dataverwerking is ook vastgelegd als (kandidaat) **toegepast
patroon** in het onderdeel [Toegepaste patronen](../11-toegepaste-patronen/README.md#toegepaste-patronen).
