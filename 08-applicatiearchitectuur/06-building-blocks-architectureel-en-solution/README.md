# Building blocks (architectureel en solution)

Binnen (enterprise) architectuur wordt onderscheid gemaakt tussen
**Architectural Building Blocks (ABB’s)** en **Solution Building Blocks
(SBB’s)**. Dit is een generiek architectuurprincipe dat ook binnen het
Platform Dienstverlening wordt toegepast.

Een **Architectural Building Block (ABB)** beschrijft een generieke of
abstracte specificatie van functionaliteit. ABB’s definiëren de
benodigde capabilities in termen van business-, informatie-, applicatie-
en technologie-architectuur. Binnen dit kader wordt functionaliteit
primair uitgedrukt als een **BusinessService**: een logisch afgebakende
dienst die waarde levert aan de business, onafhankelijk van de
onderliggende implementatie.

De concrete invulling van deze BusinessServices vindt plaats in
**Solution Building Blocks (SBB’s)**. Dit zijn de gerealiseerde
componenten binnen het platform, bestaande uit softwarecomponenten en/of
configuraties die gezamenlijk de BusinessService implementeren.

ABB’s worden binnen het platform op twee niveaus toegepast:

1.  **Op het niveau van softwarecomponenten (services)**

- ABB’s beschrijven hier de BusinessService en de bijbehorende
  functionele en architectonische eisen.

- SBB’s zijn de concrete implementaties hiervan in de vorm van services
  (bijv. registraties, proces- of integratieservices).

2.  **Op het niveau van configuratie binnen componenten**

- ABB’s beschrijven hier de functionele invulling van een
  BusinessService binnen een component.

- SBB’s zijn de concrete configuraties, zoals:

  - Formulieren

  - BPMN-processen

  - Business rules

  - Gegevensmodellen.

Deze configuraties vormen geen zelfstandige softwarecomponenten, maar
zijn een invulling van functionaliteit binnen bestaande services.

Door dit onderscheid ontstaat een heldere scheiding tussen:

- BusinessServices (wat wordt geleverd)

- Softwarecomponenten (waar dit wordt uitgevoerd)

- Configuratie (hoe dit concreet wordt ingericht binnen componenten)

Hiermee wordt geborgd dat:

- Architectuurprincipes consistent worden toegepast

- Functionaliteit herbruikbaar en vervangbaar blijft

- Implementaties flexibel kunnen evolueren.

ABB’s en SBB’s vormen daarmee de schakel tussen architectuur
(richtinggevend) en realisatie (concreet en configureerbaar).

<img
src="../../media/media/image24.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

### Voorbeeld – Aanvragen van een uitkering

De BusinessService **"Beoordelen uitkeringsaanvraag"** is een
**Architectural Building Block (ABB)**. Deze beschrijft wat de
dienstverlening moet leveren: beoordelen van een aanvraag, vastleggen
van gegevens, toepassen van beslisregels en informeren van de inwoner.

De concrete invulling bestaat uit **Solution Building Blocks (SBB's)**:

- **Niveau 1: Softwarecomponenten:** GZAC, OpenZaak, OpenKlant, DMN
  Engine en Open Formulieren.

- **Niveau 2: Configuratie:** het aanvraagformulier, het BPMN-proces, de
  DMN-beslisregels, zaaktype, producttype en validatieregels.

Hierdoor blijft de BusinessService hetzelfde, terwijl de
softwarecomponenten of configuratie in de tijd kunnen veranderen zonder
de architectuur aan te passen.
