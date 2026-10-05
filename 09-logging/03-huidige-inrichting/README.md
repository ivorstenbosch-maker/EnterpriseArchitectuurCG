# Huidige inrichting

In de huidige vorm van het platform is logging als volgt in te richten:

<img
src="../../media/media/image29.png"
style="display:block;margin-left:auto;margin-right:auto;;width:80.0%" />

- **Logging van verkeer tussen services (groene lijn)** vindt plaats in
  de onderliggende infrastructuur, binnen de servicemesh (Istio) en de
  observability stack van Haven+. Dit biedt (nu) beperkt inzicht in de
  onderliggende API-calls tussen services. FSC legt vast welke services
  met elkaar communiceren, wanneer dit gebeurt en hoe het verkeer
  verloopt, en registreert transacties en autorisaties op kanaalniveau.

- **Binnen services en applicaties (laag 4/5) (rode pijl)** wordt
  autorisatie ingericht op basis van rollen en context, en worden - als
  het goed is - auditlogs bijgehouden van handelingen binnen de service
  zelf. Deze logging is gericht op het vastleggen van verwerkingen
  binnen de eigen service. Er is ook geen - centrale of
  gestructureerde - vastgestelde plek die aan de functionele eisen voor
  Duurzame Toegankelijkheid (bijv. bewaartermijnen) voldoet, of
  bedrijfsfuncties levert zoals inzage. Er is ook geen standaard in
  gebruik voor het formaat van logregels.

Het vergaren en benutten van logs zijn functionele eisen aan het
platform (en vormen dus een architectural buildingblocks). Deze zijn
momenteel niet ingevuld met solutions. Verschillende gemeenten en
services kiezen eigen oplossingen om aan de eisen te voldoen. Voor deze
buildingblocks zijn bestaande (OpenSource) oplossingen beschikbaar.
