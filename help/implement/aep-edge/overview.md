---
title: Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge
description: Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 8e701a3da6f04ccf2d7ac3abd10c6df86feb00a7
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 73%

---

# Mettre en œuvre Adobe Analytics avec le réseau Edge d&#39;Adobe Experience Platform

Le réseau Edge d&#39;Adobe Experience Platform vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. Le réseau Edge transfère les informations appropriées aux produits souhaités. Ce concept vous permet de consolider les efforts de mise en œuvre, en particulier sur plusieurs solutions de données.

Adobe propose trois méthodes principales pour envoyer des données au réseau Edge :

* **[SDK Web Adobe Experience Platform](web-sdk/overview.md)** : utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[SDK Mobile Adobe Experience Platform](mobile-sdk/overview.md)** : utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[API Adobe Experience Platform Edge Network](api/overview.md)** : envoyez directement des données à Edge Network à l’aide d’une API.

## Comment Adobe Analytics gère les données du réseau Edge

Les données envoyées au réseau Edge d’Adobe Experience Platform peuvent avoir deux formats :

* Objet XDM : conforme aux schémas basés sur [XDM (modèle de données d’expérience)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr). XDM vous offre davantage de flexibilité quant aux champs définis comme faisant partie d’événements. Au moment où les événements atteignent Adobe Analytics, ils sont traduits dans un format qu’Adobe Analytics peut traiter.
* Objet de données : envoyez des données au réseau Edge à l’aide de champs spécifiques mappés à Adobe Analytics. Le réseau Edge détecte la présence de ces champs et les transfère vers Adobe Analytics sans avoir à se conformer à un schéma.

Edge Network utilise la logique suivante pour déterminer les pages vues Adobe Analytics et les événements de lien :

| La payload XDM contient... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.URL` et pas `xdm.web.webInteraction.type` | considère que la payload est une **page vue** |
| `xdm.eventType = web.webPageDetails.pageViews` | considère que la payload est une **page vue** |
| `xdm.web.webInteraction.type` et (`xdm.web.webInteraction.name` ou `xdm.web.webInteraction.url`) | considère que la payload est un **événement de lien** |
| `xdm.web.webInteraction.type` et (`xdm.web.webPageDetails.name` ou `xdm.web.webPageDetails.url`) | considère la payload comme un **événement de lien** <br/> définit également `xdm.web.webPageDetails.name` et `xdm.web.webPageDetails.URL` sur `null` |
| pas `xdm.web.webInteraction.type` et (pas `xdm.webPageDetails.name` et pas `xdm.web.webPageDetails.URL`) | supprime la payload et ignore les données |

{style="table-layout:auto"}

En plus de différencier les pages vues et les clics sur les liens, la logique suivante est en place pour déterminer si certains événements sont classés A4T ou sont ignorés.

| La payload XDM contient... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et `xdm._experience.decisioning` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = display` ou <br/>`xdm.eventType = decisioning.propositionDisplay` ou <br/>`xdm.eventType = personalization.request` ou <br/>`xdm.eventType = decisioning.propositionFetch` et aucune `xdm._experience.decisioning` | supprime la payload et ignore les données |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et `xdm._experience.decisioning` et pas de `web.webInteraction.type` | considère la payload comme un appel **A4T**. |
| `xdm.eventType = click` ou `xdm.eventType = decisioning.propositionInteract` et pas de `xdm._experience.decisioning` et pas de `web.webInteraction.type` | supprime la payload et ignore les données. |

{style="table-layout:auto"}

Pour plus d’informations, voir [Groupe de champs du schéma d’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=fr).
