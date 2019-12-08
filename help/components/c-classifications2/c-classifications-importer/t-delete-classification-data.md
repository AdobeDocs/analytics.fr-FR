---
description: Description de la procédure de suppression des données de classification.
subtopic: Classifications
title: Suppression des données de classification
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suppression des données de classification

Il est parfois nécessaire de supprimer les données de classification après leur téléchargement. Utilisez soit `~empty~` , `~deletekey~`, selon ce que vous souhaitez supprimer.

## Procédure de suppression des données de classification

La suppression des données de classification implique le chargement d’un fichier de classification contenant `~empty~` ou `~deletekey~` dans les cellules appropriées.

1. Cliquez sur **[!UICONTROL Admin]** &gt; **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Exportation Navigateur]**.
1. Sélectionnez la suite de rapports et le jeu de données duquel vous souhaitez supprimer des données de classification.
1. Configurez les éventuels paramètres facultatifs afin de filtrer les données que vous recherchez, puis cliquez sur **[!UICONTROL Exporter un fichier]**.
1. Une fois le fichier téléchargé, ouvrez-le et remplacez les valeurs de classification par `~empty~` ou `~deletekey~`.
1. Enregistrez le fichier dans un fichier texte délimité par des tabulations.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis rechargez le fichier de classification enregistré dans Adobe Analytics.

## Suppression d’une valeur de classification individuelle

Plusieurs classifications peuvent appartenir à la même variable. Par exemple, vous pouvez avoir 2 classifications différentes d’eVar1. Si vous souhaitez uniquement supprimer une seule valeur classée, remplacez la valeur de classification par `~empty~`. Par exemple :

| UGS de stock (eVar8) | Nom du stock | Catégorie de stock |
| --- | --- | --- |
| 857467 | Chandail à col V | Vêtements pour femmes |
| 948203 | Bracelet d'Ankle | Bijouterie |
| 174391 | Pantalon à cordon blanc | `~empty~` |

L'utilisation `~empty~` sous la classification Catégorie de stock conserve toujours les données de la classification Nom du stock. La `~empty~` valeur supprime uniquement les données de classification pour cette cellule.

## Suppression d’une ligne de classification entière

Utilisez `~deletekey~` dans n’importe quelle colonne pour supprimer la ligne de classification entière. Par exemple :

| UGS de stock (eVar8) | Nom du stock | Catégorie de stock |
| --- | --- | --- |
| 857467 | Chandail à col V | Vêtements pour femmes |
| 948203 | Bracelet d'Ankle | Bijouterie |
| 174391 | Pantalon à cordon blanc | `~deletekey~` |

L’utilisation `~deletekey~` sous la classification Catégorie de stock supprime toutes les données de classification pour la valeur de clé `174391`. C'est comme si la rangée n'avait jamais été classée.

## Pièges et conseils

* En cas d’utilisation `~deletekey~`, vous n’avez besoin que d’une ligne par ligne dans un fichier de classification.
* `~empty~` et doit `~deletekey~` correspondre *exactement* . Les espaces et les majuscules ne sont pas autorisés.
* Vous ne pouvez pas supprimer de valeurs dans la colonne de clé. Ces valeurs sont transmises directement à la variable et sont permanentes.
* Si vous supprimez une valeur de classification comportant des sous-classifications, ces sous-classifications sont également supprimées. Les classifications ne peuvent pas exister sans valeur de clé et le parent d’une sous-classification est sa propre valeur de clé.
* Il est possible de supprimer des données de classification sans modifier sa classification parent.
