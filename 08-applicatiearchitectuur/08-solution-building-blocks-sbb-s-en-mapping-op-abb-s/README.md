# Solution Building Blocks (SBB’s) en mapping op ABB’s

Solution Building Blocks (SBB’s) vormen de concrete implementatie in het
platform van de generieke capabilities zoals gedefinieerd in de ABB’s
(niveau 1).

Ondanks het uitgangspunt dat er geen functionele dubbelingen zijn, hoeft
de relatie tussen ABB’s en SBB’s niet 1:1 te zijn:

- Één ABB kan door één of meerdere SBB’s worden gerealiseerd
  (bijvoorbeeld bij functionele opsplitsing of specialisatie)

- Één SBB kan meerdere ABB’s realiseren (bijvoorbeeld bij
  platformcomponenten met bredere functionaliteit).

Per cluster en ABB bestaat - op moment van schrijven - de volgende
conceptuele mapping:

#### Laag 5 – Interactie

| **ABB (service die…)** | **Primaire SBB** |
|----|----|
| Gebruikersinteractie via portalen faciliteert | NL Portal |
| Self-service functionaliteit biedt voor inwoners en ondernemers | NL Portal |
| Digitale formulieren aanbiedt en verwerkt | Open Formulieren |
| Geïntegreerde klant- en objectbeelden toont | IKO |
| Procesuitvoering en werkvoorraad visualiseert voor medewerkers | GZAC (UI) |
| Functioneel beheer en configuratie ondersteunt | OpenBeheer |

#### Laag 4 – Procesinrichting

| **ABB (service die…)**             | **Primaire SBB**    |
|------------------------------------|---------------------|
| Procesflows orkestreert en bewaakt | GZAC                |
| Besluitvorming ondersteunt         | GZAC                |
| Business rules beheert en uitvoert | DMN Studio & Engine |
| Werkvoorraad en taken organiseert  | Taak & Workflow     |
| Casus- en procesregie ondersteunt  | GZAC                |

#### 

#### Laag 3 – Connectiviteit

| **ABB (service die…)**                               | **Primaire SBB** |
|------------------------------------------------------|------------------|
| Gegevensuitwisseling tussen organisaties faciliteert | OpenFSC          |
| Notificaties publiceert en distribueert              | OpenNotificaties |
| Omnichannel communicatie verzorgt                    | NotifyNL OMC     |
| Logging, auditing en tracing faciliteert             | Platform         |

#### Laag 2 – Diensten

| **ABB (service die…)**                | **Primaire SBB**      |
|---------------------------------------|-----------------------|
| Klantgegevens valideert en ontsluit   | OpenKlant API         |
| Zaakgegevens valideert en ontsluit    | OpenZaak API          |
| Productgegevens valideert en ontsluit | OpenProduct API       |
| Verzoeken beheert                     | Verzoeken (VTB)       |
| Taken beheert                         | Taken (VTB)           |
| Berichten beheert                     | Berichten (VTB)       |
| Referentiegegevens ontsluit           | Referentielijsten API |
| Generieke objecten ontsluit           | Objects API           |

#### Laag 1 – Registraties

| **ABB (service die…)**                          | **Primaire SBB**        |
|-------------------------------------------------|-------------------------|
| Personen en organisaties registreert            | OpenKlant Registratie   |
| Zaken en procescontext vastlegt                 | OpenZaak Registratie    |
| Producten en diensten registreert               | OpenProduct Registratie |
| Organisaties en medewerkers beheert             | OpenOrganisatie         |
| Domeinspecifieke gegevens beheert               | Domeinregistraties      |
| Verzoeken, taken en berichten duurzaam vastlegt | VTB-registraties        |
| Referentiegegevens beheert                      | Referentielijsten       |

#### Doorsnijdende voorzieningen

| **ABB (service die…)** | **Primaire SBB** |
|----|----|
| Duurzame toegankelijkheid en bewaartermijnen beheert | Registraties, OpenArchiefBeheer |
| Authenticatie en autorisatie verzorgt | Keycloak / Autorisatieservice |
| Monitoring en observability ondersteunt | Platformvoorzieningen |
| Privacy, security en compliance ondersteunt | Platformvoorzieningen |

De SBB’s op niveau 1 staan ook verzameld onder [BIJLAGE - Overzicht
services](#bijlage---overzicht-services). Een voorbeeldmapping:

<img
src="../../media/media/image25.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

De bovenstaande mapping maakt inzichtelijk hoe de verschillende
capabilities in de huidige situatie zijn belegd over componenten.
Daarbij valt op dat GZAC een duidelijk zwaartepunt vormt binnen het
procescluster, waar het meerdere ABB’s rondom processturing,
taakafhandeling en besluitvorming realiseert. Dit sluit aan bij het
uitgangspunt dat het onderliggende Operaton-framework modellering biedt
voor een breed scala aan usecases.

Tegelijkertijd is in de praktijk zichtbaar dat GZAC als
interactiecomponent beperkingen kent, bijvoorbeeld op het gebied van
casusregie. Dit leidt tot de ontwikkeling van aanvullende SBB’s en een
verdere specificatie van ABB’s om deze functionaliteit beter en
explicieter te beleggen.

Een vergelijkbare ontwikkeling speelt binnen de Doorsnijdende
voorzieningen, waar op het gebied van eventgedreven architectuur,
autorisatie en logging verdere doorontwikkeling op de roadmap staat.
Deze doorontwikkeling raakt niet alleen de doorsnijdende voorzieningen,
maar ook processervices en de registraties in de gegevenslaag. Deze
mapping is daarmee geen eindbeeld, maar een hulpmiddel om de
architectuur gericht door te ontwikkelen en verantwoordelijkheden verder
te verduidelijken.

#### SBB’s niveau 2

De identificatie en realisatie van SBB’s op niveau 2 (vertaling van een
BusinessService naar configureerbare elementen zoals formulieren,
BPMN-processen, business rules en gegevensmodellen) gebeurt op basis van
businessbehoefte. Zie ook [Samenwerking en uitwisseling
bouwstenen](../../15-bijlagen/03-bijlage-businessservices/README.md#samenwerking-en-uitwisseling-bouwstenen).
