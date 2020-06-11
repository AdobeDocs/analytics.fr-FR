---
title: Type de navigateur
description: Organisation qui a créé le navigateur.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# Type de navigateur

La dimension &quot;Type de navigateur&quot; liste les organisations qui ont créé le navigateur utilisé par le visiteur. Cette dimension est utile pour identifier les navigateurs les plus utilisés par les visiteurs. Il fournit une valeur sur la dimension &quot;Navigateurs&quot; en ce sens qu’il ne liste pas les différentes versions d’un même navigateur en tant que valeurs de dimension distinctes.

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix interne à Adobe. La valeur de recherche est basée sur l’en-tête `User-Agent` HTTP dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi.

## Valeurs de dimension

Les valeurs de dimension incluent les organisations qui créent des navigateurs. Les valeurs de dimension courantes sont `"Google"` (les créateurs de [!DNL Chrome]), `"Apple"` (les créateurs de [!DNL Safari]), `"Microsoft"` (les créateurs de [!DNL Edge]) et `"Mozilla"` (les créateurs de ).[!DNL Firefox]
