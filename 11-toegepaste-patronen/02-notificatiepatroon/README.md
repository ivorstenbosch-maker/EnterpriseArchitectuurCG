# Notificatiepatroon

Alle interactiepatronen binnen het Platform Dienstverlening bouwen voort
op hetzelfde notificatiepatroon. Componenten communiceren zoveel
mogelijk asynchroon door gebeurtenissen (events) te publiceren. Andere
componenten kunnen zich hierop abonneren zonder dat directe
afhankelijkheden ontstaan.

Hiervoor wordt gebruikgemaakt van **Open Notificaties** die een
publish/subscribe-mechanisme biedt voor het routeren van gebeurtenissen
tussen componenten.

De belangrijkste uitgangspunten zijn:

- Componenten publiceren gebeurtenissen; zij kennen hun afnemers niet.

- Componenten ontvangen notificaties via abonnementen op één of meer
  kanalen.

- Notificaties bevatten uitsluitend verwijzingen naar gewijzigde
  gegevens (informatie-arm).

- De ontvangende component bepaalt zelfstandig of en hoe de gewijzigde
  gegevens worden opgehaald.

- Componenten moeten rekening houden met tijdelijke uitval of gemiste
  notificaties en implementeren daarom een passende herstelstrategie,
  bijvoorbeeld retries of periodieke synchronisatie.

Hierdoor ontstaat een losse koppeling tussen registraties,
procescomponenten en gebruikersvoorzieningen.
