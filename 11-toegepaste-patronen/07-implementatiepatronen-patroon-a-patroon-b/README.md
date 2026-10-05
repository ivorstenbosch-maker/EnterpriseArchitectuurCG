# Implementatiepatronen (Patroon A, Patroon B)

De voorgaande paragrafen beschrijven patronen voor de samenwerking
tussen services binnen het Platform Dienstverlening. In de praktijk
bevindt elke gemeente zich reeds in een uitgangssituatie. Bestaande
applicaties, contracten en investeringen maken dat de doelarchitectuur
niet altijd in één stap kan worden gerealiseerd.

Om gemeenten hierin te ondersteunen onderscheidt het Platform
Dienstverlening twee referentie-implementatiepatronen. Beide patronen
streven dezelfde architectuurprincipes na en leiden uiteindelijk naar
dezelfde doelarchitectuur. Het verschil zit in dat bestaande software
wordt ingepast tijdens de transitie.

| **Patroon** | **Beschrijving** | **Voorbeeld** |
|----|----|----|
| **Patroon A – Volledig Platform Dienstverlening** | Alle lagen van het vijflagenmodel worden gerealiseerd met componenten conform de Common Ground-architectuur. | Een klachtenproces wordt volledig opgebouwd uit formulieren, procescomponenten, FSC, registraties, dataservices en omnichannelvoorzieningen. |
| **Patroon B – Hybride implementatie** | De gegevenslaag en connectiviteitslaag volgen de Common Ground-architectuur; de proceslaag wordt (tijdelijk) ingevuld door een bestaande SaaS- of legacy-oplossing. | De aanvraag van een paspoort wordt afgehandeld in een bestaande zaaksysteemcomponent, terwijl gegevens, formulieren, API's en communicatie via het Platform Dienstverlening verlopen. |

#### Duiding

Beide implementatiepatronen ondersteunen dezelfde doelarchitectuur, maar
verschillen in de wijze waarop deze wordt bereikt.

- **Patroon A** realiseert de architectuur volledig volgens de
  uitgangspunten van Common Ground. Dit biedt maximale flexibiliteit,
  herbruikbaarheid en loskoppeling, maar vraagt ook de grootste
  organisatorische en technische verandering.

- **Patroon B** biedt een pragmatische transitiestrategie waarbij
  bestaande applicaties voorlopig behouden blijven, terwijl gegevens,
  interactie en integratie al worden georganiseerd volgens de
  architectuur van het Platform Dienstverlening. Hierdoor kan
  stapsgewijs worden toegewerkt naar Patroon A.

### Patroon A – Volledige platformimplementatie

Binnen Patroon A worden processen volledig gerealiseerd met de
componenten van het Platform Dienstverlening. Zowel de interactie,
procesafhandeling, connectiviteit als gegevensvoorziening volgen de
architectuurprincipes uit dit document.

De implementatie bestaat doorgaans uit:

- Realiseren van de benodigde BusinessServices en procescomponenten.

- Inrichten van registraties, API's en gegevensmodellen.

- Migreren van gegevens uit bestaande systemen.

- Implementeren van de nieuwe werkwijze binnen de organisatie.

Na afronding kan de oorspronkelijke applicatie volledig worden
uitgefaseerd.

- Voordelen

  - Maximale aansluiting op de doelarchitectuur.

  - Geen structurele synchronisatie tussen systemen.

  - Optimale herbruikbaarheid van services.

  - Eenvoudiger beheer op langere termijn.

- Aandachtspunten

  - Grootste implementatie-inspanning.

  - Organisatorische verandering is vaak omvangrijk.

  - Vereist volledige migratie van processen en gegevens.

    <img
    src="../../media/media/image32.png"
    style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
    alt="Afbeelding met tekst, schermopname, diagram, Lettertype Door AI gegenereerde inhoud is mogelijk onjuist." />

### Patroon B – Hybride implementatie

Patroon B is bedoeld voor situaties waarin bestaande SaaS- of
legacy-oplossingen voorlopig gehandhaafd blijven. De procesuitvoering
vindt daarbij plaats buiten het Platform Dienstverlening, terwijl
gegevens, interactie en integratie zoveel mogelijk volgens de
architectuur worden ingericht. De bestaande applicatie wordt gekoppeld
aan de registraties en platformvoorzieningen, zodat de gegevenslaag al
voldoet aan de uitgangspunten van Common Ground.

Hierdoor ontstaat een hybride architectuur waarin:

- Interactie plaatsvindt via de platformvoorzieningen;

- Gegevens worden beheerd in Common Ground-registraties;

- Processen voorlopig blijven draaien in de bestaande applicatie.

- Voordelen

  - Versnelt de transitie naar de doelarchitectuur.

  - Gemeenten verkrijgen regie over hun gegevens.

  - Gegevens kunnen direct worden gebruikt door andere
    platformvoorzieningen, zoals MijnServices en integrale klantbeelden.

  - Beperkt de impact op bestaande bedrijfsprocessen.

- Aandachtspunten

  - Tijdelijke dubbele inrichting van beheer en configuratie.

  - Extra complexiteit door gegevenssynchronisatie.

  - Hogere beheerlast zolang beide werelden naast elkaar bestaan.

  - Bedoeld als tussenstap; uiteindelijk blijft Patroon A het eindbeeld.

#### Praktische implementatiestappen

- Inrichten van de benodigde registraties binnen het Platform
  Dienstverlening.

- Realiseren van API-koppelingen tussen de bestaande applicatie en de
  platformregistraties.

- Inrichten en testen van de gegevenssynchronisatie.

- Gefaseerd overnemen van functionaliteit totdat de bestaande applicatie
  kan worden uitgefaseerd.

<img
src="../../media/media/image33.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%"
alt="Afbeelding met tekst, schermopname, lijn, Lettertype Door AI gegenereerde inhoud is mogelijk onjuist." />
