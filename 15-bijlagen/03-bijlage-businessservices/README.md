# BIJLAGE - BusinessServices

De ‘BusinessService’ is een belangrijk concept in architectuur van het
Platform. ‘BusinessService’ is een begrip dat contextgevoelig is en
daardoor in architectuurdiscussies regelmatig langs elkaar heen wordt
gebruikt. (zie onderaan voor ambiguïteit).

In het Platform Dienstverlening is een BusinessService een logisch
geheel dat businessobjecten en -regels encapsuleert in herbruikbare
functionaliteit. Het wordt hier met twee hoofdletters geschreven om het
te onderscheiden van andere concepten.

<img
src="../../media/media/image39.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, schermopname, nummer, Lettertype Door AI gegenereerde inhoud is mogelijk onjuist." />

### BusinessService: een generiek concept

Het Platform Dienstverlening is een (micro)servicearchitectuur en een
BusinessService is **een logisch geheel dat businessobjecten en -regels
encapsuleert met een vastgestelde in - en output en herbruikbare
functionaliteit.**

De service is een *logisch* geheel, maar bestaat binnen het platform
*fysiek* uit verschillende services:

#### BusinessService in het vijflaagsmodel van Common Ground

| **Common Ground-laag** | **Rol van de laag** | **BusinessService (SOA/IT-definitie)** |
|----|----|----|
| **5. Interactie-laag** | Afhandeling van gebruikers- of kanaalinteractie | De BusinessService manifesteert zich hier als één samenhangende functionaliteit voor het kanaal (bijv. “aanvraag indienen”), of het proces (bijv. ‘vastleggen Inkomen) |
| **4. Proces-laag** | Orkestratie van stappen en volgorde | De BusinessService bestaat hier uit BPMN-fragmenten per processtap, die samen het end-to-end gedrag vormen maar zelfstandig uitvoerbaar zijn. |
| De BusinessServices worden aangestuurd door DMN-modellen\* die valideren en orkestreren op basis van beslis- en procesregels. |  |  |
| **3. Integratie-laag** | Uitwisseling data |  |
| **2. Toegang tot data** | Technische ontsluiting en validatie | De BusinessService interacteert met specifieke **API-calls,** verantwoordelijk voor extra validatie, verwerking en het wegschrijven van data. |
| **1. Data / Registratie-laag** | Duurzame vastlegging van gegevens | De BusinessService heeft geen eigen database maar gebruikt een registratie waarin de door de service beheerde gegevens consistent, leidend en deelbaar worden vastgelegd. |

<img
src="../../media/media/image40.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, lijn, ontvangst, nummer Door AI gegenereerde inhoud is mogelijk onjuist." />

> \* Voorbeeld DMN-tabel: op basis van het type proces, de huidige fase,
> en nieuwe gebeurtenissen en de inhoud van die gebeurtenissen wordt een
> logische vervolgstap bepaald en gestart.

### BusinessService: voorbeeld

**Laag 5**

Een BusinessService ‘vaststellen’ persoon bestaat op de interactie-laag
uit een formulier voor de behandelaar dat met de volgende
functionaliteit:

- Het formulier toont de persoonsgegevens uit de aanvraag (BSN, naam,
  geboortedatum).

- Daarnaast worden de bijbehorende persoonsgegevens uit de BRP getoond,
  indien beschikbaar.

- De gebruiker beoordeelt of de BRP-gegevens overeenkomen met de
  aanvraag.

- Als BRP-gegevens beschikbaar zijn, moet de gebruiker kiezen of deze
  wel of niet gebruikt mogen worden.

- Bij de keuze *nee* moet een ander (gewenst) BSN worden ingevoerd.

- Als BRP-gegevens niet beschikbaar zijn, wordt direct gevraagd om een
  BSN in te voeren.

- De gebruiker moet een toelichting geven op de gemaakte keuze.

- Het formulier kan pas worden ingediend wanneer alle verplichte keuzes
  en invoer zijn gedaan.

**Laag 4**

Op laag 2 vindt het proces plaats waarin bovenstaande (het formulier)
één gebruikerstaak is.

- Het proces start met het ophalen van relevante invoer uit de aanvraag
  en eerdere vastleggingen (persoon, BRP-keuze, toelichting).

- Deze gegevens worden voorbereid en samengebracht als input voor
  vaststelling.

- Vervolgens wordt een subproces “vaststelling persoon” aangeroepen
  waarin de beoordeling plaatsvindt (zie bovenstaand formulier)

- In dit subproces wordt vastgelegd of de persoon is vastgesteld, met
  datum, toelichting en gebruikte BRP-gegevens.

- Het proces onderscheidt expliciet handmatige beoordeling van
  automatische vaststelling.

- Na afronding worden de resultaten weggeschreven:

  - Vastgestelde persoonsgegevens,

  - Aanvullende vastleggingsvelden,

  - En brondata uit de brp.

- De vastlegging gebeurt op vaste locaties voor de gegevens

- Het proces eindigt wanneer de persoon van de aanvrager definitief is
  vastgesteld.

#### Laag 2

Op laag 2 wordt de data consistent vastgelegd met gebruik van een
API-call, die er als volgt uit kan zien:

{

"identificatie": "string",

"bronorganisatie": "string",

"omschrijving": "Vaststelling persoon aanvrager",

"toelichting": "Motivatie van de consulent bij het vaststellen van de
persoon",

"vaststellingstype": "persoon",

"registratiedatum": "2019-08-24",

"datumVastgesteld": "2019-08-24T14:15:22Z",

"handmatigVastgesteld": true,

"vastgesteldePersoon": {

"bsn": "string",

"voornamen": "string",

"voorletters": "string",

"voorvoegsel": "string",

"achternaam": "string",

"geboortedatum": "2019-08-24"

},

"brongegevensPersoon": {

"bron": "BRP",

"bsn": "string",

"voornamen": "string",

"voorletters": "string",

"voorvoegsel": "string",

"achternaam": "string",

"geboortedatum": "string",

"onvolledigeGeboortedatum": true

},

"beoordeling": {

"brpGegevensGebruikt": true,

"toelichtingConsulent": "Korte onderbouwing van de gemaakte keuze"

},

"herkomst": {

"proces": "BSB-211 Vaststelling persoon",

"taak": "Vaststellen persoon aanvrager"

},

"archivering": {

"archiefstatus": "nog_te_archiveren",

"archiefactiedatum": "2019-08-24",

"archiefnominatie": "blijvend_bewaren"

}

}

#### 

#### Laag 1

Op laag 1 worden de door de service beheerde gegevens consistent,
leidend en deelbaar vastgelegd. Op het niveau van businessobjecten zijn
registraties beschikbaar (’Common Ground-registraties’) voor Zaken,
Producten, Klanten.

Voor specifieke (domeingebonden gegevens) zoals bijvoorbeeld Burgerzaken
of processen in het Sociaal Domein worden Domeinregistraties gebruikt.

**Granulariteit van BusinessServices**

Hoe groot of klein een BusinessService moet zijn, wordt bepaald door een
samenhang van functionele en inhoudelijke overwegingen. Daarbij zijn met
name de volgende factoren leidend:

- **Herbruikbaarheid van de service.** Een BusinessService moet logisch
  herbruikbaar zijn over meerdere processen en contexten. In het
  voorbeeld is de service *vaststellen persoon* generiek toepasbaar,
  omdat deze functionaliteit in veel processen terugkomt. Wanneer aan
  deze service ook proces- of domeinspecifieke functionaliteit wordt
  toegevoegd — zoals het toekennen van een paspoort — neemt de
  herbruikbaarheid af. Dergelijke functionaliteit hoort daarom thuis in
  een aparte BusinessService die een ander businessdoel dient.

- **Herhaalbaarheid van de service.** Een BusinessService moet meerdere
  keren op dezelfde wijze kunnen worden uitgevoerd, met vergelijkbare
  invoer en uitkomsten. Als een handeling slechts éénmalig of sterk
  contextafhankelijk is, is deze minder geschikt als zelfstandige
  BusinessService.

- **Niveau en scope van datavalidatie.** De benodigde mate van validatie
  en consistentiebewaking bepaalt mede de omvang van de BusinessService.
  Als een bedrijfsobject groot is en de vereiste consistentie zich
  uitstrekt over alle attributen (bijvoorbeeld identiteit, naam en
  geboortedatum in samenhang), is het logisch om deze validatie binnen
  één BusinessService te concentreren. Hierdoor kan de service als
  consistente eenheid optreden richting afnemers.

- **Cohesie van het businessconcept.** Een BusinessService moet één
  duidelijk businessconcept vertegenwoordigen.

### Blauwdruk gebruik van BusinessServices

Bovenstaand voorbeeld komt uit het proces Aanvraag Leefonderhoud. Dit
proces leent zich goed voor standaardisatie in de vorm van
BusinessServices omdat er een breedgedragen ontologie is geformuleerd
(<https://github.com/VNG-Realisatie/Ontologie-Inkomen/>).

Op basis van wat er ‘bestaat’ in het domein (concepten, relaties,
handelingen) worden BusinessServices geïdentificeerd. Een
**informatiemodel**, waarbij de Ontologie Inkomen een heel gedetailleerd
en gereviseerd voorbeeld betreft, is voorwaardelijk.

#### BusinessService - Ambiguïteit.

| **Context** |  | **Betekenis** | **Definitie** |
|----|----|----|----|
| **Businessarchitectuur** |  | Waarde voor een externe afnemer | Een *businessservice* is een door de organisatie geleverde, extern waarneembare dienst die een specifieke behoefte van een afnemer vervult, onafhankelijk van interne processen en technologie. |
| **ArchiMate (business layer)** |  | Formeel gedefinieerd architectuurconcept | Een *businessservice* is een service die vanuit de businesslaag wordt aangeboden aan een business actor of role, en die wordt gerealiseerd door businessprocessen en/of businessfuncties. |
| **SOA / IT-architectuur (informeel gebruik)** |  | IT-service met businesssemantiek | Een *BusinessService* is een applicatieservice die businessobjecten en -regels encapsuleert en herbruikbare functionaliteit biedt aan andere applicaties of kanalen. - in platformcontext: **een logisch geheel dat businessobjecten en -regels encapsuleert met een vastgestelde in - en output en herbruikbare functionaliteit.** |
| **Capability-gebaseerde architectuur** |  | Concretisering van een capability | Een *businessservice* is een afgebakende levering van waarde die laat zien hoe een capability extern of intern wordt benut door de organisatie. |
| **Product-georiënteerde organisaties** |  | Markt- of productdienst | Een *businessservice* is een door een team of product aangeboden dienst met een duidelijke scope, eigenaar en prestatieafspraken, gericht op continue waardecreatie voor gebruikers of klanten. |
| **Operating-model / service-management** |  | Organisatorische dienst | Een *businessservice* is een stabiel gedefinieerde organisatorische dienst waarvoor afspraken bestaan over kwaliteit, kosten en beschikbaarheid, vaak vastgelegd in SLA’s. |

### Samenwerking en uitwisseling bouwstenen

<https://samendelen.opengem.nl/> - Samen Delen is de plek waar de
inrichting van applicaties gedeeld kan worden met elkaar. Als een
applicatie een exportfunctie heeft, kunnen deze exports hier worden
geüpload. Anderen kunnen deze exports weer downloaden en importeren in
hun applicatie.

Voor **GZAC** is een Exchange.gzac.nl beschikbaar, met daarop:

[App](https://exchange.gzac.nl/)

- **Process Blue Prints** – Startklare basisprocessen; altijd lokaal te
  configureren en soms uit te breiden met maatwerk (bijv. een plugin).

- **Building Blocks** – Herbruikbare onderdelen zoals formulieren,
  zaakdefinities en subprocessen.

- **Plugins** – Uitbreidingen voor extra functionaliteit, vaak voor
  generieke koppelingen met andere systemen.
