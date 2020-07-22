---
title: Pages introuvables
description: URL qui ont renvoyé une erreur sur votre site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Pages introuvables

*Cette page d&#39;aide décrit le fonctionnement de &quot;Pages introuvables&quot; en tant que dimension. Pour plus d’informations, voir la mesure[Pages introuvables](../metrics/pages-not-found.md).*

La dimension Pages introuvables affiche les URL qui contenaient une erreur. Cette dimension s’avère utile lorsque vous souhaitez réduire le nombre d’erreurs que les visiteurs rencontrent sur votre site.

* Vous pouvez utiliser cette dimension dans une visualisation [](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) Flux pour identifier les pages que les visiteurs cliquent pour atteindre l’erreur. Vous pouvez ensuite travailler avec les équipes de développement de votre organisation pour corriger le lien sur chaque page.
* Vous pouvez utiliser cette dimension avec la dimension [&quot;Parrain&quot;](referrer.md) pour déterminer où les visiteurs arrivent sur votre site à partir de liens externes. Vous pouvez ensuite implémenter des redirections vers l’emplacement souhaité ou travailler avec un tiers pour faire réparer le lien.

## Renseigner cette dimension avec des données

Cette dimension récupère les données des chaînes [`pageType` `g` et](/help/implement/validate/query-parameters.md) de requête dans les demandes d’image. Si la chaîne de `pageType` requête est égale `errorPage`, la chaîne de `g` requête (URL de page) est enregistrée. AppMeasurement collecte ces données à l’aide de la [`pageType`](/help/implement/vars/page-vars/pagetype.md) variable. Si la `pageType` variable n’est pas définie ou définie sur autre chose `errorPage`, aucune donnée pour cette dimension n’est collectée.

## Éléments de dimension

Les éléments de dimension incluent les URL des pages de votre site où une erreur s’est produite.
