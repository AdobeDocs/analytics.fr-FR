---
title: Présentation des classifications
description: Personnalisez le regroupement des éléments de dimension.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 62%

---

# Présentation des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que [Code de suivi](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) et [eVars](/help/components/dimensions/evar.md).

Adobe propose plusieurs méthodes de classification des données. Toutes les données de classification fonctionnent de la même manière dans les rapports. Vous pouvez combiner n’importe laquelle de ces méthodes qui correspond le mieux à votre organisation. Adobe recommande d’utiliser les **Jeux de classifications**.

* **Jeux de classifications** : créez et gérez des classifications et leurs règles dans une seule interface simplifiée.
* **Règles de classification** : créez des règles qui attribuent un élément de dimension donné à un élément de dimension de classification. Cette méthode de classification des données est préférable lorsqu’une dimension rencontre fréquemment de nouvelles valeurs uniques ou lorsqu’une classification manuelle est fréquente et fastidieuse.
* **Importateur de classifications** : exportez une feuille de calcul de modèle avec des éléments de dimension dans chaque ligne. Les colonnes représentent chaque classification d’une dimension. Cette méthode de classification des données est préférable lorsque tous les éléments de dimension sont connus et ne nécessite pas de mise à jour fréquente.

Une seule dimension peut comporter plusieurs dimensions de classification. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Chacun de ces attributs serait une dimension de classification distincte appartenant à la même dimension parent. L’augmentation de vos rapports avec ces attributs vous permet de disposer de rapports plus approfondis et plus complexes. Une fois qu’une dimension contient des données de classification, la dimension de classification est disponible dans les rapports contenant uniquement des éléments de dimension de classification. Tout élément de dimension parent qui ne contient pas de valeur de classification est regroupé sous [Non spécifié](/help/technotes/unspecified.md).
