---
title: Type de navigateur
description: L’entreprise qui a créé le navigateur.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 89%

---

# Type de navigateur

&quot;Type de navigateur&quot; [dimension](overview.md) répertorie les organisations qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle offre une valeur à la dimension « Navigateurs » dans la mesure où elle ne répertorie pas les différentes versions d’un même navigateur comme des éléments de dimension distincts.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les entreprises qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de [!DNL Firefox]).
