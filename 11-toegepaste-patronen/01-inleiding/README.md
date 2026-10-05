# Inleiding

In onderdeel [Samenwerking tussen
services](../../08-applicatiearchitectuur/04-samenwerking-tussen-services/README.md#samenwerking-tussen-services) zijn de generieke
interactievormen binnen het Platform Dienstverlening beschreven. Daar is
onderscheid gemaakt tussen synchrone communicatie (request/response),
asynchrone communicatie (event-driven) en API-compositie. Deze
beschrijven op welke wijze services technisch met elkaar samenwerken.

Dit hoofdstuk beschrijft een ander abstractieniveau. De hier opgenomen
patronen zijn oplossingspatronen voor veelvoorkomende functionele
vraagstukken binnen de gemeentelijke dienstverlening. Zij beschrijven
hoe meerdere services gezamenlijk invulling geven aan een specifieke
capability, zoals het registreren van een verzoek, het uitvoeren van een
taak of het verzenden van een bericht.

Een patroon bestaat daarbij uit een samenhang van registraties, API's,
notificaties en procescomponenten die volgens vaste afspraken
samenwerken. Een patroon kan gebruikmaken van één of meerdere
interactievormen. Zo combineert het Verzoekenpatroon bijvoorbeeld
a-synchrone notificaties voor de registratie van een verzoek met
synchrone API-calls voor de verdere procesafhandeling.
