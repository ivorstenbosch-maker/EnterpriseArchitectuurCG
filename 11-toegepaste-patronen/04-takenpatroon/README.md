# Takenpatroon

Taken worden binnen het platform niet rechtstreeks aangeboden vanuit
procescomponenten, maar eerst geregistreerd als zelfstandig
informatieobject. Procescomponenten zijn verantwoordelijk voor het
registreren en beheren van taken; gebruikersinterfaces zijn
verantwoordelijk voor het tonen en afhandelen ervan.

Hierdoor ontstaat een generieke takenvoorziening die door meerdere
processen en gebruikersinterfaces kan worden hergebruikt.

#### Aansluiten op het patroon

Procescomponenten:

- Registreren taken via de Taken API.

- Koppelen taken aan het relevante hoofdobject.

- Beheren de levenscyclus van de taak.

De takenregistratie:

- Registreert de taken

- Publiceert wijzigingen via notificaties.

Portalen:

- Halen bij login van de gebruiker de taken op

- Tonen de actuele taken

- Verwerken gebruikersacties.
