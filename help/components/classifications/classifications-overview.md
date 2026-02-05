---
title: Présentation des classifications
description: Personnalisez le regroupement des éléments de dimension.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 1e209d4313c3d9d67f15a0c3a0939ceeb7a1ed31
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Présentation des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que le [Code de suivi](/help/components/dimensions/tracking-code.md), les [props](/help/components/dimensions/prop.md) et les [eVars](/help/components/dimensions/evar.md).

* Les **jeux de classifications** sont les principaux composants de classification des données. Les [jeux de classifications](/help/components/classifications/sets/overview.md) permettent de créer et de gérer des classifications dans une seule interface simplifiée.

* Les **classifications héritées** documentent les méthodes de classification héritées dans le but de classer les données. Ces méthodes sont obsolètes et ne seront plus accessibles après le 31 août 2026.

   * [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) : créez des règles qui attribuent un élément de dimension donné à un élément de dimension de classification. Cette méthode de classification des données est préférable lorsqu’une dimension rencontre fréquemment de nouvelles valeurs uniques ou lorsque des classifications manuelles seraient fréquentes et fastidieuses.
   * [Importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) : exportez une feuille de calcul de modèle avec des éléments de dimension dans chaque ligne. Les colonnes représentent chaque classification d’une dimension. Cette méthode de classification des données est préférable lorsque tous les éléments de dimension sont connus et ne nécessite pas de mise à jour fréquente.

Une seule dimension peut comporter plusieurs dimensions de classification. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Chacun de ces attributs serait une dimension de classification distincte appartenant à la même dimension parent. Ajoutez ces attributs à vos rapports pour créer des rapports plus détaillés et plus complexes. Une fois qu’une dimension contient des données de classification, la dimension de classification est disponible dans les rapports contenant uniquement des éléments de dimension de classification. Tout élément de dimension parent qui ne contient pas de valeur de classification est regroupé sous [Non spécifié](/help/technotes/unspecified.md).
