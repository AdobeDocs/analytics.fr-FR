---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=fr) pour envoyer des données à Adobe Analytics. Cette méthode de mise en œuvre fonctionne en traduisant le [modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) le [SDK Web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr).

1. Assurez-vous que les suites de rapports applicables sont mises en correspondance avec les données de votre choix. Les données XDM sont automatiquement transférées à la suite de rapports depuis Adobe Experience Edge.
