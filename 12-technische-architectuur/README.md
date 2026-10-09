# 12. Technische architectuur

De technische architectuur (ook wel aangeduid als **Laag 0**) vormt de
onderliggende laag van het Platform Dienstverlening . Deze laag voorziet
in de infrastructuur en generieke technische voorzieningen waarop alle
hogere lagen – van dataservices tot procesapplicaties – draaien.

De principes van data-autonomie, open standaarden en Open Source, werken
ook door in deze laag. Dit betekent dat de technische architectuur
gericht is op:

- Het voorkomen van afhankelijkheid van specifieke leveranciers

- Het borgen van verplaatsbaarheid van applicaties en data

- En het realiseren van een reproduceerbare en gestandaardiseerde
  infrastructuur.

Binnen Common Ground zijn hiervoor twee samenhangende standaarden
ontwikkeld: **Haven** en **Haven+**.

## Haven

De Haven-standaard beschrijft hoe een uniforme en overdraagbare
hostingomgeving voor applicaties wordt ingericht. Centraal staat het
gebruik van Kubernetes als generieke uitvoeringslaag, waarmee
applicaties containerized en platformonafhankelijk kunnen worden
uitgerold.

Haven definieert onder andere:

- De inrichting van een Kubernetes-omgeving

- De minimale set aan basisvoorzieningen voor deployment

- Richtlijnen om vendor lock-in te voorkomen door gebruik van open
  standaarden.

Haven vormt daarmee de technische basis waarop applicaties consistent
kunnen draaien, ongeacht de onderliggende infrastructuur of
cloudprovider.

## Haven+

Haven+ bouwt voort op deze basis en levert een voorgeconfigureerde
platformlaag met generieke voorzieningen die nodig zijn in een
productieomgeving. Waar Haven beschrijft *waar* en *hoe* applicaties
draaien, voorziet Haven+ in de vraag *wat er nodig is om ze operationeel
te beheren*.

Haven+ omvat onder andere:

- Voorzieningen voor monitoring, logging en tracing

- Identity- en toegangsvoorzieningen

- Datadiensten zoals databasebeheer

- Certificaat- en secretmanagement.

Deze voorzieningen worden gestandaardiseerd en als samenhangend geheel
aangeboden, zodat ontwikkelteams zich kunnen richten op functionaliteit
in plaats van op het opbouwen en beheren van infrastructuur.

## Positionering in de architectuur

Haven en Haven+ vormen samen de technische fundering onder het Platform
Dienstverlening. Zij leveren generieke capabilities die door alle
services worden gebruikt, maar bevatten zelf geen businesslogica of
domeinspecifieke functionaliteit.

De technische architectuur:

- Faciliteert de uitvoering van services

- Borgt randvoorwaarden zoals beveiliging, beschikbaarheid en
  observability en

- Maakt het mogelijk om applicaties en data onafhankelijk van specifieke
  leveranciers te beheren en te verplaatsen.

Daarmee is deze laag een essentiële voorwaarde voor het realiseren van
de bredere architectuurprincipes van Common Ground, zonder deze
inhoudelijk in te vullen.

#### Nadere uitwerking

De technische architectuur wordt in dit document op hoofdlijnen
beschreven. Voor de concrete inrichting, componenten en implementatie
wordt verwezen naar de documentatie Haven+.

Documentatie: <https://havenplus.commonground.nl/docs/overview>
