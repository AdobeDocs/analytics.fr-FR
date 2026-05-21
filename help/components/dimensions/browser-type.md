---
title: Type de navigateur
description: L’entreprise qui a créé le navigateur.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 69%

---

# Type de navigateur

La [dimension](overview.md) « Type de navigateur » répertorie les organisations qui ont créé le navigateur que le visiteur utilise. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle offre une valeur à la dimension « Navigateurs » dans la mesure où elle ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe s’associe à [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le navigateur.

* Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations de Web SDK, activez [!UICONTROL Recherche d’appareil] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les entreprises qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de [!DNL Firefox]).
