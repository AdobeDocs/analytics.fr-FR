---
title: Type de navigateur
description: L’entreprise qui a créé le navigateur.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 69%

---

# Type de navigateur

&quot;Type de navigateur&quot; [dimension](overview.md) répertorie les organisations qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle offre une valeur à la dimension « Navigateurs » dans la mesure où elle ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Adobe de partenaires avec [DeviceAtlas](https://deviceatlas.com/) pour gérer les recherches entre l’agent utilisateur et le navigateur.

* Pour les implémentations AppMeasurement, cette dimension est prête à l’emploi.
* Pour les implémentations du SDK Web, activez [!UICONTROL Recherche de périphérique] when [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

## Éléments de dimension

Les éléments de dimension incluent les entreprises qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de [!DNL Firefox]).
