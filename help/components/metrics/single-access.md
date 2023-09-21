---
title: Accès unique
description: Le nombre de fois qu’un élément de dimension n’a pas changé au cours d’une visite.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 93%

---

# Accès unique

&quot;Accès unique&quot; [metric](overview.md) indique le nombre de visites pour lesquelles l’élément de dimension ne contenait qu’une valeur unique pour l’intégralité de la visite. Cette mesure s’avère utile pour les dimensions dans lesquelles vous souhaitez identifier les éléments de dimension stagnants au cours d’une visite.

## Méthode de calcul de cette mesure

Cette mesure compte les visites pour lesquelles l’élément de dimension contenait une valeur unique. Vous pouvez définir l’élément de dimension plusieurs fois ou le faire persister tout en le considérant comme un accès unique. Dès qu’un élément de dimension est remplacé par une seconde valeur unique, la visite n’est plus considérée comme un accès unique.

## Différence entre « Accès unique » et « Visite de page unique »

Dans le cadre de la dimension [Page](../dimensions/page.md), « Accès unique » et « Visites de page unique » sont parfaitement identiques. Des différences apparaissent lorsque vous utilisez d’autres dimensions.

* **Accès unique** : indique le nombre de visites au cours desquelles l’élément de dimension donné n’a pas changé pour l’intégralité de la visite. Il est lié à la dimension que vous utilisez dans votre projet.
* **Visite de page unique** : indique le nombre de visites au cours desquelles la dimension « Page » n’a pas changé pour l’intégralité de la visite. Même si vous utilisez une autre dimension dans votre rapport, elle tient tout de même compte des visites contenant un élément de dimension « Page » unique.

Prenons l’exemple suivant de deux visites d’accès. La dimension de votre rapport est [Section du site](../dimensions/site-section.md).

* Un visiteur accède à deux pages, mais elles se trouvent toutes deux dans la même section du site. Comme la section du site n’a pas changé pendant la visite, cela est considéré comme un accès unique. Cela ne constitue pas une visite de page unique, car la visite contient plusieurs éléments de dimension Page uniques.
* Un visiteur accède à deux pages dans différentes sections du site, mais il se trouve que les deux pages portent le même nom. La visite ne constitue pas un accès unique, car le site comptait deux valeurs de section uniques. Elle constitue une visite de page unique, car le site comptait qu’un seul élément de dimension Page unique.
