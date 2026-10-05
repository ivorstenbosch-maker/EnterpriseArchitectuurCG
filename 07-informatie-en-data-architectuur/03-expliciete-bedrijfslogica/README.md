# Expliciete bedrijfslogica

De informatiearchitectuur geeft ook uitdrukking aan het [**Principe:
Expliciete bedrijfslogica**](../05-visie-principes-scope/04-architectuurprincipes/README.md#principe-expliciete-bedrijfslogica):
Bedrijfslogica wordt expliciet gemodelleerd en losgekoppeld van
processen, gegevens en softwarecomponenten. Regels die voortkomen uit
wetgeving, beleid of gemeentelijke afspraken worden éénmalig vastgelegd,
centraal beheerd en meervoudig toegepast.

Beslisregels vormen een zelfstandig bedrijfsobject binnen deze
architectuur. Zij beschrijven de formele vertaling van wet- en
regelgeving of beleid naar uitvoerbare logica. Beslisregels kennen een
eigen levenscyclus, versiebeheer, geldigheidsperiode en metadata. Dat
heeft de volgende implicaties:

- Beslisregels vormen een expliciet onderdeel van de dienstverlening en
  beschrijven hoe wetgeving en beleid worden toegepast.

- Beslisregels zijn versieerbaar en historisch reproduceerbaar.

- Beslisregels zijn begrijpelijk voor beleidsmedewerkers, juristen en
  uitvoerende professionals.
