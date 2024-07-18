---
title: Collisions de hachage
description: Décrit ce qu’est une collision de hachage et de quelle façon elle se manifeste.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 06f61fa7b39faacea89149650e378c8b8863ac4f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 6%

---

# Collisions de hachage

Les Dimensions dans Adobe Analytics collectent des valeurs de chaîne. Parfois, ces chaînes comportent des centaines de caractères, tandis que d’autres fois elles sont courtes. Pour améliorer les performances, ces valeurs de chaîne ne sont pas utilisées directement dans le traitement. À la place, un hachage est calculé pour chaque valeur afin de uniformiser la taille de toutes les valeurs. Tous les rapports s’exécutent sur ces valeurs hachées, ce qui augmente considérablement leurs performances.

Pour la plupart des champs, la chaîne est d’abord convertie en minuscules. La conversion en minuscules réduit le nombre de valeurs uniques. Les valeurs sont hachées sur une base mensuelle ; le cas d’une valeur donnée utilise la première valeur affichée chaque mois. D’un mois à l’autre, il est possible que deux valeurs de variable uniques soient hachées à la même valeur. On parle alors de *collision de hachage*.

Les collisions de hachage peuvent se manifester dans les rapports comme suit :

* Si vous affichez un rapport au fil du temps et constatez un pic inattendu, il est possible que plusieurs valeurs uniques de cette variable utilisent le même hachage.
* Si vous utilisez un segment et que vous voyez une valeur inattendue, il est possible que l’élément de dimension inattendu utilise le même hachage qu’un autre élément de dimension correspondant à votre segment.

## Impacts d’une collision de hachage

Adobe Analytics utilise des hachages 32 bits pour la plupart des dimensions, ce qui signifie qu’il existe 2<sup>32</sup> combinaisons de hachage possibles (environ 4,3 milliards). Un nouveau tableau de hachage est créé chaque mois pour chaque dimension. Les chances approximatives de rencontrer une collision de hachage en fonction du nombre de valeurs uniques sont les suivantes. Ces probabilités sont basées sur une seule dimension pour un seul mois.

| Valeurs uniques | Odd |
| --- | --- |
| 1,000 | 0,01 % |
| 10 000 | 1 % |
| 50 000 | 26 % |
| 100 000 | 71 % |

{style="table-layout:auto"}

Tout comme le [paradoxe d&#39;anniversaire](https://en.wikipedia.org/wiki/Birthday_problem), la probabilité de collisions de hachage augmente de manière drastique à mesure que le nombre de valeurs uniques augmente. À 1 million de valeurs uniques, il est probable qu’il existe au moins 100 collisions de hachage pour cette dimension.

## Atténuation des collisions de hachage

La plupart des collisions de hachage se produisent avec deux valeurs peu courantes, qui n’ont aucun impact significatif sur les rapports. Même si un hachage entre en conflit avec une valeur commune et rare, le résultat est négligeable. Cependant, dans de rares cas où deux valeurs populaires rencontrent une collision de hachage, il est possible de voir clairement son effet. Adobe recommande ce qui suit pour réduire son effet dans les rapports :

* **Modifier la période** : les tables de hachage changent chaque mois. Le fait de modifier la période pour qu’elle s’étende sur un autre mois peut donner à chaque valeur différents hachages qui ne sont pas en conflit.
* **Réduire le nombre de valeurs uniques** : vous pouvez ajuster votre mise en oeuvre ou utiliser les [règles de traitement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) pour réduire le nombre de valeurs uniques collectées par une dimension. Par exemple, si votre dimension collecte une URL, vous pouvez supprimer des chaînes de requête ou du protocole.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
