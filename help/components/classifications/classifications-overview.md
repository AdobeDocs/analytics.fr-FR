---
title: Présentation des classifications
description: Personnalisez le regroupement des éléments de dimension.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 3701aa7a2a1528cd735c70fc7b061755a15b34a6
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 36%

---

# Présentation des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que [Code de suivi](/help/components/dimensions/tracking-code.md), [props](/help/components/dimensions/prop.md) et [eVars](/help/components/dimensions/evar.md).

Les **ensembles de classifications** sont la principale méthode de classification des données. **Règles de classification** et l’**importateur de classifications** sont des méthodes héritées permettant de classer les données. Ces méthodes sont obsolètes et ne seront plus accessibles après le 31 août 2026.

* **Ensembles de classifications** : créez et gérez des classifications dans une interface unique et simplifiée.
* **Règles de classification** (héritées) : créez des règles qui attribuent un élément de dimension donné à un élément de dimension de classification. Cette méthode de classification des données est préférable lorsqu’une dimension rencontre fréquemment de nouvelles valeurs uniques ou lorsque les classifications manuelles sont fréquentes et fastidieuses.
* **Importateur de classifications** (hérité) : exportez une feuille de calcul de modèle avec des éléments de dimension dans chaque ligne. Les colonnes représentent chaque classification d’une dimension. Cette méthode de classification des données est préférable lorsque tous les éléments de dimension sont connus et ne nécessite pas de mise à jour fréquente.

Une seule dimension peut comporter plusieurs dimensions de classification. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Chacun de ces attributs serait une dimension de classification distincte appartenant à la même dimension parent. Ajoutez ces attributs à vos rapports pour créer des rapports plus détaillés et plus complexes. Une fois qu’une dimension contient des données de classification, elle est disponible dans les rapports qui ne contiennent que des éléments correspondant à cette dimension. Tout élément de dimension parent qui ne contient pas de valeur de classification est regroupé sous [&#x200B; Non spécifié &#x200B;](/help/technotes/unspecified.md)
