# Berichtenpatroon

Ook berichten worden als zelfstandig informatieobject geregistreerd
voordat zij daadwerkelijk worden verzonden. Procescomponenten zijn
verantwoordelijk voor **wat** moet worden gecommuniceerd; de
berichtenvoorziening (Outputmanagementcomponent en Notify) bepaalt
**hoe** en via welk kanaal dit gebeurt.

Het patroon bestaat uit:

- Registratie van het bericht.

- Validatie.

- Opslag.

- Publicatie van een notificatie.

- Verzending door de omnichannelvoorziening.

Hierdoor ontstaat een volledige scheiding tussen proceslogica en
communicatiekanalen.

#### Aansluiten op het patroon

Procescomponenten:

- Stellen berichten inhoudelijk samen.

- Registreren deze via de Berichten API.

- Relateren berichten aan het relevante hoofdobject.

OMC/Notify:

- Abonneert zich op relevante notificaties.

- Haalt berichtgegevens op.

- Bepaalt – op basis van klantgegevens (KlantenAPI) via welk kanaal het
  bericht moet worden verzonden

- Verzorgt de daadwerkelijke verzending.
