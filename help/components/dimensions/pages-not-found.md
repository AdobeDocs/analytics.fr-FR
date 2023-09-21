---
title: Pages introuvables (dimensions)
description: Adresses URL ayant renvoyé une erreur sur votre site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 92%

---

# Pages introuvables

*Cette page d’aide décrit le fonctionnement de &quot;Pages introuvables&quot; en tant que [dimension](overview.md). Pour plus d’informations, consultez la mesure [Pages introuvables](../metrics/pages-not-found.md).*

La dimension « Pages introuvables » indique les adresses URL qui contenaient une erreur. Cette dimension s’avère utile lorsque vous souhaitez réduire le nombre d’erreurs rencontrées par les visiteurs sur votre site.

* Vous pouvez utiliser cette dimension dans une [visualisation de flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) pour identifier les pages sur lesquelles les visiteurs cliquent pour atteindre l’erreur. Vous pouvez ensuite travailler avec les équipes de développement de votre organisation pour corriger le lien sur chaque page.
* Vous pouvez utiliser cette dimension avec la dimension [Référent](referrer.md) pour déterminer la page de votre site sur laquelle les visiteurs arrivent depuis les liens externes. Vous pouvez ensuite implémenter des redirections vers l’emplacement souhaité ou travailler avec un tiers pour corriger le lien.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données des [`pageType` chaînes de requête `g` à partir de ](/help/implement/validate/query-parameters.md) et dans les demandes d’image. Si la chaîne de requête `pageType` est égale à `errorPage`, la chaîne de requête `g` (URL de la page) est enregistrée. AppMeasurement collecte ces données à l’aide de la variable [`pageType`](/help/implement/vars/page-vars/pagetype.md). Si la variable `pageType` n’est pas définie ou si elle est définie sur autre chose que `errorPage`, aucune donnée n’est collectée pour cette dimension.

## Éléments de dimension

Les éléments de dimension incluent les adresses URL des pages de votre site où une erreur s’est produite.
