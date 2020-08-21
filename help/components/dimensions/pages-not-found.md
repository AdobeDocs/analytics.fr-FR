---
title: Pages introuvables
description: Adresses URL ayant renvoyé une erreur sur votre site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 92%

---


# Pages introuvables

*Cette page d’aide décrit le fonctionnement de la dimension « Pages introuvables ». Pour plus d’informations, consultez la mesure[Pages introuvables](../metrics/pages-not-found.md).*

La dimension « Pages introuvables » indique les adresses URL qui contenaient une erreur. Cette dimension s’avère utile lorsque vous souhaitez réduire le nombre d’erreurs rencontrées par les visiteurs sur votre site.

* Vous pouvez utiliser cette dimension dans une [visualisation de flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) pour identifier les pages sur lesquelles les visiteurs cliquent pour atteindre l’erreur. Vous pouvez ensuite travailler avec les équipes de développement de votre organisation pour corriger le lien sur chaque page.
* Vous pouvez utiliser cette dimension avec la dimension [Référent](referrer.md) pour déterminer la page de votre site sur laquelle les visiteurs arrivent depuis les liens externes. Vous pouvez ensuite implémenter des redirections vers l’emplacement souhaité ou travailler avec un tiers pour corriger le lien.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données des chaînes de requête](/help/implement/validate/query-parameters.md) à partir de [`pageType` et `g` dans les demandes d’image. Si la chaîne de requête `pageType` est égale à `errorPage`, la chaîne de requête `g` (URL de la page) est enregistrée. AppMeasurement collecte ces données à l’aide de la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Si la variable `pageType` n’est pas définie ou si elle est définie sur autre chose que `errorPage`, aucune donnée n’est collectée pour cette dimension.

## Éléments de Dimension

Les éléments de Dimension incluent les URL des pages de votre site où une erreur s’est produite.
