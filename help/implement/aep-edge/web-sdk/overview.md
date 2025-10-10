---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez le SDK Web pour envoyer des données à Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) pour envoyer des données à Adobe Analytics. Il existe deux méthodes principales pour implémenter le SDK Web, et chaque méthode possède deux types d’implémentation :

| | **Migration depuis AppMeasurement** | **Implémentation de Clean Web SDK** |
| --- | --- | --- |
| **Utiliser les balises** | [ Migration de l’extension Analytics vers l’extension Web SDK ](analytics-extension-to-web-sdk.md) | [Envoyer des données à Adobe Analytics à l’aide de l’extension Web SDK](web-sdk-tag-extension.md) |
| **Utiliser JavaScript** | [Migration d’AppMeasurement vers la bibliothèque JavaScript Web SDK](appmeasurement-to-web-sdk.md) | [Envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript Web SDK](web-sdk-javascript-library.md) |

Si votre entreprise a besoin d’une nouvelle mise en œuvre de Web SDK et prévoit d’utiliser Customer Journey Analytics à l’avenir, Adobe recommande une mise en œuvre de Web SDK propre et utilisant votre propre schéma. Voir [ Ingestion de données via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) dans le guide d’utilisation de Customer Journey Analytics.

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation sur le SDK web d’Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
