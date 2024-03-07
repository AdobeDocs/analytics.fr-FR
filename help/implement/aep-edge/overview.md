---
title: Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge
description: Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 23%

---

# Mise en oeuvre d’Adobe Analytics avec Adobe Experience Platform Edge Network

Le réseau Adobe Experience Platform Edge vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. Le réseau Edge transfère les informations appropriées aux produits souhaités. Ce concept vous permet de consolider les efforts de mise en œuvre, en particulier sur plusieurs solutions de données.

Adobe propose trois méthodes principales pour envoyer des données au réseau Edge :

* **[SDK Web Adobe Experience Platform](web-sdk/overview.md)** : utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[SDK Mobile Adobe Experience Platform](mobile-sdk/overview.md)** : utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[API du serveur réseau Adobe Experience Platform Edge](server-api/overview.md)**: envoyez directement des données à Edge à l’aide d’une API.



## Comment Adobe Analytics gère les données du réseau Edge

Les données envoyées à Adobe Experience Platform Edge Network peuvent suivre deux formats :

* Objet XDM : configuration des schémas en fonction de [XDM (modèle de données d’expérience)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr). XDM vous offre davantage de flexibilité quant aux champs définis comme faisant partie d’événements. Au moment où les événements atteignent Adobe Analytics, ils sont traduits dans un format qu’Adobe Analytics peut traiter.
* Objet de données : envoyez des données au réseau Edge à l’aide de champs spécifiques mappés à Adobe Analytics. Le réseau Edge détecte la présence de ces champs et les transfère vers Adobe Analytics sans avoir à se conformer à un schéma.


Le réseau Edge utilise la logique suivante pour déterminer les pages vues Adobe Analytics et les événements de lien.

| La charge utile XDM contient... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` ou `web.webPageDetails.URL` et non `web.webInteraction.type` | considère la charge utile a **page vue** |
| `web.webInteraction.type` et (`web.webInteraction.name` ou `web.webInteraction.url`) | considère la charge utile a **événement de lien** |
| `web.webInteraction.type` et (`web.webPageDetails.name` ou `web.webPageDetails.url`) | considère la charge utile a **événement de lien** <br/>`web.webPageDetails.name` et `web.webPageDetails.URL` sont définis sur `null` |
| non `web.webInteraction.type` et (non `webPageDetails.name` et non `web.webPageDetails.URL`) | supprime la charge utile et ignore les données |

{style="table-layout:auto"}

Voir [Groupe de champs de l’extension complète Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html) pour plus d’informations.
