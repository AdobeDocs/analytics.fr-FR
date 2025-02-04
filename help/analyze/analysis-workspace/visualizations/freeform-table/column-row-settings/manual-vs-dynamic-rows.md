---
title: Éléments de dimension dynamiques ou statiques dans les tableaux à structure libre
description: Interaction avec des éléments de dimension dynamiques et statiques dans des tableaux.
feature: Freeform Tables
role: User, Admin
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 44%

---

# Éléments de dimension dynamiques et statiques

Dans les tableaux à structure libre, les lignes et les colonnes peuvent contenir diverses valeurs de composant. Ces valeurs peuvent être dynamiques (elles changent au fil du temps) ou statiques (elles ne changent pas au fil du temps), selon l’analyse que vous souhaitez créer.

## Éléments de dimension dynamiques

Les éléments de dimension dynamiques changent au fil du temps et dépendent de la mesure triée dans le tableau à structure libre. Les éléments de dimension dynamiques sont recommandés lorsque vous souhaitez analyser les éléments principaux d’une période donnée.

Lorsque vous déposez une dimension dans un tableau à structure libre, des lignes dynamiques sont renvoyées. Les lignes dynamiques représentent les principaux éléments qui correspondent à la dimension pour une mesure et une période données. Vous pouvez également déposer une dimension dans des colonnes de tableau à structure libre et la dimension se développe automatiquement dans les 5 premiers éléments de dimension.

Par exemple, lorsque vous faites glisser la dimension Type de navigateur dans le tableau, les principaux éléments de dimension Type de navigateur (par exemple, Microsoft, Apple, Google, etc.) reviennent dynamiquement sur les lignes du tableau. Si vous les déposez dans une colonne, les 5 premiers éléments de dimension Type de navigateur sont dynamiquement renvoyés.

Les éléments de dimension dynamiques comportent l’option de filtre de ligne ![Filtrer](/help/assets/icons/Filter.svg) et un ![Fermer](/help/assets/icons/Close.svg), et ne comportent **pas** de verrou ![LockClosed](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Lorsque vous cliquez sur ![Fermer](/help/assets/icons/Close.svg) en regard d’un élément de dimension dynamique, un filtre est automatiquement appliqué. Pour plus d’informations sur l’application de filtres aux tableaux, voir [Filtrer et trier des tableaux](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Tableau à structure libre mettant en surbrillance l’icône de filtre.](assets/dynamic-items.png)

## Éléments de dimension statiques

Les éléments de dimension statiques ne changent pas avec le temps. Il s’agit de composants fixes toujours renvoyés dans un tableau à structure libre. Les éléments de dimension statiques sont recommandés lorsque vous souhaitez toujours analyser le même élément, qu’il s’agisse de campagnes spécifiques ou de jours précis de la semaine.

Chaque fois que vous sélectionnez et déposez manuellement des valeurs de composant spécifiques (dimension, mesure, filtre, période) dans un tableau, le résultat est une liste statique de lignes ou de colonnes.

Par exemple, lorsque vous faites glisser des éléments Type de navigateur spécifiques tels que Microsoft et Apple, ces deux éléments spécifiques sont toujours extraits dans le tableau.

Les éléments de dimension statiques peuvent également être créés si vous choisissez de sélectionner **[!UICONTROL Afficher uniquement les lignes sélectionnées]** dans le menu contextuel des lignes sélectionnées.

Les éléments de dimension statiques ne disposent **pas** de l’option de filtre de ligne. Au lieu de cela, un ![LockClosed](/help/assets/icons/LockClosed.svg) et un ![Close](/help/assets/icons/Close.svg) sont présents sur chaque élément. Sélectionnez ![Fermer](/help/assets/icons/Close.svg) pour supprimer cet élément de dimension du tableau.

![Tableau à structure libre présentant le type de navigateur et la ligne Microsoft avec une icône de verrouillage. Remarque : cet élément de dimension est statique et ne change pas avec le temps.](assets/static-items.png)

## Éléments de dimension mixtes

Vous pouvez ajouter des éléments de dimension de différentes dimensions au même tableau. L’en-tête de ligne indique **[!UICONTROL Dimensions mixtes]** dans ces cas. Ces éléments de dimension sont statiques. Par exemple, l’ajout d’éléments de dimension spécifiques de la dimension Groupe de navigateurs et d’autres éléments de dimension de la dimension Nom du navigateur .

![Tableau à structure libre mettant en surbrillance la colonne Dimensions mixtes.](assets/mixed-dimensions.png)

## Lignes totales à structure libre

Les lignes dynamiques et statiques se comportent différemment dans la ligne de total à structure libre. Par défaut :

* Les lignes dynamiques sont additionnées côté serveur et permettent de dédupliquer les mesures telles que les sessions ou les personnes.
* Les lignes statiques sont additionnées côté client et ne dédupliquent **pas** les mesures. Pour calculer la ligne de total côté serveur, définissez le paramètre des lignes sur **Afficher le total général**. [En savoir plus](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Réorganiser les lignes statiques](https://video.tv.adobe.com/v/31319?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


