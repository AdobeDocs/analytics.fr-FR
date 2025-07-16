---
title: Collisions de hachage
description: Décrit ce qu’est une collision de hachage et de quelle façon elle se manifeste.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 6%

---

# Collisions de hachage

Dans Adobe Analytics, les dimensions collectent les valeurs de chaîne. Parfois, ces chaînes comptent des centaines de caractères, tandis que d&#39;autres fois, elles sont courtes. Pour améliorer les performances, ces valeurs de chaîne ne sont pas utilisées directement dans le traitement. Au lieu de cela, un hachage est calculé pour chaque valeur afin d’uniformiser la taille de toutes les valeurs. Tous les rapports s’exécutent sur ces valeurs hachées, ce qui accroît considérablement leurs performances.

Pour la plupart des champs, la chaîne est d’abord convertie en minuscules. La conversion en minuscules réduit le nombre de valeurs uniques. Les valeurs sont hachées tous les mois. Dans le cas d’une valeur donnée, la première valeur vue chaque mois est utilisée. D’un mois à l’autre, il est peu probable que deux valeurs de variable uniques se hachent sur la même valeur. On parle alors de *collision de hachage*.

Les collisions de hachage peuvent se manifester dans les rapports comme suit :

* Si vous affichez un rapport au fil du temps et constatez un pic inattendu, il est possible que plusieurs valeurs uniques pour cette variable utilisent le même hachage.
* Si vous utilisez un segment et que vous voyez une valeur inattendue, il est possible que l’élément de dimension inattendu utilise le même hachage qu’un autre élément de dimension correspondant à votre segment.

## Probabilité d’une collision de hachage

Adobe Analytics utilise des hachages 32 bits pour la plupart des dimensions, ce qui signifie qu’il existe 2<sup>32 </sup> de combinaisons de hachage possibles (environ 4,3 milliards). Une nouvelle table de hachage pour chaque dimension est créée chaque mois. La probabilité approximative de rencontrer une collision de hachage en fonction du nombre de valeurs uniques est la suivante. Ces cotes sont basées sur une seule dimension pour un seul mois.

| Valeurs uniques | Odds |
| --- | --- |
| 1 000 | 0,01 % |
| 10 000 | 1 % |
| 50 000 | 26 % |
| 100 000 | 71 % |

{style="table-layout:auto"}

Tout comme le [paradoxe d’anniversaire](https://en.wikipedia.org/wiki/Birthday_problem), la probabilité de collisions de hachage augmente considérablement à mesure que le nombre de valeurs uniques augmente. Avec 1 million de valeurs uniques, il est probable qu’il existe au moins 100 collisions de hachage pour cette dimension.

## Réduire les collisions de hachage

La plupart des collisions de hachage se produisent avec deux valeurs peu courantes, qui n’ont aucun impact significatif sur les rapports. Même si un hachage entre en conflit avec une valeur commune et peu commune, le résultat est négligeable. Cependant, dans les rares cas où deux valeurs populaires subissent une collision de hachage, il est possible de voir clairement son effet. Adobe recommande ce qui suit pour réduire son effet dans les rapports :

* **Modifier la période** : les tableaux de hachage changent tous les mois. Si la période s’étend sur un autre mois, chaque valeur peut avoir des hachages différents qui ne sont pas en conflit.
* **Réduire le nombre de valeurs uniques** : vous pouvez ajuster votre implémentation ou utiliser les [Règles de traitement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) pour réduire le nombre de valeurs uniques qu’une dimension collecte. Par exemple, si votre dimension collecte une URL, vous pouvez supprimer les chaînes de requête ou le protocole.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
