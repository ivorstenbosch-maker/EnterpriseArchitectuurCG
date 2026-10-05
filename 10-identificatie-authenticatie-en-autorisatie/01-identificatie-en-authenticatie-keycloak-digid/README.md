# Identificatie en authenticatie (Keycloak, DigiD)

Authenticatie wordt centraal verzorgd door Keycloak als Identity
Provider (IdP). Dit omvat:

- Authenticatie van gebruikers (bijv. via DigiD, eHerkenning of andere
  IdP’s)

- Uitgifte van tokens (bijv. OAuth2 / OpenID Connect)

- Identity federation

- Beheer van gebruikers, rollen en attributen

Applicaties vertrouwen op de door Keycloak uitgegeven tokens voor het
vaststellen van de identiteit van de gebruiker (subject).

Voor **eindgebruikers** (burgers en bedrijven) vindt authenticatie
plaats via erkende landelijke voorzieningen. Inwoners loggen in met
DigiD en bedrijven met eHerkenning, bijvoorbeeld bij gebruik van
OpenFormulieren en portalen (zoals een MijnOmgeving).

Daarnaast wordt het gebruik van de **European Digital Identity Wallet
(EUDI-wallet)** momenteel verder uitgewerkt als toekomstige voorziening
voor digitale identificatie en attributenuitwisseling binnen Europa.
