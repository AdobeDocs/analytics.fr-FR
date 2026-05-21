---
title: Présentation des classifications
description: Personnalisez le regroupement des éléments de dimension.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 84%

---

# Présentation des classifications

Une classification est une méthode permettant de catégoriser des données de variables Analytics, puis de les afficher de différentes manières lors de la création de rapports. Vous établissez une relation entre une valeur de variable et les métadonnées associées à cette valeur. Les classifications peuvent être utilisées sur la plupart des dimensions personnalisées, telles que le [Code de suivi](/help/components/dimensions/tracking-code.md), les [props](/help/components/dimensions/prop.md) et les [eVars](/help/components/dimensions/evar.md).

* Les **jeux de classifications** sont les principaux composants de classification des données. Les [jeux de classifications](/help/components/classifications/sets/overview.md) permettent de créer et de gérer des classifications dans une seule interface simplifiée.

* Les **classifications héritées** documentent les méthodes de classification héritées dans le but de classer les données. Ces méthodes seront abandonnées dans un avenir proche et ne seront plus accessibles.

   * [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) : créez des règles qui attribuent un élément de dimension donné à un élément de dimension de classification. Cette méthode de classification des données est préférable lorsqu’une dimension rencontre fréquemment de nouvelles valeurs uniques ou lorsque des classifications manuelles seraient fréquentes et fastidieuses. Cette fonctionnalité sera abandonnée après le 28 février 2027.

   * [Importateur de classifications](/help/components/classifications/importer/c-working-with-saint.md) : exportez une feuille de calcul de modèle avec des éléments de dimension dans chaque ligne. Les colonnes représentent chaque classification d’une dimension. Cette méthode de classification des données est préférable lorsque tous les éléments de dimension sont connus et ne nécessite pas de mise à jour fréquente. Cette fonctionnalité sera abandonnée après le 31 août 2026. Avec l’obsolescence, vous ne pourrez plus importer de classifications à l’aide du FTP standard.

Une seule dimension peut comporter plusieurs dimensions de classification. Par exemple, il est possible de classer les [!UICONTROL ID de produits] avec des attributs de produit supplémentaires, tels que le nom, la couleur, la taille, la description et la référence du produit. Chacun de ces attributs serait une dimension de classification distincte appartenant à la même dimension parent. Ajoutez ces attributs à vos rapports pour créer des rapports plus détaillés et plus complexes. Une fois qu’une dimension contient des données de classification, la dimension de classification est disponible dans les rapports contenant uniquement des éléments de dimension de classification. Tout élément de dimension parent qui ne contient pas de valeur de classification est regroupé sous [Non spécifié](/help/technotes/unspecified.md).
