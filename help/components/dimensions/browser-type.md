---
title: Type de navigateur
description: L’entreprise qui a créé le navigateur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 100%

---


# Type de navigateur

La dimension « Type de navigateur » répertorie les entreprises qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle offre une valeur à la dimension « Navigateurs » dans la mesure où elle ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les entreprises qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de [!DNL Firefox]).
