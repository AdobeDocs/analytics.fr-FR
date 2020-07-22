---
title: Type de navigateur
description: Organisation qui a créé le navigateur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# Type de navigateur

La dimension &quot;Type de navigateur&quot; liste les organisations qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Elle fournit une valeur sur la dimension &quot;Navigateurs&quot; en ce qu’elle ne liste pas les différentes versions d’un même navigateur en tant qu’éléments de dimension distincts.

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix interne à Adobe. La valeur de recherche est basée sur l’en-tête `User-Agent` HTTP dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par exemple par le biais du lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension incluent les organisations qui créent des navigateurs. Les éléments de dimension courants comprennent `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de ).[!DNL Firefox]
