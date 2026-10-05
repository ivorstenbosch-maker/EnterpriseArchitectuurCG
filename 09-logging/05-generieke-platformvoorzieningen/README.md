# Generieke platformvoorzieningen

Voor bovenstaande inrichting zijn in de doelarchitectuur drie generieke
voorzieningen nodig.

#### Logboek Dataverwerkingen

Het **Logboek Dataverwerkingen** is de centrale voorziening waarin de
verwerkingslogregels ketenbreed worden verzameld.

Het LDV moet onder meer:

- Verwerkingen ketenbreed kunnen reconstrueren;

- Verwerkingen kunnen koppelen aan het verwerkingsregister;

- De autorisatiebeslissing kunnen koppelen;

- Kunnen zoeken en filteren;

- Verschillende doelgroepen gecontroleerd inzage kunnen geven;

- Bewaartermijnen ondersteunen;

- Uitlegbaarheid en inzage mogelijk maken.

#### Verwerkingenregister

Het **Verwerkingenregister** beschrijft vooraf welke verwerkingen zijn
toegestaan: welk doel de verwerking heeft en op welke grondslag deze
plaatsvindt.

Het LDV verwijst vervolgens naar deze registratie. Daardoor ontstaat de
gewenste relatie:

**beleid / doelbinding → toegestane verwerking → feitelijke verwerking →
logregel**

De doelarchitectuur beschrijft dit als de koppeling tussen het register
van verwerkingsactiviteiten en het operationele verwerkingenlog.

#### Presentatie

Bovenop het logboek komt een presentatielaag voor bijvoorbeeld:

- Inzage door de inwoner;

- Auditing;

- Toezicht en verantwoording.

De presentatievoorziening is daarbij niet zelf de bron van de logging.
Zij ontsluit informatie uit het centrale logboek, met autorisatie en
dataminimalisatie passend bij de doelgroep.
