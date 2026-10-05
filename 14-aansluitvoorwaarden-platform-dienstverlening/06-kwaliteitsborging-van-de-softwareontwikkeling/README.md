# Kwaliteitsborging van de softwareontwikkeling

Dit onderdeel beschrijft de eisen die worden gesteld aan het
ontwikkelproces van platformservices. Deze hebben onder meer betrekking
op softwarekwaliteit, documentatie, testautomatisering, en gebruik van
AI. Niet alleen het eindproduct moet van hoge kwaliteit zijn, ook het
ontwikkelproces moet transparant, overdraagbaar en reproduceerbaar zijn.

De algemene eisen ten aanzien van softwareontwikkeling, kwaliteit,
beveiliging, documentatie, testen, acceptatie en onderhoud zijn
opgenomen in de
[GIBIT](https://vng.nl/sites/default/files/2026-03/gibit-2025-artikelen.pdf).
De onderstaande bepalingen vormen daarop een aanvulling en gelden
specifiek voor software die onderdeel uitmaakt van het Platform
Dienstverlening.

#### Principes

- **Leverancier is verantwoordelijk.** De leverancier is
  eindverantwoordelijk voor de kwaliteit van de opgeleverde software,
  ongeacht de inzet van AI.

- **Menselijke beoordeling is verplicht.** Alle opgeleverde software
  wordt beoordeeld door voldoende gekwalificeerde ontwikkelaars.
  AI-output wordt nooit zonder review geaccepteerd.

- **Kwaliteit boven metrics.** Kwaliteit wordt vastgesteld op basis van
  onderhoudbaarheid, beveiliging, architectuur, testbaarheid en naleving
  van afspraken. Geautomatiseerde analyses ondersteunen dit, maar
  vervangen geen inhoudelijke review.

- **Passende technologie.** De gekozen programmeertaal, frameworks en
  architectuur moeten aantoonbaar passend zijn voor de functionele en
  niet-functionele eisen van de oplossing.

- **Onderhoudbaarheid staat centraal.** Software moet begrijpelijk,
  overdraagbaar en duurzaam onderhoudbaar zijn gedurende de gehele
  levenscyclus.

#### Verplichtingen voor de leverancier

Onverminderd de verplichtingen uit de GIBIT toont de leverancier
aanvullend aan dat:

- De opgeleverde software aantoonbaar is gereviewd door ervaren
  ontwikkelaars; dit kan onderbouwd worden met gedocumenteerde Pull
  Requests gereviewed door ervaren ontwikkelaars;

- De gekozen architectuur, programmeertaal en gebruikte technologie
  passend zijn voor de oplossing;

- Beveiliging, testbaarheid en onderhoudbaarheid onderdeel zijn van het
  ontwikkelproces;

- Eventuele inzet van AI niet afdoet aan de kwaliteit of
  verantwoordelijkheid voor het eindproduct;

- De software zodanig is gedocumenteerd dat beheer en doorontwikkeling
  door een opvolgende partij mogelijk zijn;

- Het is verplicht om AI-gebruik aan te geven; in dat geval wordt
  vastgelegd:

  - Welke AI-middelen zijn gebruikt en waarvoor;

  - Op welke onderdelen AI een wezenlijke bijdrage heeft geleverd;

  - Welke menselijke reviews en controles zijn uitgevoerd, bij
    realisatie van functionaliteit, en routine-/procesmatige checks;

  - Indien gebruik is gemaakt van agentic AI of vergelijkbare autonome
    ontwikkelprocessen: de gebruikte prompts, instructies, guardrails,
    beslisregels en werkwijze, voor zover deze noodzakelijk zijn om de
    software te begrijpen, reproduceren en onderhouden. Deze informatie
    maakt onderdeel uit van de architectuur- en projectdocumentatie en
    wordt samen met de broncode in de repository opgeleverd.

#### Toelatingsvoorwaarde/Borging van compliance

Het voldoen aan deze richtlijn is een voorwaarde voor ingebruikname van
software door gemeenten en voor opname van software in het Platform
Dienstverlening. De leverancier toont voorafgaand aan oplevering aan dat
aan de gestelde eisen is voldaan en levert de hiervoor benodigde
documentatie, reviewresultaten en architectuurartefacten aan.

#### Richtlijn toetsing

De toetsing richt zich niet uitsluitend op de kwaliteit van de broncode,
maar ook op de professionaliteit en beheersbaarheid van het
softwareontwikkelproces. Binnen de governance van het Platformmanagement
is een toetsingscommissie ingericht; deze organiseert deze beoordeling
samen met leveranciers, softwarespecialisten en architecten.

Bij de beoordeling wordt vastgesteld of de leverancier kan aantonen dat:

- Architectuur- en technologiekeuzes navolgbaar zijn onderbouwd;

- Softwareontwikkeling plaatsvindt volgens aantoonbare kwaliteits- en
  reviewprocessen;

- Beheer, doorontwikkeling en overdracht aan een andere partij voldoende
  zijn geborgd;

- Documentatie, deployment-instructies en architectuurartefacten actueel
  beschikbaar zijn;

- De inzet van AI, indien van toepassing, transparant is vastgelegd en
  onder menselijke verantwoordelijkheid plaatsvindt.

De toetsing kan worden ondersteund door steekproeven op pull requests,
architectuurreviews, reproduceerbaarheidstesten, kwaliteitsrapportages
en securityscans. Hierbij staat centraal of de leverancier aantoonbaar
werkt volgens professioneel software-engineering- en beheerproces, en
niet uitsluitend of het eindproduct functioneel voldoet.

Geautomatiseerde kwaliteitsmetingen en securityscans kunnen hierbij
worden gebruikt als ondersteunend bewijs, aangevuld met een inhoudelijke
beoordeling door architecten en/of senior softwareontwikkelaars,
bijvoorbeeld van andere softwarepartners. Bij onvoldoende onderbouwing
of kwaliteit kan de software niet worden geaccepteerd of opgenomen
totdat de geconstateerde tekortkomingen zijn hersteld.
