---
description: Interaction avec des lignes statiques dans les tableaux.
seo-description: Interaction avec des lignes statiques dans les tableaux.
seo-title: Lignes statiques/dynamiques
title: Lignes statiques/dynamiques
uuid: caf 033 ef-d 252-4 f 8 a -802 e -7 edbbac 5 c 8 c 0
translation-type: tm+mt
source-git-commit: a121851d3f96aee243aaffd2fde24c98d4fc55e1

---


# Lignes statiques/dynamiques

Quand vous faites glisser une dimension sur un tableau d’Analysis Workspace, des lignes « dynamiques » sont générées, ce qui signifie que tous les éléments qui correspondent à la dimension, pour une mesure donnée, sont reportés dans le tableau.

Par exemple, si vous faites glisser la dimension Navigateur dans le tableau, tous les éléments de dimension (navigateur Android, Safari mobile, Firefox, etc.) sont reportés dans le tableau de manière dynamique.

En comparaison, chaque fois que vous sélectionnez et faites glisser manuellement une mesure, un segment, une classe de données ou une dimension individuelle dans un tableau, il en résulte une ligne ou une liste codée en dur ou « statique ». Vous pouvez maintenant interagir sur une ligne statique de différentes façons :

* Cliquez sur l’icône Aperçu dans une ligne statique pour prévisualiser les segments, les mesures et les plages de dates.
* Cliquez sur l’icône X pour supprimer cette ligne du tableau.
* Limitez le nombre de lignes affichées et activez la pagination.
* Ajoutez des éléments de dimension mixtes. Par exemple, ajoutez un élément issu d’une dimension de navigateur et un autre élément issu d’une dimension de produit.

   En voici une illustration :

   ![](assets/static_rows.png)

En outre, (uniquement) lorsque vous êtes en mode de ligne statique, vous pouvez maintenant modifier le mode de calcul des totaux de colonne. Il vous suffit de cliquer sur l’icône d’engrenage et de permuter entre ces deux options :

![](assets/column-totals.png)

| Option | Description |
|---|---|
| (Par défaut) Calculez les totaux en additionnant les valeurs actuellement dans chaque colonne. | Cette option calcule seulement les lignes figurant actuellement dans le tableau. (Calcul côté client) |
| Calculez les totaux d’après toutes les lignes pour chaque mesure. | Cette option comprend tous les éléments de cette dimension, même ceux qui ne sont pas répertoriés dans le tableau. (Calcul côté serveur) |

