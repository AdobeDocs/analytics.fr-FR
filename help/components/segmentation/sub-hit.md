---
title: Analyse des sous-accès
description: Découvrez comment l’analyse des sous-accès vous permet de filtrer les produits individuels d’un accès dans Adobe Analytics, en éliminant le fond perdu d’attribution dans les rapports de produit.
feature: Segmentation
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: dbbf0fc296c6ef750f7027730f02ccb8b33e83c6
workflow-type: tm+mt
source-wordcount: 808
ht-degree: 0%

---

# Analyse des sous-accès

L’analyse des sous-accès vous permet d’analyser les données de produit à un niveau plus granulaire que le niveau d’accès. Au lieu de filtrer les accès entiers, vous pouvez segmenter les produits individuels dans les accès. Par exemple, segmenter une catégorie de produits spécifique sans inclure tous les autres produits achetés dans la même commande.

Dans Adobe Analytics, la variable [Products](/help/components/dimensions/product.md) peut capturer plusieurs produits sur un seul accès. Sans analyse des sous-accès, la segmentation sur un attribut de produit renvoie tous les accès où n’importe quel produit d’un accès correspond à l’attribut de produit. Il en résulte une attribution incorrecte et des mesures de revenus exagérées. L’analyse des sous-accès étend le filtre à des lignes de produits individuelles au sein d’un accès et résout ces problèmes.

Dans l’analyse de sous-accès, la logique d’exclusion se comporte différemment de l’exclusion au niveau de l’accès standard par rapport à la variable Products. Lorsque vous excluez des attributs de produit dans le conteneur [!UICONTROL Product], le segment renvoie des accès qui **contiennent des produits** mais ne correspondent pas à vos critères d’exclusion. Le segment ne renvoie pas d’accès sans produits du tout.

## Exemple

Vous souhaitez uniquement mesurer le chiffre d’affaires en ligne de la catégorie Hommes . Sans analyse des sous-accès, l’application d’un segment pour les hommes inclut le chiffre d’affaires de chaque produit sur n’importe quelle commande (accès) contenant au moins un produit de la catégorie Hommes. Avec l’analyse des sous-accès, vous définissez la portée du filtre au niveau du produit et renvoyez uniquement les recettes pour les produits de la catégorie Hommes .

Vous souhaitez également mesurer les recettes en ligne de toutes les autres catégories, à l’exception de la catégorie Hommes.

>[!BEGINTABS]

>[!TAB  Analyse des accès ]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Inclure]** le **[!UICONTROL Dimension]** **[!UICONTROL Vente au détail : catégorie de produits de mode]** **[!UICONTROL égal]** **[!UICONTROL Hommes]** sur le conteneur **[!UICONTROL Hits]**.

![Panneau présentant la segmentation au niveau de l’accès pour la catégorie de produits Hommes](./assets/product-category-segmentation-hits.png)

Par conséquent, toutes les commandes contenant au moins une **[!UICONTROL Hommes]** **[!UICONTROL Vente au détail : catégorie de produits de mode]** sont prises en compte, et le chiffre d’affaires des autres produits de ces commandes est inclus dans la mesure **[!UICONTROL Chiffre d’affaires en ligne]**.
Lorsque vous éditez des catégories, toutes les autres valeurs de **[!UICONTROL Vente au détail : Catégorie de produits de mode]** sont générées dans le cadre d&#39;une commande qui incluait un produit avec le **[!UICONTROL Hommes]** **[!UICONTROL Vente au détail : Catégorie de produits de mode]**.

>[!TAB  Analyse des sous-accès ]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Inclure]** le **[!UICONTROL Dimension]** **[!UICONTROL Vente au détail : catégorie de produits de mode]** **[!UICONTROL égal]** **[!UICONTROL Hommes]** sur le conteneur **[!UICONTROL Products]**.

![Panneau présentant la segmentation au niveau des sous-accès pour la catégorie de produits Hommes](./assets/product-category-segmentation-sub-hits.png)

Par conséquent, toutes les commandes contenant au moins une **[!UICONTROL Hommes]** **[!UICONTROL Vente au détail : Catégorie de produits de mode]** sont prises en compte et seuls les produits appartenant à la **[!UICONTROL Hommes]** **[!UICONTROL Vente au détail : Catégorie de produits de mode]** sont inclus dans la mesure **[!UICONTROL Chiffre d’affaires en ligne]**.
Lorsque vous créez des rapports sur les catégories, seule la **[!UICONTROL Hommes]** **[!UICONTROL Vente au détail : Catégorie de produits de mode]** est indiquée.

>[!TAB Analyse des sous-accès (exclure)]

Dans le créateur de segments ou dans le cadre d’un **[!UICONTROL segment rapide]**, vous spécifiez pour **[!UICONTROL Exclure]** le conteneur **[!UICONTROL Dimension]** **[!UICONTROL Retail : Fashion Product Category]** **[!UICONTROL equals]** **[!UICONTROL Men]** sur le **[!UICONTROL Products]**.

![Panneau présentant la segmentation au niveau des sous-accès pour exclure la catégorie de produits Hommes](./assets/product-category-segmentation-sub-hits-exclude.png)

Pour exclure au niveau du produit, les accès contenant au moins un produit sont inclus, puis l’exclusion au niveau des sous-accès est appliquée dans cette portée. Cette exclusion diffère de l’exclusion au niveau de l’accès, qui exclut l’accès entier.

>[!ENDTABS]

Dans Adobe Analytics, l’analyse des sous-accès s’applique spécifiquement à la variable **[!UICONTROL Products]**. La variable **[!UICONTROL Products]** est le seul objet à plusieurs valeurs dans Adobe Analytics qui prend en charge l’analyse des sous-accès.


>[!WARNING]
>
>Les sections suivantes vont être déplacées vers leurs articles pertinents (sur le créateur de segments, le segment rapide, l’histogramme, etc.) lorsque cette fonctionnalité sera disponible. Et ces articles se référeront ensuite à cet article pour référence sur ce qu’est l’analyse des sous-accès. Cette action n’est actuellement pas effectuée afin de ne pas perturber les clients lorsque la fonctionnalité n’est pas disponible.

## Auto-inférence du conteneur

Lorsque vous faites glisser une dimension ou une mesure de produit dans le créateur de segments ou le panneau de segments rapides, le système sélectionne automatiquement le conteneur **[!UICONTROL Produit]** et n’utilise pas le conteneur **[!UICONTROL Accès]** par défaut. Ce comportement limite le segment à des produits individuels plutôt qu’à l’accès complet.

## Comportement de conteneur mixte

Si vous faites glisser les composants au niveau du produit et au niveau de l’accès dans une seule règle de segment, le système utilise le conteneur **[!UICONTROL Accès]**, qui est le conteneur partagé le plus élevé (le moins granulaire). Si tous les composants qui font partie d’une règle de segment sont au niveau du produit, le conteneur **[!UICONTROL Product]** est utilisé.

## Filtres de produit dans le rail de gauche

Le créateur de segments comprend une nouvelle option de filtre dans le rail de gauche pour afficher uniquement les dimensions et mesures des produits. Cela facilite la recherche de composants au niveau du produit lors de la création de segments de sous-accès.

>[!NOTE]
>
>Cette option de filtre est disponible uniquement dans le créateur de segments. Il n’est pas disponible dans d’autres rails gauche tels que les panneaux ou les visualisations d’Analysis Workspace.

## Visualisation sous forme d’histogramme

La visualisation Histogramme comprend un nouveau menu déroulant de conteneur de sous-accès. Vous pouvez ainsi regrouper les valeurs de mesure au niveau du produit. Par exemple, en comptant les occurrences de produit par commande plutôt que par accès.

L’histogramme est la seule visualisation qui nécessite une sélection de conteneur de sous-accès. Tous les autres panneaux et visualisations fonctionnent avec les données d’analyse des sous-accès sans configuration supplémentaire.

