# Verzoekenpatroon

Het verzoekenpatroon vormt het standaardpatroon voor het starten van
dienstverlening. Het uitgangspunt is dat een aanvraag eerst als
zelfstandig **Verzoek** wordt geregistreerd, voordat een proces of zaak
wordt gestart. Hierdoor wordt de interactie met de inwoner losgekoppeld
van de procesafhandeling.

Het patroon bestaat uit de volgende stappen:

- Een kanaal registreert een verzoek via de Verzoeken API.

- Het verzoek wordt gevalideerd.

- Het verzoek wordt opgeslagen als zelfstandig informatieobject.

- De registratie publiceert een notificatie.

- Procescomponenten bepalen zelfstandig of en welk proces moet worden
  gestart.

Hierdoor kunnen meerdere processen gebruikmaken van dezelfde
verzoekregistratie.

#### Aansluiten op het patroon

Procescomponenten:

- Abonneren zich op relevante notificaties.

- Halen het volledige verzoek op via de API.

- Bepalen zelfstandig welk proces moet worden gestart.
