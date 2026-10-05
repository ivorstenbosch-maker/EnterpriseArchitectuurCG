# Doelarchitectuur logging

De doelarchitectuur ziet er als volgt uit:

<img
src="../../media/media/image29.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

De doelarchitectuur logging is (o.a.) gebaseerd op het Logboek
dataverwerkingen. De doelarchitectuur maakt onderscheid tussen de
verschillende lagen van het Platform Dienstverlening. Per laag ligt de
verantwoordelijkheid voor logging anders. Het uitgangspunt is dat iedere
service voldoende informatie levert om een verwerking **ketenbreed te
kunnen herleiden**, terwijl centrale voorzieningen zorgen voor het
verzamelen, koppelen, bewaren en ontsluiten van de logging.

#### Laag 4/5 – Procesinrichting & interactie

**Voorbeelden:** GZAC, NL-Portal.

Deze laag is belangrijk omdat hier bedrijfsprocessen worden uitgevoerd
en gegevens worden verwerkt in de context van een proces of zaak.

Een service op deze laag moet:

- Iedere relevante gegevensverwerking als event kunnen vastleggen;

- De **trace_id** uit de keten behouden;

- Actor, doelbinding en verwerkingsactiviteit vastleggen;

- Vastleggen welke handeling is uitgevoerd en op welke
  gegevens/resource;

- Interne verwerkingen loggen wanneer gegevens in een eigen database,
  cache of andere opslag worden verwerkt;

- De logging beschikbaar maken voor het centrale Logboek
  Dataverwerkingen.

Voor deze services geldt dat logging niet automatisch ontstaat doordat
een onderliggende registratie wordt gelogd. Een processervice die zelf
gegevens verwerkt, heeft ook een eigen loggingverantwoordelijkheid.
Iedere service op laag 4/5 logt hiervoor iedere relevante actie via
OpenTelemetry (OTel), buffert de logging lokaal en streamt deze naar de
infrastructuur.

Het LDV kent hiervoor, bovenstaand beschreven, drie mogelijke niveaus:

1.  **Registerverwijzing** – aantonen dát een bepaalde verwerking heeft
    plaatsgevonden.

2.  **Kolomverwijzing** – aantonen welke gegevenscategorieën zijn
    gebruikt.

3.  **Concrete data** – kunnen reconstrueren welke concrete waarden zijn
    verwerkt.

Het noodzakelijke niveau wordt per proces bepaald.

#### Laag 3 – Connectiviteit

Op deze laag wordt vooral **de verbinding en toegang** gelogd:

- Welke service communiceert met welke andere service;

- Wanneer de communicatie plaatsvindt;

- Via welk kanaal of welke gateway;

- Welke autorisatie-/toegangsbeslissing heeft plaatsgevonden;

- De technische trace-context.

De logging op deze laag ondersteunt daarmee de ketenbrede
herleidbaarheid.

Belangrijk is dat deze logging niet moet worden verward met logging van
de wettelijke dataverwerking. FSC legt verbinding en toegang vast; het
LDV legt de daadwerkelijke dataverwerking vast.

Op deze laag wordt ook een centrale loggingpipeline ingericht voor

- De verwerking van de logs uit laag 4/5

- Het creëren van logs die naar de registraties (laag 1/2) gaan.

Deze inrichting is inclusief **l**ogcollectie, processing, labeling,
routering naar de juiste storage en retrymechanismen. De service (laag
4/5) blijft verantwoordelijk voor het correct produceren van de
logregels en het behouden van de ketenbrede trace-context.

De logging hoeft daarbij niet noodzakelijk alle gegevenswaarden zelf te
bevatten. Het doel is primair om vast te kunnen stellen welke
gegevensverwerking heeft plaatsgevonden en, afhankelijk van het vereiste
niveau, welke gegevenscategorieën of concrete gegevens daarbij zijn
gebruikt.
