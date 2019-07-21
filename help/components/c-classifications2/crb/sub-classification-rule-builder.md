---
description: Vous pouvez associer le Créateur de règles de classifications à des sous-classifications afin de simplifier la gestion des classifications et de réduire le nombre de règles requises. Vous pouvez procéder de la sorte si votre code de suivi se compose de codes que vous souhaitez classer séparément.
seo-description: Vous pouvez associer le Créateur de règles de classifications à des sous-classifications afin de simplifier la gestion des classifications et de réduire le nombre de règles requises. Vous pouvez procéder de la sorte si votre code de suivi se compose de codes que vous souhaitez classer séparément.
seo-title: Sous-classifications et Créateur de règles - cas d'utilisation
solution: Analytics
subtopic: Gestionnaire
title: Sous-classifications et Créateur de règles - cas d'utilisation
topic: Outils d’administration
uuid: 6 db 6 a 4 a 9-b 93 c -413 b -8049-1 e 6 cc 1 ba 4 a 38
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Sous-classifications et Créateur de règles - cas d'utilisation

Vous pouvez associer le Créateur de règles de classifications à des sous-classifications afin de simplifier la gestion des classifications et de réduire le nombre de règles requises. Vous pouvez procéder de la sorte si votre code de suivi se compose de codes que vous souhaitez classer séparément.

## Sub-classifications and the Rule Builder - use case {#concept_6C8672C242544D7487E82886BBFABE6E}

Vous pouvez associer le Créateur de règles de classifications à des sous-classifications afin de simplifier la gestion des classifications et de réduire le nombre de règles requises. Vous pouvez procéder de la sorte si votre code de suivi se compose de codes que vous souhaitez classer séparément.

See [Sub-Classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE) for conceptual information about sub-classifications.

**Exemple**

Prenons comme exemple le code de suivi ci-dessous :

`channel:broad_campaign:creative`

Une hiérarchie de classification vous permet d’appliquer une classification à une autre (appelée *`sub-classification`*). En d’autres termes, vous pouvez utiliser l’importateur comme une base de données relationnelle, avec plusieurs tables. Une table fait correspondre des codes de suivi complets à des clés, tandis qu’une autre fait correspondre ces clés à d’autres tables.

![](assets/sub_class_table.png)

Une fois cette structure en place, vous pouvez utiliser le [Créateur de règles de classifications](../../../components/c-classifications2/crb/classification-rule-builder.md) pour télécharger des petits fichiers qui mettent uniquement à jour les tables de recherche (tables de couleurs verte et rouge dans l’image précédente). Vous pouvez ensuite utiliser le créateur de règles pour assurer la mise à jour du tableau de classification principal.

La tâche ci-dessous décrit la marche à suivre.

## Set up Sub-Classifications using the Rule Builder{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

Cette procédure décrit le téléchargement de sous-classifications à l’aide du Créateur de règles.

>[!NOTE]
>
>These steps describe how to accomplish the use case described in [Sub-Classifications and the Rule Builder](../../../components/c-classifications2/crb/sub-classification-rule-builder.md).

1. Créez des classifications et des sous-classifications dans le [Gestionnaire de classifications](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=classifications).

   Exemple :

   ![Informations sur les étapes](assets/sub_class_create.png)

1. In the [Classifications Rule Builder](../../../components/c-classifications2/crb/classification-rule-builder.md#concept_C1F219E622044D43852EF5168FF7192A), classify the sub-classification key from the original tracking code.

   Pour ce faire, utilisez une expression régulière. Dans cet exemple, la règle servant à compléter *`Broad Campaign code`* utilisera cette expression régulière :

   | `#` | Type de règle | Correspond à | Définir la classification | Sur |
   |---|---|---|---|---|
   |  | Expression régulière | `[^\:]:([^\:]):([^\:]`) | Code de campagne large | `$1` |
   |  | Expression régulière | `[^\:]:([^\:]):([^\:]`) | Code de création | `$2` |

   >[!NOTE]
   >
   >At this point, you do not populate the sub-classifications *`Campaign Type`* and *`Campaign Director`*.

1. Téléchargez un fichier de classification contenant uniquement les sous-classifications spécifiées.

   See [Multiple-Level Classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_35AD906CDDC4441DAAF70664CF76AA0A).

   Exemple :

   | Clé | Canal | Code de campagne large | Code de campagne large et amp ; Chapeau ; Type de campagne | Code de campagne large et amp ; Chapeau ; Directeur de campagne | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Marque | Suzanne |  |
   | * |  | 222 | Marque | Frank |  |

1. Pour gérer les tables de recherche, téléchargez un petit fichier (comme illustré ci-dessus).

   You would upload this file, for example, when a new *`Broad Campaign code`* is introduced. Ce fichier s’appliquera aux valeurs classées précédemment. De même, si vous créez une sous-classification (telle que *`Creative Theme`* sous la forme d'une sous-classification de *`Creative code`*), vous téléchargez uniquement le fichier de sous-classification, plutôt que le fichier de classification entier.

   Dans le cadre de la création de rapports, ces sous-classifications se comportent exactement comme des classifications de niveau supérieur. Cela a pour effet d’alléger la charge de gestion associée à leur utilisation.
