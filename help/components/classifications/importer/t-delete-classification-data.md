---
description: Description de la procédure de suppression des données de classification.
title: Suppression des données de classification
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
TQID: https://experienceleague.adobe.com/NZhXTXSwpA-E-6JaGRInMf3TMwHp5A1uMSjaAU1whts
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 96%

---

# Suppression des données de classification

{{classification-importer-deprecation}}

Il est parfois nécessaire de supprimer les données de classification une fois chargées. Utilisez soit `~empty~` ou `~deletekey~`, en fonction de ce que vous souhaitez supprimer.

## Procédure de suppression des données de classification

La suppression des données de classification implique de charger un fichier de classification contenant `~empty~` ou `~deletekey~` dans les cellules appropriées.

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
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
* Si vous supprimez une valeur de classification qui comporte des sous-classifications, ces sous-classifications sont également supprimées. Les classifications ne peuvent pas exister sans valeur de clé et le parent d’une sous-classification est sa propre valeur de clé.
* Il est possible de supprimer des données de classification sans modifier sa classification parente.
