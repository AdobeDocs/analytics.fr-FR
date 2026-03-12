---
title: Présentation des classifications
description: Personnalisez le regroupement des éléments de dimension.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: e4cfebf6a6932f66ac78ea2f7cea747ce558cf96
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 71%

---

# Présentation des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que le [Code de suivi](/help/components/dimensions/tracking-code.md), les [props](/help/components/dimensions/prop.md) et les [eVars](/help/components/dimensions/evar.md).

* Les **jeux de classifications** sont les principaux composants de classification des données. Les [jeux de classifications](/help/components/classifications/sets/overview.md) permettent de créer et de gérer des classifications dans une seule interface simplifiée.

* Les **classifications héritées** documentent les méthodes de classification héritées dans le but de classer les données. Ces méthodes seront abandonnées dans un avenir proche et ne seront plus accessibles.

   * [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) : créez des règles qui attribuent un élément de dimension donné à un élément de dimension de classification. Cette méthode de classification des données est préférable lorsqu’une dimension rencontre fréquemment de nouvelles valeurs uniques ou lorsque les classifications manuelles sont fréquentes et fastidieuses. Cette fonctionnalité sera abandonnée après le 28 février 2027.

   * [Importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) : exportez une feuille de calcul de modèle avec des éléments de dimension dans chaque ligne. Les colonnes représentent chaque classification d’une dimension. Cette méthode de classification des données est préférable lorsque tous les éléments de dimension sont connus et ne nécessitent pas de mises à jour fréquentes. Cette fonctionnalité sera abandonnée après le 31 août 2026. Avec l’obsolescence, vous ne pourrez plus importer de classifications à l’aide du FTP standard.

Une seule dimension peut comporter plusieurs dimensions de classification. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Chacun de ces attributs serait une dimension de classification distincte appartenant à la même dimension parent. Ajoutez ces attributs à vos rapports pour créer des rapports plus détaillés et plus complexes. Une fois qu’une dimension contient des données de classification, la dimension de classification est disponible dans les rapports contenant uniquement des éléments de dimension de classification. Tout élément de dimension parent qui ne contient pas de valeur de classification est regroupé sous [Non spécifié](/help/technotes/unspecified.md).
