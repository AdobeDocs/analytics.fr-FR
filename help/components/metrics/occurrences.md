---
title: Occurrences
description: Nombre d’accès pour lesquels une variable a été définie ou conservée.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 57%

---

# Occurrences

La [mesure](overview.md) « Occurrences » indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée. Lorsque vous faites glisser une dimension de Workspace vers un canevas vierge, Adobe applique automatiquement cette mesure au projet.

## Méthode de calcul de cette mesure

Sur tous les accès d’une suite de rapports, incluez les accès pour lesquels un élément de dimension est défini ou conservé. Certaines dimensions, telles que les [eVars](../dimensions/evar.md), persistent au-delà de l’accès pour lequel elles ont été définies. Cette mesure comptabilise à la fois les valeurs initiales et les valeurs conservées.

## Comparaison avec des mesures similaires

* **Occurrences par rapport aux [Instances](instances.md)** : Occurrences comptabilise les accès où un élément de dimension a été défini ou conservé. Les instances n’incluent pas les accès pour lesquels un élément de dimension persiste.
* **Occurrences par rapport aux [Pages vues](page-views.md)** : la mesure Occurrences inclut tous les types d’accès, y compris les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)), les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) et les données à partir des[sources de données](/help/import/data-sources/overview.md) récapitulatives. La mesure Pages vues inclut uniquement les appels de suivi de pages vues, à l’exclusion des appels de suivi de liens et des sources de données récapitulatives.

## Persistance

La persistance permet à une valeur de dimension donnée de se relier à une mesure au-delà de l’événement sur lequel elle est définie. Il utilise une combinaison d’attribution et d’expiration. L’affectation vous permet de déterminer la valeur conservée lorsque plusieurs éléments de dimension peuvent persister à la fois dans une seule colonne. L’expiration vous permet de déterminer la durée pendant laquelle un élément de dimension persiste au-delà de l’événement sur lequel il est défini.

La persistance n’est disponible que sur les dimensions et est rétroactive aux données auxquelles elle est appliquée. Il s’agit d’une transformation immédiate des données qui se produit avant l’application du filtrage ou d’autres opérations d’analyse. Si la persistance n’est pas activée, la dimension se rapporte uniquement aux mesures qui existent dans le même événement.