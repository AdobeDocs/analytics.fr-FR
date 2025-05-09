---
description: Table de recherche permettant de déterminer le type d’accès en fonction de l’événement de page.
keywords: page;événement;page_event;post_page_event
title: Recherche d’événement de page
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# Recherche d’événement de page

Table de recherche permettant de déterminer le type d’un accès en fonction de la valeur `page_event`. Comme indiqué dans la [Référence des colonnes de données](datafeeds-reference.md), les colonnes `page_event` et `post_page_event` ne comportent pas de signe.

* Consultez [`t()`](/help/implement/vars/functions/t-method.md) pour comprendre l’implémentation des appels de pages vues pour AppMeasurement et le SDK Web.
* Consultez [`tl()`](/help/implement/vars/functions/tl-method.md) pour comprendre l’implémentation des appels de suivi des liens pour AppMeasurement et le SDK Web.
* Consultez [Implémentation d’Adobe Analytics avec Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) pour découvrir comment Adobe Analytics traduit les payloads XDM en types d’événements de page.

| Valeur `page_event` | Valeur `post_page_event` | Description |
| --- | --- | --- |
| `0` | `0` | Tous les appels de pages vues standard. Il s’agit de la valeur par défaut pour la plupart des accès. |
| `10` | `100` | Liens personnalisés. Définissez le type de lien sur `o` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `other` (Web SDK ou Mobile SDK). |
| `11` | `101` | Liens de téléchargement. Définissez le type de lien sur `d` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `download` (Web SDK ou Mobile SDK). |
| `12` | `102` | Liens de sortie. Définissez le type de lien sur `e` (AppMeasurement) ou `xdm.web.webInteraction.type` sur `exit` (Web SDK ou Mobile SDK). |
| `31` | `76` | Démarrage du média |
| `32` | `77` | Mises à jour des médias (sans autre traitement des variables) |
| `33` | `78` | Mises à jour des médias (avec autre traitement des variables) |
| `40` | `80` | Enquête |
| `50` | `50` | Début du streaming multimédia |
| `51` | `51` | Fermeture du streaming multimédia |
| `52` | `52` | Nettoyage des médias en flux continu |
| `53` | `53` | Les médias en flux continu restent actifs |
| `54` | `54` | Démarrage de la publicité pour les médias en flux continu |
| `55` | `55` | Annonce publicitaire en flux continu |
| `56` | `56` | Nettoyage et nettoyage des médias en flux continu |
| `60` | `60` | Démarrage du média Primetime |
| `61` | `61` | Fermeture du média Primetime |
| `62` | `62` | Nettoyage des médias Primetime |
| `63` | `63` | Les médias Primetime restent actifs |
| `64` | `64` | Démarrage de l’annonce publicitaire sur les médias Primetime |
| `65` | `65` | Annonce publicitaire sur le média Primetime |
| `66` | `66` | Nettoyage et nettoyage des médias Primetime |
| `70` | `70` | Inclut les données d’activité de Target |
