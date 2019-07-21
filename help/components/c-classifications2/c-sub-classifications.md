---
description: Adobe Analytics prend en charge les modèles de classifications à niveau unique et à plusieurs niveaux. Une hiérarchie de classification vous permet d’appliquer une classification à une autre classification.
seo-description: Adobe Analytics prend en charge les modèles de classifications à niveau unique et à plusieurs niveaux. Une hiérarchie de classification vous permet d’appliquer une classification à une autre classification.
seo-title: A propos des sous-classifications
solution: Analytics
subtopic: Gestionnaire
title: A propos des sous-classifications
topic: Outils d’administration
uuid: 48 bd 7 fc 1-54 a 1-40 ef-bc 55-395338522 f 2 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# A propos des sous-classifications

Adobe Analytics prend en charge les modèles de classifications à niveau unique et à plusieurs niveaux. Une hiérarchie de classification vous permet d’appliquer une classification à une autre classification.

>[!NOTE]
>
>La sous-classification fait référence à la possibilité de créer des classifications de classifications. Toutefois, il ne s’agit pas de la même [!UICONTROL hiérarchie de classification] que celle utilisée pour créer des rapports de [!UICONTROL hiérarchie]. For more information about Classification hierarchies, see [Classification Hierarchies](classification-hierarchies.md).

<!-- 

<p>Removed sub-classifications in rule builder. Preserve subclass files in project for future reference. </p>

 -->

<!-- 

c_single-level_classifications.xml

 -->

Par exemple :

![](assets/single-level-popup-C.png)

Chaque classification de ce modèle est indépendante et correspond à un nouveau sous-rapport pour la variable de création de rapports sélectionnée. De plus, chaque classification constitue une colonne de données dans le fichier de données avec son nom comme en-tête de colonne. Par exemple :

| CLÉ | PROPRIÉTÉ 1 | PROPRIÉTÉ 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

Pour plus d’informations sur le fichier de données, consultez [Fichiers de données de classification](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

<!-- 

c_multiple-level_classifications.xml

 -->

Les classifications à plusieurs niveaux comprennent les classifications parentes et filles. Par exemple :

![](assets/Multi-Level-Class-popup.png)

**Classifications parentes** : une classification parente est une classification associée à une classification fille. Une classification peut être une classification parente et fille. Les classifications parentes de niveau supérieur correspondent à des classifications à niveau unique (Voir [Classifications à niveau unique](../../components/c-classifications2/c-sub-classifications.md#concept_6B909B54221F4A9BAEA8E30594F06C49)).

**Classifications enfants** : une classification enfant est une classification qui possède une autre classification en tant que parent à la place de la variable. Les classifications filles fournissent des informations supplémentaires sur leur classification parente. Par exemple, une classification de [!UICONTROL campagne] peut posséder une classification fille de propriétaire de campagne. Les classifications [!UICONTROL numériques] fonctionnent également comme des mesures dans les rapports de classification.

Chaque classification, parent ou enfant, constitue une colonne de données dans le fichier de données. L’en-tête de colonne d’une classification fille utilise le format d’affectation de nom suivant :

`<parent_name>^<child_name>`

For more information about the data file format, see [Classification Data Files](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

Par exemple :

| CLÉ | PROPRIÉTÉ 1 | Propriété 1 &amp; amp ; Chapeau ; Propriété 1-1 | Propriété 1 &amp; amp ; Chapeau ; Propriété 1-2 | Propriété 2 |
|---|---|---|---|---|
| 123 | ABC | Vert | Petit | A12B |
| 456 | DEF | Rouge | Grand | C3D4 |

Bien que le modèle de fichier d’une classification à plusieurs niveaux soit plus complexe, l’avantage des classifications à plusieurs niveaux réside dans le fait que les différents niveaux peuvent être transférés sous forme de fichiers séparés. Il est possible d’utiliser cette approche pour réduire au minimum la quantité de données à charger périodiquement (chaque jour, chaque semaine, etc.) en regroupant les données par niveaux de classification qui changent au fil du temps et ceux qui ne changent pas.

>[!NOTE]
>
>If the [!UICONTROL Key] column in a data file is blank, Adobe automatically generates unique keys for each data row. Pour éviter toute corruption de fichier lors du chargement d’un fichier de données avec des données de classification de deuxième niveau ou de niveau supérieur, ajoutez un astérisque (*) à chaque ligne de la colonne [!UICONTROL Clé].

Pour plus d’informations sur la résolution des problèmes, reportez-vous à la section [Problèmes de téléchargement de classifications courants](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-common-saint-upload-issues).

<!-- 

c_classifications_example.xml

 -->

![](assets/sample-product-classifications.png)

>[!NOTE]
Les données de classification de produit sont limitées aux attributs de données directement liés au produit. et non à la manière dont les produits sont classés ou vendus sur le site web. Les éléments de données tels que les catégories de vente, les nœuds de navigateur du site ou les articles en vente ne sont pas des données de classification de produit. Ces éléments sont capturés dans des variables de conversion de rapport.

Lors du téléchargement de fichiers de données pour cette classification de produit, vous pouvez télécharger les données de classification sous la forme d’un ou de plusieurs fichiers (vois ci-dessous). En séparant le code couleur du fichier 1 et le nom de la couleur dans le fichier 2, les informations concernant le nom de la couleur (qui peuvent n’occuper que quelques lignes) ne doivent être mises à jour que lors de la création de nouveaux codes couleur. Cela élimine le nom de la couleur (CODE &amp; amp ; Chapeau ; COLOR) du fichier 1 qui a été mis à jour plus souvent et qui réduit la taille et la complexité du fichier lors de la création du fichier de données.

## Classification de produit - fichier unique {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| CLÉ | NOM DU PRODUIT | DÉTAILS DU PRODUIT | SEXE | TAILLE | CODE | CODE &amp; amp ; Chapeau ; COULEUR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-MC | Polo homme, manches courtes (M,01) | M | M | 01 | Gris |
| 410390014 | Polo-MC | Polo homme, manches courtes (L,03) | M | L | 03 | Bruyère |
| 410390015 | Polo-ML | Polo femme, manches longues (S,23) | F | S | 23 | Bleu-vert |

## Classification de produit - plusieurs fichiers (fichier 1) {#section_A99F7D0F145540069BA4EEC0597FF13F}

| CLÉ | NOM DU PRODUIT | DÉTAILS DU PRODUIT | SEXE | TAILLE | CODE |
|---|---|---|---|---|---|
| 410390013 | Polo-MC | Polo homme, manches courtes (M,01) | M | M | 01 |
| 410390014 | Polo-MC | Polo homme, manches courtes (L,03) | M | L | 03 |
| 410390015 | Polo-ML | Polo femme, manches longues (S,23) | F | S | 23 |

## Classification de produit - plusieurs fichiers (fichier 2) {#section_19ED95C33B174A9687E81714568D56A3}

| CLÉ | CODE | CODE &amp; amp ; Chapeau ; COULEUR |
|---|---|---|
| * | 01 | Gris |
| * | 03 | Bruyère |
| * | 23 | Bleu-vert |
