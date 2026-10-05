# Autorisatie (huidige situatie)

Autorisatie *tussen* services wordt primair gerealiseerd op **laag 3
(integratie- en servicelaag)** via de FSC. Binnen de FSC worden
afspraken (contracten) vastgelegd tussen dienstaanbieders en afnemers.
Toegang tot API’s wordt daarbij gecontroleerd op basis van deze
contracten en technisch afgedwongen met behulp van tokens (bijvoorbeeld
JWT). Hierdoor is geborgd dat alleen geautoriseerde afnemers gebruik
kunnen maken van specifieke services.

Binnen afnemende services op **laag 4 en 5** — zoals KISS en GZAC —
wordt aanvullende autorisatie ingericht op basis van rollen en rechten.
Dit betekent dat gebruikers binnen deze applicaties alleen toegang
hebben tot functionaliteiten en gegevens die passen bij hun rol.
Tegelijkertijd worden binnen deze applicaties auditlogs gegenereerd,
waarin gebruikershandelingen worden vastgelegd ten behoeve van
verantwoording en controle.
