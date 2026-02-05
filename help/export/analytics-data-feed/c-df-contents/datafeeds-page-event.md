---
description: Table de recherche permettant de déterminer le type d’un accès d’après l’événement de page.
keywords: page;événement;page_event;post_page_event
title: Recherche d’événement de page
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---

# Recherche d’événement de page

Table de recherche permettant de déterminer le type d’un accès d’après la valeur `page_event`. Comme indiqué dans la [Référence des colonnes de données](datafeeds-reference.md), les colonnes `page_event` et `post_page_event` ne comportent pas de signe tinyint.

* Consultez [`t()`](/help/implement/vars/functions/t-method.md) pour comprendre l’implémentation des appels de pages vues pour AppMeasurement et le SDK web.
* Consultez [`tl()`](/help/implement/vars/functions/tl-method.md) pour comprendre l’implémentation des appels de suivi des liens pour AppMeasurement et le SDK web.
* Consultez [Implémentation d’Adobe Analytics avec Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) pour découvrir comment Adobe Analytics traduit les payloads XDM en types d’événements de page.

| Valeur `page_event` | Valeur `post_page_event` | Description |
| --- | --- | --- |
| `0` | `0` | Tous les appels de pages vues standard. Il s’agit de la valeur par défaut pour la plupart des accès. |
| `10` | `100` | Liens personnalisés. Définissez le type de lien sur `o` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `other` (SDK web ou SDK mobile). |
| `11` | `101` | Liens de téléchargement. Définissez le type de lien sur `d` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `download` (SDK web ou SDK mobile). |
| `12` | `102` | Liens de sortie. Définissez le type de lien sur `e` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `exit` (SDK web ou SDK mobile). |
| `31` | `76` | Démarrage du média |
| `32` | `77` | Mises à jour des médias (sans autre traitement des variables) |
| `33` | `78` | Mises à jour des médias (avec autre traitement des variables) |
| `40` | `80` | Enquête |
| `50` | `50` | Démarrage des médias en streaming |
| `51` | `51` | Fermeture des médias en streaming |
| `52` | `52` | Analyse des médias en streaming |
| `53` | `53` | Persistance des médias en streaming |
| `54` | `54` | Démarrage de la publicité des médias en streaming |
| `55` | `55` | Fermeture de la publicité des médias en streaming |
| `56` | `56` | Analyse publicitaire des médias en streaming |
| `60` | `60` | Démarrage des médias Primetime |
| `61` | `61` | Fermeture des médias Primetime |
| `62` | `62` | Analyse des médias Primetime |
| `63` | `63` | Persistance des médias Primetime |
| `64` | `64` | Démarrage de la publicité des médias Primetime |
| `65` | `65` | Fermeture de la publicité des médias Primetime |
| `66` | `66` | Analyse publicitaire des médias Primetime |
| `70` | `70` | Inclut les données d’activité de Target. |
