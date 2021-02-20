---
title: Navigateur
description: Le nom et la version du navigateur utilisé.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 100%

---


# Navigateur

La dimension « Navigateur » indique le nom et la version du navigateur qui envoie l’accès. Cette dimension est utile pour déterminer les navigateurs les plus utilisés par les visiteurs. Lors du test de nouvelles versions du site, vous pouvez exécuter ces tests sur les principaux navigateurs de cette dimension afin d’optimiser les tâches de contrôle de la qualité.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais d’Adobe Experience Platform Launch, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent les noms et les versions des navigateurs utilisés. Les différentes versions d’un même navigateur sont des éléments de dimension distincts.

Certains éléments de dimension contiennent `"(unknown version)"` à la place du numéro de version. Cet élément de dimension fait référence à une version récente du navigateur qu’Adobe n’a pas ajouté aux tables de recherche. Comme les navigateurs sont fréquemment mis à jour, l’élément `"(unknown version)"` d’un navigateur donné est courant et temporaire. Adobe met généralement à jour les tables de recherche lors des versions de maintenance mensuelles.
