# BIJLAGE - Overzicht services

Overzicht van services en link naar documentatie binnen Platform
Dienstverlening.

**Laag 1/2 – Registraties & API-laag (Data & Services)**

**OpenZaak**

Moderne open-source implementatie van de ZGW-API’s voor zaak- en
documentbeheer.

<https://github.com/open-zaak/open-zaak>

**OpenKlant**

Registratiecomponent voor opslag en ontsluiting van klantgegevens
volgens de Klantinteracties-API-specificaties.

<https://github.com/maykin../../media/open-klant>

**OpenOrganisatie**

Component voor beheer van medewerkers, teams en organisaties met
API-toegang en o.a. SCIM-integratie.

<https://github.com/maykin../../media/open-organisatie>

**OpenProduct**

Centrale API voor producttypen en producten, bedoeld voor hergebruik in
andere applicaties.

<https://github.com/maykin../../media/open-product>

**Registraties VTB (Verzoeken, taken berichten)**

Componenten voor (resp.) Verzoeken, Taken en Berichten als
gestandaardiseerde informatie-objecten, voor communicatie- en
interactiepatronen over het platform.

[maykin../../media/open-vtb: Open Verzoeken, Taken en
Berichten](https://github.com/maykin../../media/open-vtb)

**Objects API**

API en beheerinterface voor het registreren en beheren van generieke
objecten binnen Common Ground.

<https://github.com/maykin../../media/objects-api>

**Objecttypes API**

API voor het definiëren en beheren van objecttypen die gebruikt worden
door Objects API-implementaties.

<https://github.com/maykin../../media/objecttypes-api>

**Referentielijsten API**

API voor generieke en herbruikbare referentielijsten binnen het Common
Ground-landschap.

<https://github.com/maykin../../media/referentielijsten>

**OpenNotificaties**

API voor het routeren en publiceren van notificaties tussen applicaties
binnen een Common Ground-architectuur.

<https://github.com/open-zaak/open-notificaties>

**OpenArchiefbeheer**

Component voor recordmanagement en vernietigingslijsten conform
archiefwet- en ZGW-principes.

<https://github.com/maykin../../media/open-archiefbeheer>

**Open API Framework**

Gedeeld framework met basisfunctionaliteit en configuratie voor meerdere
Open-componenten.

<https://github.com/maykin../../media/open-api-framework>

**Laag 4/5 – Interactie & Toepassingen (Portalen & UI)**

**GZAC**

Zaakafhandelcomponent gericht op proces- en taakondersteuning bovenop
ZGW-API’s.

<https://github.com/generiekzaakafhandelcomponent>

Het onderliggende framework (Operaton) wordt tevens ingezet voor de
uitvoering van beslislogica via DMN. Op basis van de DMN-engine(s) wordt
regelbeheer voor verschillende services centraal uitgevoerd en afgedekt
via configuratie, zonder dat hiervoor maatwerk per proces nodig is.

**ZAC**

Zaakafhandelcomponent gericht op proces- en taakondersteuning bovenop
ZGW-API’s.

<https://github.com/infonl/dimpact-zaakafhandelcomponent>

**DMN Studio**

Beheercomponent voor inrichting van beslisregels in Operaton
DMN-instances.

<https://github.com/SynTouchNL/dmn-studio-backend>

**NL Portal**

Portaaloplossing voor inwoner- en medewerkersinteractie binnen een
Common Ground-architectuur.

<https://github.com/nl-portal>

**OpenInwonerPortaal**

Gemeentelijk platform voor producten en diensten met integraties naar
Common Ground-componenten.

<https://github.com/maykin../../media/open-inwoner>

**IKO – Integraal Klant- en Objectbeeld**

Integreert klant- en objectgegevens tot één overzicht voor
case-medewerkers

*Doc pagina (functieomschrijving):*
<https://docs.valtimo.nl/features/iko>

**Open Formulieren**

Faciliteert het modelleren, aanbieden en verwerken van digitale
formulieren voor inwoners en organisaties. Het component verzorgt de
gestructureerde uitvraag van gegevens, valideert invoer en legt
inzendingen vast via gestandaardiseerde API’s.

<https://github.com/open-formulieren/open-forms/>

**OpenBeheer**

Biedt een centrale beheerinterface voor het beheren van gegevens uit
meerdere registraties binnen samenhangende processen, zonder dat deze
registraties zelf worden aangepast.

<https://github.com/maykin../../media/open-beheer>

**Faciliterende voorzieningen**

Aanvullend op de bovenstaande kerncomponenten bevat het platform een
aantal ondersteunende voorzieningen die noodzakelijk zijn voor de
volledige inrichting van de dienstverlening:

- **Toegang en beveiliging**: authenticatie- en autorisatievoorzieningen
  (o.a. DigiD, eHerkenning, eIDAS, machtigingen, Keycloak/OpenID
  Connect, met (optionele) koppeling met Azure AD)

- **Communicatie en output**: integratie met e-mailafhandeling (SMTP
  relay, mailbox/outbox), documentgeneratie (templates, PDF) en
  printvoorzieningen

- **Gegevensontsluiting en externe bronnen**: koppelingen met landelijke
  registraties en externe databronnen (zoals BRP, BAG, KvK, Kadaster via
  HaalCentraal)

- **Monitoring en logging**: centrale voorzieningen voor observability
  (o.a. Grafana, Loki) ten behoeve van beheer, auditing en
  betrouwbaarheid (onderdeel van Haven+).

Deze voorzieningen zijn integraal onderdeel van het platform, maar
worden ingezet als generieke capabilities die door meerdere services en
processen worden gebruikt.
