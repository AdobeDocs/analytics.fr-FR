---
title: Mise en oeuvre d’Adobe Analytics à l’aide du SDK Web de Adobe Experience Platform
description: Utilisez l’extension SDK Web dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# Mise en oeuvre d’Adobe Analytics à l’aide du SDK Web de Adobe Experience Platform

Vous pouvez utiliser la variable [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=fr) pour envoyer des données à Adobe Analytics. Cette méthode de mise en oeuvre fonctionne en traduisant la variable [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=fr) dans un format utilisé par Analytics.

## Configuration

Pour configurer Analytics pour recevoir des données XDM :

1. Installez et [configurez](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) le [SDK Web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=fr).

1. Assurez-vous que les suites de rapports applicables sont mappées aux données de votre choix. Les données XDM sont automatiquement transmises à la suite de rapports à partir d’Adobe Experience Edge.
