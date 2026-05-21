---
description: Table de recherche permettant de déterminer le type d’un accès d’après l’événement de page.
keywords: page;événement;page_event;post_page_event
title: Recherche d’événement de page
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: https://experienceleague.adobe.com/QAGYKNnpMl2tM6BRux7BBL-YFpMTgUIXsHT-9bGKWnA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
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
