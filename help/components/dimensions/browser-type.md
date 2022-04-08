---
title: Type de navigateur
description: L’entreprise qui a créé le navigateur.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '134'
ht-degree: 100%

---

# Type de navigateur

La dimension « Type de navigateur » répertorie les entreprises qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle offre une valeur à la dimension « Navigateurs » dans la mesure où elle ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les entreprises qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de [!DNL Firefox]).
