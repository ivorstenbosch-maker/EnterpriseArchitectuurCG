# Het Vijf-lagen model

Conform de [Informatiekundige visie Common
Ground](https://www.gemmaonline.nl/wiki/Thema-architectuur_Common_Ground)
maakt de applicatie-architectuur van het Platform onderscheid tussen:

- **Interactie** (gebruikersinterface)

- **Proces** (afhandeling van het proces)

- **Connectiviteit** (aansluiting van afnemers en diensten)

- **Diensten** (API’s)

- **Gegevens** (registraties).

  <img
  src="../../media/media/image22.png"
  style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

  Deze lagen, hun betekenis en betrokken (applicatie)capabilities worden
  in [Architectural Building Blocks (ABB’s) en
  clusters](../07-architectural-building-blocks-abb-s-en-clusters/README.md#architectural-building-blocks-abbs-en-clusters) verder
  toegelicht.

#### Interpretatie van het lagenmodel

Het lagenmodel geeft op hoofdlijnen de verdeling van
verantwoordelijkheden binnen de applicatiearchitectuur weer. Het is een
**conceptueel architectuurmodel** en geen letterlijk implementatiemodel.
De plaats van een component in een laag geeft aan **waar de primaire
verantwoordelijkheid ligt**, niet dat de component uitsluitend
functionaliteit uit die laag bevat.

In de praktijk bevatten componenten ook ondersteunende functionaliteit
uit andere lagen. Zo kent een registratie bijvoorbeeld validaties en
beperkte proceslogica, beschikt een integratievoorziening vaak over een
beheerinterface en bevatten processervices gegevens of configuratie die
noodzakelijk zijn voor hun werking. Deze functies zijn echter
ondersteunend; de component wordt ingedeeld op basis van zijn dominante
verantwoordelijkheid binnen de architectuur. Bij de ontwikkeling van
nieuwe componenten geldt daarom het uitgangspunt dat functionaliteit
wordt geplaatst in de laag waarvoor zij primair verantwoordelijk is.
