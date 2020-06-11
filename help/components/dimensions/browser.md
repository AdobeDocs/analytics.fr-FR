---
title: Navigateur
description: Nom et version du navigateur utilisé.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Navigateur

La dimension &quot;Navigateur&quot; indique le nom et la version du navigateur qui envoie l’accès. Cette dimension est utile pour comprendre quels sont les navigateurs les plus utilisés par les visiteurs. Lors du test de nouvelles versions de votre site, vous pouvez exécuter ces tests sur les principaux navigateurs de cette dimension afin d’optimiser les efforts de contrôle de la qualité.

## Renseigner cette dimension avec des données

Cette dimension fait référence à une table de choix interne à Adobe. La valeur de recherche est basée sur l’en-tête `User-Agent` HTTP dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par exemple via le lancement d’Adobe Experience Platform), cette dimension est prête à l’emploi.

## Valeurs de dimension

Les valeurs de dimension incluent les noms et versions des navigateurs utilisés. Les différentes versions d’un même navigateur sont des valeurs de dimension distinctes.

Certaines valeurs de dimension contiennent `"(unknown version)"` à la place de leur numéro de version. Cette valeur de dimension fait référence à une version récente du navigateur que Adobe n’a pas ajoutée à ses tables de recherche. Comme les navigateurs sont fréquemment mis à jour, le navigateur `"(unknown version)"` pour un navigateur donné est courant et temporaire. Adobe met généralement à jour les tables de recherche lors des versions de maintenance mensuelles.
