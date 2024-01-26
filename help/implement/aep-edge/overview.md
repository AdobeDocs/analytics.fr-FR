---
title: Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge
description: Présentation de l’utilisation des données XDM d’Experience Platform dans Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 37%

---

# Mettre en œuvre Adobe Analytics à l’aide d’Adobe Experience Platform Edge

Adobe Experience Platform Edge vous permet d’envoyer des données destinées à plusieurs produits vers un emplacement centralisé. Experience Edge transfère les informations appropriées aux produits souhaités. Ce concept vous permet de consolider les efforts de mise en œuvre, en particulier sur plusieurs solutions de données.

Adobe propose trois méthodes principales pour envoyer des données à Experience Edge :

* **[SDK Web Adobe Experience Platform](web-sdk/overview.md)** : utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[SDK Mobile Adobe Experience Platform](mobile-sdk/overview.md)** : utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Edge.
* **[API du serveur réseau Adobe Experience Platform Edge](server-api/overview.md)**: envoyez directement des données à Edge à l’aide d’une API.



## Comment Adobe Analytics gère les données Experience Edge

Les données envoyées à Experience Edge doivent être conformes aux schémas basés sur [XDM (modèle de données d’expérience)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr). XDM vous offre davantage de flexibilité quant aux champs définis comme faisant partie d’événements. Au moment où les événements atteignent Adobe Analytics, ces événements sont traduits en données plus structurées qu’Adobe Analytics peut gérer : pages vues ou événements de lien.

XDM ne détermine pas lui-même comment définir les pages vues ou les événements de lien, et il n’indique pas non plus à Adobe Analytics comment traiter sa charge utile. Par exemple, certains champs XDM prêts à l’emploi qui semblent liés à des pages vues ou des événements de lien, comme `eventType`, `web.webPageDetails.pageViews`, ou `web.webInteraction.linkEvents` sont entièrement agnostiques en matière de mise en oeuvre et n’ont aucun intérêt pour Adobe Analytics.

Pour gérer correctement les pages vues et les événements de lien, la logique suivante est appliquée aux données envoyées au réseau Experience Edge Adobe et transférées vers Adobe Analytics.

| La charge utile XDM contient... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` ou `web.webPageDetails.URL` et non `web.webInteraction.type` | considère la charge utile a **page vue** |
| `web.webInteraction.type` et (`web.webInteraction.name` ou `web.webInteraction.url`) | considère la charge utile a **événement de lien** |
| `web.webInteraction.type` et (`web.webPageDetails.name` ou `web.webPageDetails.url`) | considère la charge utile a **événement de lien** <br/>`web.webPageDetails.name` et `web.webPageDetails.URL` sont définis sur `null` |
| non `web.webInteraction.type` et (non `webPageDetails.name` et non `web.webPageDetails.URL`) | supprime la charge utile et ignore les données |

{style="table-layout:auto"}

