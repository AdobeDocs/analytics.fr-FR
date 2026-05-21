---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform
description: Utilisez le SDK Web pour envoyer des données à Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/4pS-q3F3W7D1ojdMkCzgUyZkO3LDt1DpFfxqcTtZXLQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 42%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Web d’Adobe Experience Platform

Vous pouvez utiliser le [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) pour envoyer des données à Adobe Analytics. Il existe deux méthodes principales pour implémenter le SDK Web, et chaque méthode possède deux types d’implémentation :

| | **Migration depuis AppMeasurement** | **Implémentation de Clean Web SDK** |
| --- | --- | --- |
| **Utiliser les balises** | [&#x200B; Migration de l’extension Analytics vers l’extension Web SDK &#x200B;](analytics-extension-to-web-sdk.md) | [Envoyer des données à Adobe Analytics à l’aide de l’extension Web SDK](web-sdk-tag-extension.md) |
| **Utiliser JavaScript** | [Migration d’AppMeasurement vers la bibliothèque JavaScript Web SDK](appmeasurement-to-web-sdk.md) | [Envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript Web SDK](web-sdk-javascript-library.md) |

Si votre entreprise a besoin d’une nouvelle mise en œuvre de Web SDK et prévoit d’utiliser Customer Journey Analytics à l’avenir, Adobe recommande une mise en œuvre de Web SDK propre et utilisant votre propre schéma. Voir [&#x200B; Ingestion de données via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) dans le guide d’utilisation de Customer Journey Analytics.

## Ressources supplémentaires

Les balises peuvent être hautement personnalisées. Découvrez comment tirer le meilleur parti d’Adobe Analytics en incluant les données appropriées dans votre mise en œuvre.

- [Documentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr#) : découvrez le fonctionnement de l’interface et les extensions disponibles.

- [Documentation de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=fr)
