---
title: Navigateur
description: Le nom et la version du navigateur utilisé.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# Navigateur

Le &quot;[!UICONTROL Navigateur]&#39; [dimension](overview.md) indique le nom et la version du navigateur qui envoie l’accès. Cette dimension est utile pour comprendre les navigateurs les plus utilisés par les visiteurs. Lors du test de nouvelles versions du site, vous pouvez exécuter ces tests sur les principaux navigateurs de cette dimension afin d’optimiser les tâches de contrôle de la qualité.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à une table de recherche interne à Adobe. La valeur de recherche est basée sur l’en-tête HTTP `User-Agent` dans les demandes d’image. Si vous utilisez une bibliothèque AppMeasurement (par le biais des balises dans Adobe Experience Platform, par exemple), cette dimension est prête à l’emploi.

## Éléments de dimension

Les éléments de dimension comprennent les noms et les versions des navigateurs utilisés. Les différentes versions d’un même navigateur sont des éléments de dimension distincts.

Certains éléments de dimension contiennent `"(unknown version)"` à la place du numéro de version. Cet élément de dimension fait référence à une version récente du navigateur qu’Adobe n’a pas ajouté aux tables de recherche. Comme les navigateurs sont fréquemment mis à jour, l’élément `"(unknown version)"` d’un navigateur donné est courant et temporaire. Adobe met généralement à jour les tables de recherche lors des versions de maintenance mensuelles.

## Modifications de l’étiquetage et de la définition

Vous trouverez ci-dessous une liste des modifications apportées à la représentation des navigateurs dans les rapports. Ces modifications peuvent avoir un impact sur vos rapports ou sur toute logique, telle que les segments, qui dépend de ces valeurs.

### Suppression d’une société du navigateur

À compter de la version 100 pour les navigateurs Chrome, Edge et Firefox, le nom de l’entreprise n’apparaîtra plus avant le navigateur. Cela peut avoir un impact sur les utilisateurs s’ils disposent de définitions de segment basées sur le nom du navigateur. Par exemple, un segment comprenant une définition selon laquelle &quot;le navigateur contient &quot;Google&quot; n’identifie plus les navigateurs Chrome à partir de la version 110.

Exemples :

La version 109 de Chrome s’affiche sous la forme &quot;Google Chrome 109&quot;.
La version 110 de Chrome apparaît comme &quot;Chrome 109&quot;.

### Suppression de la distinction entre mobile et non-mobile pour Chrome

À partir de Chrome 110, les versions mobile et non mobile de Chrome seront étiquetées de la même manière. Actuellement, les versions mobiles et non mobiles sont étiquetées séparément. Ce qui est important, c&#39;est que cela change la signification du nom sans &quot;mobile&quot;. &quot;Chrome 109&quot; est non mobile (c’est-à-dire ordinateur de bureau) &quot;Chrome 110&quot; est mobile et non mobile. Encore une fois, si le nom du navigateur contient des définitions de segment faisant référence à &quot;mobile&quot;, elles peuvent ne plus fonctionner comme prévu. Vous pouvez utiliser la segmentation et les ventilations mobiles pour comparer le trafic mobile au trafic non mobile.

Exemples :

Mobile Chrome 109 s’affiche comme &quot;Chrome Mobile 109&quot;.
Chrome 109 non mobile apparaît comme &quot;Chrome 109&quot;.

Mobile Chrome 110 s’affiche comme &quot;Chrome 110&quot;.
Chrome 110 non mobile apparaît comme &quot;Chrome 110&quot;.
