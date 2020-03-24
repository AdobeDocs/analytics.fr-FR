---
description: Vous ne pouvez pas combiner le Créateur de règles de classification avec des sous-classifications.
title: Sous-classifications et Créateur de règles
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# Sous-classifications et Créateur de règles

Vous pouvez combiner le Créateur de règles de classification avec des sous-classifications si vous vous assurez que chaque sous-classification possède une valeur parent.

La combinaison du Créateur de règles de classification et des sous-classifications peut simplifier la gestion des classifications et réduire le nombre de règles requises. Vous pouvez le faire si votre code de suivi est constitué de codes que vous souhaitez classer séparément.

Voir [Sous-classifications](/help/components/c-classifications2/c-sub-classifications.md) pour obtenir des informations conceptuelles sur les sous-classifications.

## Exemple

Supposons le code de suivi suivant :

`channel:broad_campaign:creative`

Une hiérarchie de classification vous permet d’appliquer une classification à une autre (appelée *`sub-classification`*). En d’autres termes, vous pouvez utiliser l’importateur comme une base de données relationnelle, avec plusieurs tables. Un tableau met en correspondance les codes de suivi complets avec les clés, et un autre les met en correspondance avec d&#39;autres tableaux.

![](assets/sub_class_table.png)

Une fois cette structure en place, vous pouvez utiliser le  [Créateur de règles de classifications](/help/components/c-classifications2/crb/classification-rule-builder.md) pour télécharger des petits fichiers qui mettent uniquement à jour les tables de recherche (tables de couleurs verte et rouge dans l’image précédente). Vous pouvez ensuite utiliser le créateur de règles pour tenir le tableau de classification principal à jour.

Le suivant décrit la  à suivre.

## Configurer des sous-classifications à l’aide du Créateur de règles {#task_2D9016D8B4E84DBDAF88555E5369546F}

Cette procédure décrit le téléchargement de sous-classifications à l’aide du Créateur de règles.

>[!NOTE]
>
>Ces étapes décrivent la procédure à suivre pour réaliser le cas d’utilisation décrit dans [Sous-classifications et Créateur de règles](/help/components/c-classifications2/crb/sub-classification-rule-builder.md).

1. Créez des classifications et des sous-classifications dans le [Gestionnaire de classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html).

   Exemple :

   ![Infos sur l’étape](assets/sub_class_create.png)

1. Dans [Créateur de règles de classifications](/help/components/c-classifications2/crb/classification-rule-builder.md), classez la clé de sous-classification à partir du code de suivi d’origine.

   Pour ce faire, utilisez une expression régulière. Dans cet exemple, la règle servant à compléter  *`Broad Campaign code`* utilisera cette expression régulière :

   | `#` | Type de règle | Correspondre | Définir la classification | À |
   |---|---|---|---|---|
   |  | Expression régulière | `[^\:]:([^\:]):([^\:]`) | Code de campagne large | `$1` |
   |  | Expression régulière | `[^\:]:([^\:]):([^\:]`) | Code de création | `$2` |

   >[!NOTE]
   >
   >À ce stade, vous ne complétez pas les sous-classifications *`Campaign Type`* et *`Campaign Director`*.

1. Téléchargez un fichier de classification contenant uniquement les sous-classifications spécifiées.

   Voir [Classifications à plusieurs niveaux](/help/components/c-classifications2/c-sub-classifications.md).

   Exemple :

   | Clé | Canal | Code de campagne large | Broad Campaign code&amp;Hat;Campaign type | Broad Campaign code&amp;Hat;Campaign Director | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Marque | Suzanne |  |
   | * |  | 222 | Marque | Frank |  |

1. Pour gérer les tables de recherche, téléchargez un petit fichier (comme illustré ci-dessus).

   Le téléchargement de ce fichier sera effectué, par exemple, lors de l’insertion d’un nouveau *`Broad Campaign code`*. Ce fichier s’appliquera aux valeurs classées précédemment. De même, si vous créez une sous-classification (telle que  *`Creative Theme`* en tant que sous-classification de *`Creative code`*), vous ne téléchargerez que le fichier de sous-classification, au lieu de l’intégralité du fichier de classification.

   Pour  ces sous-classifications fonctionnent exactement comme des classifications de niveau supérieur. Cela réduit la charge de gestion nécessaire pour les utiliser.-->
