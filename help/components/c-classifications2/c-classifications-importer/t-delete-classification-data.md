---
description: Description de la procédure de suppression des données de classification.
subtopic: Classifications
title: Suppression des données de classification
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suppression des données de classification

Il est parfois nécessaire de supprimer les données de classification une fois chargées. Utilisez soit `~empty~` ou `~deletekey~`, en fonction de ce que vous souhaitez supprimer.

## Procédure de suppression des données de classification

La suppression des données de classification implique de charger un fichier de classification contenant `~empty~` ou `~deletekey~` dans les cellules appropriées.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Exportation Navigateur]**.
1. Sélectionnez la suite de rapports et le jeu de données duquel vous souhaitez supprimer des données de classification.
1. Configurez les éventuels paramètres facultatifs afin de filtrer les données que vous recherchez, puis cliquez sur **[!UICONTROL Exporter un fichier]**.
1. Une fois le fichier téléchargé, ouvrez-le et remplacez n’importe quelle valeur de classification par `~empty~` ou `~deletekey~`.
1. Enregistrez le fichier en tant que fichier texte délimité par des tabulations.
1. Cliquez sur **[!UICONTROL Importer un fichier]**, puis chargez à nouveau le fichier de classification enregistré dans Adobe Analytics.

## Suppression d’une valeur de classification individuelle

Plusieurs classifications peuvent appartenir à la même variable. Par exemple, vous pouvez avoir 2 classifications différentes d’un eVar1. Si vous souhaitez supprimer une seule valeur de classification, remplacez-la par `~empty~`. Par exemple :

| UGS de l’inventaire (eVar8) | Nom de l’inventaire | Catégorie de l’inventaire |
| --- | --- | --- |
| 857467 | Pull avec col en V | Vêtement pour femmes |
| 948203 | Bracelet de cheville | Bijoux |
| 174391 | Pantalon en velours côtelé blanc | `~empty~` |

L’utilisation de `~empty~` sous la classification Catégorie de l’inventaire conserve toujours les données de la classification Nom de l’inventaire. La valeur `~empty~` supprime uniquement les données de classification pour cette cellule.

## Suppression d’une ligne de classification entière

Utilisez `~deletekey~` dans n’importe quelle colonne pour supprimer la ligne de classification entière. Par exemple :

| UGS de l’inventaire (eVar8) | Nom de l’inventaire | Catégorie de l’inventaire |
| --- | --- | --- |
| 857467 | Pull avec col en V | Vêtement pour femmes |
| 948203 | Bracelet de cheville | Bijoux |
| 174391 | Pantalon en velours côtelé blanc | `~deletekey~` |

L’utilisation de `~deletekey~` sous la classification Catégorie de l’inventaire supprime toutes les données de classification pour la valeur de clé `174391`. C’est comme si la ligne n’avait jamais été classée.

## Pièges et conseils

* Si vous utilisez `~deletekey~`, vous n’avez besoin de l’utiliser qu’une fois par ligne dans un fichier de classification.
* `~empty~` et `~deletekey~` doivent être écrits *exactement* de la même façon. Les espaces et les majuscules ne sont pas autorisées.
* Vous ne pouvez pas supprimer de valeurs dans la colonne de clé. Ces valeurs sont transmises directement à la variable et sont permanentes.
* Si vous supprimez une valeur de classification qui comporte des sous-classifications, ces dernières sont également supprimées. Les classifications ne peuvent pas exister sans valeur de clé et le parent d’une sous-classification est sa propre valeur de clé.
* Il est possible de supprimer des données de classification sans modifier sa classification parente.
