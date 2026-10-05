# Policy Based Access Control (PBAC) en FTV

In de doelarchitectuur wordt autorisatie ingericht volgens een
**externalized authorization model** gebaseerd op het PxP-concept.
Hierbij worden verantwoordelijkheden gescheiden over meerdere
componenten:

- **PEP (Policy Enforcement Point)** Bevindt zich in API-gateways of
  services en dwingt autorisatie af.

- **PDP (Policy Decision Point)** Neemt autorisatiebeslissingen op basis
  van policies.

- **PAP (Policy Administration Point)** Beheert en publiceert
  autorisatieregels.

- **PIP (Policy Information Point)** Levert contextinformatie (bijv. uit
  registraties of andere bronnen).

Het AuthZEN-initiatief van de OpenID Foundation beschrijft hoe deze
componenten samenwerken. AuthZEN definieert een gestandaardiseerde
Authorization API waarmee een PEP een autorisatievraag kan stellen aan
een PDP. De specificatie stelt dat de PDP deze API aanbiedt en dat de
PEP deze gebruikt om beslissingen op te vragen. In een verzoek worden
bijvoorbeeld het subject (wie), de resource (waarop), de actie (wat) en
contextinformatie meegestuurd. De PDP evalueert deze gegevens tegen
policies en retourneert een beslissing zoals *permit* of *deny*.

Dit model ondersteunt externalized authorization: autorisatielogica
bevindt zich niet in applicaties zelf, maar in een aparte service. De
gekozen architectuur ondersteunt federatieve samenwerking tussen
organisaties. Dit betekent dat:

- Autorisatiebeslissingen gebaseerd zijn op context uit meerdere
  domeinen

- Policies organisatie-overstijgend kunnen worden toegepast

- Toegang tot informatieobjecten consistent en herleidbaar wordt
  beoordeeld

  Deze aanpak sluit aan bij initiatieven zoals [**Federatieve
  Toegangsverlening (FTV)**](https://vng-realisatie.github.io/ftv/) en
  de referentie-implementatie
  [OpenFTV](https://vng-realisatie.github.io/ftv/actueel/nieuws/20251014updateopenftv/)
  en is ook vastgelegd als (kandidaat) **toegepast patroon** in het
  onderdeel [Toegepaste patronen](../../11-toegepaste-patronen/README.md#toegepaste-patronen).

<img
src="../../media/media/image30.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />
