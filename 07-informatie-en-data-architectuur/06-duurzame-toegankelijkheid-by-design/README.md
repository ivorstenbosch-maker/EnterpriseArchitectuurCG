# Duurzame toegankelijkheid by design

In traditionele (zaak)systemen bevinden gegevens zich veelal binnen één
applicatie. In een Common Ground-architectuur zijn informatieobjecten
verdeeld over meerdere zelfstandige registraties en services. Hierdoor
verschuift de uitdaging van het archiveren van één applicatie naar het
duurzaam toegankelijk houden van een samenhangend netwerk van
informatieobjecten.

Een van de architectuurprincipes is [**Principe: Kwaliteit by
Design**](../../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-kwaliteit-by-design):

> Niet-functionele kwaliteitseisen worden vanaf het ontwerp integraal
> meegenomen in architectuur, software en dienstverlening. Aspecten
> zoals informatiebeveiliging, privacy, toegankelijkheid,
> informatiebeheer, logging, auditing en beheerbaarheid zijn geen
> afzonderlijke voorzieningen achteraf, maar vormen een integraal
> onderdeel van iedere platformvoorziening.

Dit sluit aan bij de visie op de digitale overheid, waarin de overheid
duurzaam regie moet houden op haar informatie en digitale
infrastructuur. Publieke waarden zoals transparantie, uitlegbaarheid,
toegankelijkheid en duurzame beschikbaarheid van overheidsinformatie
moeten niet afhankelijk zijn van individuele applicaties of
leveranciers, maar structureel worden geborgd in de inrichting van het
informatiestelsel.

Voor de uitwerking van duurzame toegankelijkheid sluit deze architectuur
aan bij het
[DUTO-raamwerk](https://www.nationaalarchief.nl/archiveren/kennisbank/duto-raamwerk)
van het Nationaal Archief. DUTO beschrijft geen afzonderlijke
archiefvoorziening, maar een ontwerpbenadering waarbij
informatiesystemen vanaf het ontwerp zodanig worden ingericht dat
overheidsinformatie gedurende haar gehele levenscyclus duurzaam
toegankelijk blijft. Het raamwerk onderscheidt daarbij de
kwaliteitskenmerken vindbaar, beschikbaar, leesbaar, interpreteerbaar,
betrouwbaar en toekomstbestendig en werkt deze uit in concrete
ontwerpmaatregelen voor informatiesystemen.

Dit onderdeel beperkt zich tot de architectuurimplicaties van duurzame
toegankelijkheid binnen een Common Ground-architectuur en onderscheidt
daarbij de **architectuur** en de **implementatie**.

### Duurzame toegankelijkheid vanuit de architectuur

Het DUTO-raamwerk onderscheidt vijf informatiebeheerprocessen die
gezamenlijk invulling geven aan duurzame toegankelijkheid:

- Registreren;

- Bewaren;

- Migreren;

- Vernietigen;

- Ter beschikking stellen.

Binnen het Platform Dienstverlening worden deze processen niet door één
component uitgevoerd, maar verdeeld over meerdere
architectuurbouwblokken. Daarmee sluit de architectuur aan op het
uitgangspunt dat iedere component verantwoordelijk is voor zijn eigen
gegevens en functionaliteit.

De relevante bouwblokken zijn uitgewerkt in de
[applicatiearchitectuur](../../08-applicatiearchitectuur/07-architectural-building-blocks-abb-s-en-clusters/README.md#architectural-building-blocks-abbs-en-clusters):

- **ABB Registraties** (laag 1) en **ABB Diensten** (laag 2) zijn
  verantwoordelijk voor het vastleggen, beheren en ontsluiten van
  informatieobjecten.

- De doorsnijdende **ABB Duurzame toegankelijkheid** ondersteunt de
  platformbrede informatiebeheerprocessen, zoals lifecyclebeheer,
  archivering, overbrenging en vernietiging.

  De (applicatie)architectuur van
  [registraties](../../08-applicatiearchitectuur/10-architectuur-van-registraties/README.md#architectuur-van-registraties) en
  [API’s](../../08-applicatiearchitectuur/11-architectuur-van-api-s/README.md#architectuur-van-apis) geeft invulling aan een belangrijk
  deel van de eisen voor duurzame toegankelijkheid. Registraties leggen
  informatie duurzaam vast, inclusief historie, metadata en
  gebeurtenissen, terwijl handelingsgedreven API's zorgen voor
  gecontroleerde mutaties en volledige herleidbaarheid van wijzigingen.

  Maar een gedistribueerde architectuur vraagt om aanvullende
  functionaliteit en afspraken die in deze versie van de architectuur
  verder worden uitgewerkt aan de hand van het DUTO-functiemodel.

### Implementatie & DUTO-functiemodel

De DUTO-processen worden verdiept met het
[DUTO-functiemodel](https://www.nationaalarchief.nl/archiveren/kennisbank/duto-functiemodel).
Dit geeft een handvat om te controleren in hoeverre, en op welke manier,
het Platform voldoet aan de gestelde eisen.

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 24%" />
<col style="width: 51%" />
</colgroup>
<thead>
<tr>
<th><strong>DUTO-functie</strong></th>
<th><strong>Primaire ABB</strong></th>
<th><strong>Toelichting</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>F01 Bevriezing</strong></td>
<td>ABB Registraties</td>
<td>API’s op registraties dwingen af dat gegevens volgens bedrijfsregels
worden vastgezet zodat ze niet meer kunnen worden gewijzigd. De interne
logica van Registraties dwingt af dat de registratie van data niet
aanpasbaar is, maar dat een mutatie een nieuwe registratie is.</td>
</tr>
<tr>
<td><strong>F02 Conversie</strong></td>
<td><strong>Niet ingevuld</strong></td>
<td><p>In de registraties worden informatie-objecten zo opgeslagen dat
ze op diverse wijzen kunnen worden gerepresenteerd, conform doel en
doelbinding.</p>
<p>In de periferie van het platform (zaakbruggen, koppelvlakken) worden
door leveranciers wel degelijk conversiefunctionaliteit gerealiseerd om
legacy-dataformaten om te zetten naar de standaarden (data <em>in</em>
het platform te krijgen). Maar andersom nog niet. Een usecase daarvoor
zou overbrenging naar het E-Depot kunnen zijn.</p></td>
</tr>
<tr>
<td><strong>F03 Creatie</strong></td>
<td>ABB Processervice, ABB Diensten + ABB Registraties</td>
<td>Creatie speelt over het hele platform een rol: vanaf formulieren
(bepaling van velden, validatie), tot processervices (datamodellen,
validatie, procesinrichting; Diensten(API’s) dwingen validatie en
constraints af; registraties nemen informatieobjecten duurzaam op.</td>
</tr>
<tr>
<td><strong>F04 Inwinning</strong></td>
<td>ABB Processervices</td>
<td>In de proceslaag worden gegevens opgehaald via gestandaardiseerde
API’s van externe bronnen. Ze worden daar gevalideerd; via API’s en
configuratie worden de gegevens met de juiste metadata (bron) verwerkt
in registraties.</td>
</tr>
<tr>
<td><strong>F05 Maskering</strong></td>
<td><strong>Niet ingevuld</strong></td>
<td>In het huidige platform is geen generieke maskeringsfunctionaliteit
gerealiseerd. Dat is voor verschillende doeleinden wel nodig.</td>
</tr>
<tr>
<td><strong>F06 Metagegevensbeheer</strong></td>
<td>ABB Registraties</td>
<td>Registraties beheren objectmetadata; Hiervoor worden standaarden
gevolgd</td>
</tr>
<tr>
<td><strong>F07 Opname</strong></td>
<td>ABB Registraties</td>
<td>Registraties nemen informatieobjecten duurzaam in beheer.</td>
</tr>
<tr>
<td><strong>F08 Opslag</strong></td>
<td>ABB Registraties</td>
<td>Registraties zijn verantwoordelijk voor duurzame opslag van
informatieobjecten. Hier is een vast patroon voor (URN’s)</td>
</tr>
<tr>
<td><strong>F09 Publicatie</strong></td>
<td>ABB Diensten</td>
<td>Informatie wordt beschikbaar gesteld via gestandaardiseerde
dataservices en API's.</td>
</tr>
<tr>
<td><strong>F10 Representatie</strong></td>
<td>ABB Interactieservices</td>
<td>Portalen en gebruikersinterfaces tonen informatie aan gebruikers.
Dit gaat om diverse services, conform doel(groep) en doelbinding.</td>
</tr>
<tr>
<td><strong>F11 Toegangsbeheer</strong></td>
<td>ABB Autorisatie (AuthZEN/OpenFTV)</td>
<td>Platformbrede autorisatie op basis van beleid, attributen en
context.</td>
</tr>
<tr>
<td><strong>F12 Uitwisseling</strong></td>
<td>ABB Dataservices + ABB Connectiviteit</td>
<td>Machine-to-machine-uitwisseling via API's en FSC.</td>
</tr>
<tr>
<td><strong>F13 Validatie</strong></td>
<td>Crossfunctioneel</td>
<td>Zie F03 – Creatie.</td>
</tr>
<tr>
<td><strong>F14 Verantwoording</strong></td>
<td>(o.a.) ABB Logging Dataverwerkingen, ABB Registraties</td>
<td>Verantwoording ontstaat uit de samenhang tussen registraties
(states, events en metadata), het Logboek Dataverwerkingen en de
autorisatievoorziening. Samen maken deze bouwblokken beheer en gebruik
van informatieobjecten volledig herleidbaar.</td>
</tr>
<tr>
<td><strong>F15 Vernietiging</strong></td>
<td>ABB Duurzame toegankelijkheid + ABB Registraties</td>
<td>De ABB Duurzame toegankelijkheid stelt de recordmanager in staat
regie te voeren op vernietiging; registraties voeren de feitelijke
verwijdering uit.</td>
</tr>
<tr>
<td><strong>F16 Zoeken</strong></td>
<td>ABB Dataservices + ABB Interactieservices</td>
<td>Registraties bieden zoekfunctionaliteit via API's;
interactieservices ondersteunen gebruikers bij het vinden van
informatie.</td>
</tr>
</tbody>
</table>

De mapping laat zien dat een belangrijk deel van de DUTO-functies geheel
of gedeeltelijk wordt ingevuld door de referentie-architectuur van het
Platform Dienstverlening. Registraties vormen daarbij de primaire
bouwsteen voor het duurzaam beheren van informatieobjecten, terwijl
diensten, dataservices, autorisatie, logging en connectiviteit
gezamenlijk invulling geven aan de overige functies. Duurzame
toegankelijkheid wordt daarmee niet gerealiseerd door één afzonderlijke
archiefcomponent, maar als een integrale eigenschap van het gehele
platform.

Daarbij moet worden opgemerkt dat niet alle architectuurbouwblokken
(ABB's) in de huidige referentie-implementatie zijn gerealiseerd.
Voorbeelden hiervan zijn de verdere doorontwikkeling van de
registraties, de volledige implementatie van het Logboek
Dataverwerkingen (LDV) en de realisatie van de
OpenFTV/AuthZEN-voorziening.

De volgende capabilities zijn (architectureel) nog geheel of
gedeeltelijk uit te werken:

- **Platformbrede maskeringsfunctionaliteit (F05)**  
  Het platform kent nog geen generieke capability voor het dynamisch
  maskeren of pseudonimiseren van gegevens op basis van doel, context of
  gebruikersrol.

- **Lifecyclebeheer van informatieobjecten**  
  Platformbrede ondersteuning voor lifecycle-overgangen, zoals
  archiefstatussen, overbrenging en vernietiging, vraagt verdere
  standaardisatie. Daarbij moet – waarschijnlijk – ook invulling worden
  gegeven aan de eisen uit de Archiefwet voor de overbrenging van
  blijvend te bewaren informatie naar een archiefbewaarplaats (e-depot).
  De wijze waarop deze overbrenging plaatsvindt, is niet uitgewerkt.
  Daarbij spelen onder meer vragen over de
  verantwoordelijkheidsverdeling tussen registraties en
  archiefvoorzieningen, de benodigde metadata en de vraag of
  informatieobjecten vóór overbrenging moeten worden geconverteerd, en
  welke service dat moet doen.

- **Platformbreed metagegevensbeheer**  
  Registraties beheren hun eigen metadata. Verdere uitwerking is nodig
  voor uniforme archiefmetadata, classificaties, bewaartermijnen en
  andere lifecyclemetadata conform landelijke standaarden zoals MDTO.
  Dit wordt ten dele ondervangen in de architectuur van registraties.

- **Duurzame reconstructie van dossiers**  
  Omdat informatieobjecten verspreid zijn over meerdere registraties, is
  een architectuur nodig waarmee dossiers en andere samenhangende
  informatie ook op langere termijn volledig en reproduceerbaar kunnen
  worden samengesteld.

- **Referentie-implementatie van de ABB Duurzame toegankelijkheid**  
  Binnen de huidige referentie-implementatie van het Platform
  Dienstverlening wordt de ABB Duurzame toegankelijkheid gedeeltelijk
  ingevuld door de Open Archiefbeheer Beheercomponent (OAB). Deze
  component richt zich primair op de vernietiging van informatie. OAB
  geeft slechts een eerste invulling van de ABB Duurzame
  toegankelijkheid. Verdere doorontwikkeling is noodzakelijk.

De nadruk van bovenstaande inventarisatie ligt nadrukkelijk op de
ontwikkeling van architectuurcapabilities. De *organisatorische*
inrichting van informatiebeheer, recordmanagement en archiefprocessen
valt buiten de scope van deze Enterprise Architectuur en wordt
uitgewerkt binnen de daarvoor geldende vakinhoudelijke kaders.

De concrete doorontwikkeling van services (zoals registraties, en OAB)
vindt iteratief plaats in samenwerking met de betrokken vakexperts.
Hierbij worden de architectuurprincipes uit deze Enterprise Architectuur
verfijnd en vertaald naar concrete services, API's, informatiepatronen
en implementaties.

### Openbaarheid van overheidsinformatie (Woo)

De [Wet open overheid
(Woo)](https://www.rijksoverheid.nl/themas/overheid-en-democratie/wet-open-overheid-woo/hoofdlijnen-woo)
heeft als doel de transparantie van de overheid te vergroten door
overheidsinformatie actief en passief openbaar te maken. De wet gaat uit
van het principe dat overheidsinformatie openbaar is, tenzij een
wettelijke uitzonderingsgrond van toepassing is. Daarnaast stelt de Woo
eisen aan de digitale informatiehuishouding van overheidsorganisaties,
zodat informatie vindbaar, toegankelijk en duurzaam beschikbaar is.

De (informatie)architectuur van het Platform Dienstverlening vormt een
belangrijke randvoorwaarde voor de uitvoering van de Woo. De Woo vereist
aanvullende functionaliteit, denk hierbij aan het selecteren van
openbaar te maken informatie, het toepassen van uitzonderingsgronden,
anonimisering of pseudonimisering, publicatie naar landelijke
voorzieningen en het ondersteunen van de processen rondom actieve en
passieve openbaarmaking.

Binnen de huidige referentiearchitectuur is hiervoor nog geen oplossing
aangewezen. Hoewel binnen de Common Ground-gemeenschap voorzieningen
zijn ontwikkeld, zoals
[OpenWoo](https://www.conduction.nl/solutions/openwoo/) en [de Generieke
Publicatievoorziening Woo (GPP-Woo)](https://www.gpp-woo.nl/), maken
deze op dit moment nog geen integraal onderdeel uit van het Platform
Dienstverlening en bestaat er nog geen gestandaardiseerd
integratiepatroon met de overige platformvoorzieningen. Tegelijkertijd
wordt landelijk gewerkt aan de [Generieke Woo-voorziening
(GWV)](https://www.koopoverheid.nl/voor-overheden/rijksoverheid/open-overheid)
voor de gefaseerde invoering van de actieve openbaarmakingsplicht.

De verdere uitwerking van Woo-ondersteuning valt buiten de scope van
deze versie van de Enterprise Architectuur. Wel worden de volgende
architectuurcapabilities voorzien voor toekomstige ontwikkeling:

- **Platformbrede Woo-capability**, inclusief een architectuurbouwblok
  voor actieve en passieve openbaarmaking.

- **Gestandaardiseerde koppeling tussen registraties en
  Woo-voorzieningen**, zodat informatieobjecten inclusief metadata,
  relaties en context beschikbaar kunnen worden gesteld voor
  openbaarmaking.

- **Ondersteuning van openbaarmakingsprocessen**, waaronder selectie,
  beoordeling, anonimisering, publicatie en intrekking.

- **Platformbrede maskeringsfunctionaliteit**, waarmee persoonsgegevens
  en andere beschermde informatie op basis van wet- en regelgeving,
  autorisatie en doelbinding automatisch kunnen worden afgeschermd of
  geanonimiseerd. Deze capability sluit aan op de ABB **Duurzame
  toegankelijkheid**, waarin generieke ondersteuning voor maskering als
  ontbrekende functie is geïdentificeerd.

- **Integratie met landelijke Woo-voorzieningen**, waaronder de
  Generieke Woo-voorziening (GWV) en eventuele opvolgende landelijke
  publicatievoorzieningen.

- **Samenhang met duurzame toegankelijkheid**, zodat informatie
  gedurende de gehele levenscyclus zowel archiefwaardig als
  openbaarmaakbaar blijft.
