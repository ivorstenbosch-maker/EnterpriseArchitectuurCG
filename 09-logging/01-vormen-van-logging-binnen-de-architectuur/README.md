# Vormen van logging binnen de architectuur

Verschillende doelen stellen ook verschillende eisen aan de vastgelegde
informatie, de bewaartermijnen en de wijze waarop logging wordt
gebruikt. Logging is daarom geen eenduidige voorziening, maar bestaat
uit meerdere vormen die elk een eigen verantwoordelijkheid en
toepassingsgebied hebben.

Op hoofdlijnen worden binnen de architectuur drie vormen onderscheiden:

- Technische logging (infrastructuur en observability)

  - Deze vorm richt zich op het functioneren van systemen en
    infrastructuur. Het gaat om logs, metrics en traces die inzicht
    geven in beschikbaarheid, performance en onderlinge communicatie
    tussen services.

  - Deze logging wordt gerealiseerd in de onderliggende infrastructuur
    (Haven/Haven+) en via standaarden zoals OpenTelemetry. Zij maakt het
    mogelijk om storingen te analyseren, ketens te volgen en de
    technische werking van het platform te monitoren.

- Security logging

  - Security logging richt zich op het detecteren en analyseren van
    beveiligingsincidenten en afwijkend gedrag.

  - Deze logging ontstaat op meerdere plekken in het platform, zoals de
    infrastructuur, identity-voorzieningen en autorisatieketen, en wordt
    gebruikt voor monitoring, alarmering en incidentonderzoek. Het
    resultaat is een set events die inzicht geven in mogelijke
    dreigingen en misbruik.

- Logging op juridisch en verantwoordingsniveau

  - De derde vorm betreft logging vanuit het perspectief van
    gegevensgebruik. In deze context bestaan drie niveaus van logging:

    - Connectie van services (via FSC),

    - Toegang (via (Open)FTV) en

    - Verwerking (waarvoor het [Logboek
      dataverwerkingen](https://logius-standaarden.github.io/logboek-dataverwerkingen/) -
      LDV - de standaard is).

  - Deze zijn formeel met elkaar verbonden in de standaarden. Voor de
    terminologie is het belangrijk alleen LDV een dataverwerking te
    noemen. FTV en FSC (of elke andere gateway) doen geen verwerking in
    wettelijke zin (AVG/Wpg/etc).

Bij logging van Dataverwerking staat de vraag centraal:

- Wie heeft welke gegevens gebruikt, wanneer, met welk doel en op basis
  van welke grondslag?

Deze logging is noodzakelijk voor rechtmatigheid, transparantie en
verantwoording richting inwoners, toezichthouders en bestuur, en dit is
het hoofdthema van dit onderdeel.
