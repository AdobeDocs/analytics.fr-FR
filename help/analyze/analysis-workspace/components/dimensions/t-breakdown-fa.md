---
description: Ventilez les dimensions et les éléments de dimension dans Analysis Workspace.
keywords: Analysis Workspace
title: Ventilation des dimensions
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 100%

---

# Ventilation des dimensions

Ventilez les dimensions et les éléments de dimension dans Analysis Workspace.

Répartissez vos données de différentes manières en fonction de vos besoins ; créez des requêtes à l’aide de mesures, de dimensions, de segments, de chronologies pertinentes et autres valeurs de répartition d’analyse.

1. [Créez un projet](/help/analyze/analysis-workspace/home.md) avec un tableau de données.
1. Dans le tableau de données, cliquez avec le bouton droit de la souris sur une ligne et sélectionnez **[!UICONTROL Répartition]** > *`<item>`*.

   ![Résultat de l’étape](assets/fa_data_table_actions.png)

   Vous pouvez ventiler les mesures par éléments de dimension ou segments d’audience sur plusieurs périodes sélectionnées. Vous pouvez également approfondir l’analyse à un niveau plus détaillé.

   >[!NOTE]
   >
   >Vous ne pouvez pas afficher plus de 200 répartitions dans le tableau. Cette limitation augmentera pour l’exportation des répartitions.

## Application des modèles d’attribution aux répartitions

Il est également possible d’appliquer n’importe quel modèle d’attribution à n’importe quelle répartition dans un tableau. Ce modèle d’attribution peut être identique ou non à la colonne parente. Par exemple, vous pouvez analyser les Commandes linéaires au niveau de la dimension de vos canaux marketing, mais appliquer les Commandes en forme de U aux codes de suivi spécifiques au sein d’un canal. Pour modifier le modèle d’attribution appliqué à une répartition, il suffit de pointer la souris sur le modèle de répartition et de cliquer sur **[!UICONTROL Modifier]** :

![Paramètres de répartition](assets/breakdown_settings.png)

Voici le comportement attendu lors de l’application des modèles d’attribution aux répartitions ou de leur modification :

* Si vous appliquez une attribution lorsqu’il n’en existe aucune autre, celle-ci s’applique à l’ensemble de l’arborescence des colonnes.

* Si vous ajoutez une répartition après l’application d’une attribution, elle utilise la valeur par défaut de la répartition donnée ajoutée, si cette dimension comporte une valeur par défaut. Sinon, elle utilisera la répartition de la colonne parente. Certaines dimensions disposent d’une attribution par défaut.  Par exemple : les dimensions [!UICONTROL temporelles] et le [!UICONTROL référent] utilisent la [!UICONTROL même touche]. La dimension de [!UICONTROL produit] utilise la [!UICONTROL dernière touche]. Les autres dimensions ne disposent pas de valeur par défaut et utiliseront l’attribution de la colonne parente.

* Si des attributions sont déjà disponibles dans l’arborescence des colonnes, la modification de l’attribution n’a un impact que sur celle que vous modifiez.

## Vidéos

Ajout de dimensions et de mesures à votre projet dans Analysis Workspace :

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

Utilisation des dimensions dans un tableau à structure libre :

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

Regardez une vidéo sur les répartitions des dimensions par position :

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
