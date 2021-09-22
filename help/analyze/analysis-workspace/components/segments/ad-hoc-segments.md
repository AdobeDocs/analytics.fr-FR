---
description: Utilisez des segments ad hoc dans Analysis Workspace.
title: Segments ad hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 25%

---


# Segments de projet ad hoc

Voici une vidéo sur la création de segments de projet ad hoc :

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Vous pouvez créer des segments de projet ad hoc si vous souhaitez explorer rapidement la manière dont un segment peut affecter votre projet, sans passer par le créateur de segments. Considérez ces segments comme des segments temporaires au niveau du projet. Ils ne font généralement pas partie de votre &quot;bibliothèque&quot; de segments comme les segments de composants dans le rail de gauche. Vous pouvez toutefois les enregistrer, comme illustré ci-dessous.

Pour une comparaison des effets des segments de projet ad hoc par rapport aux segments de niveau de composant complet, voir [ici](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

1. Déposez tout type de composant (dimension, élément de dimension, événement, mesure, segment, modèle de segment, période) dans la zone de dépôt des segments en haut d’un panneau. Les types de composants sont automatiquement transformés en segments.
Voici un exemple de création d’un segment pour le domaine référent Twitter :

   ![](assets/ad-hoc1.png)

   Ce segment est automatiquement appliqué à votre panneau et vous pouvez immédiatement afficher les résultats.

1. Vous pouvez ajouter un nombre illimité de composants à un panneau.
1. Si vous décidez d&#39;enregistrer ce segment, reportez-vous à la section ci-dessous.

Remarque :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de segment : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de segments.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de chute « existe ». Exemples : `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépose, ils sont automatiquement transformés en segment « n’existe pas » afin d’être traités correctement dans la segmentation.

>[!NOTE]
>
>Les segments créés de cette façon sont internes au projet.

## Enregistrement des segments de projet ad hoc {#ad-hoc-save}

Vous pouvez choisir d’enregistrer ces segments en procédant comme suit :

1. Pointez sur le segment de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Dans le panneau d’informations qui s’affiche, cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/segment-info.png)

## Que sont les segments de projet uniquement ?

Les segments de projet uniquement sont des segments rapides ou des segments de projet Workspace ad hoc. Lorsque vous les modifiez/ouvrez dans le créateur de segments, la zone Projet uniquement s’affiche. S’ils APPLIQUENT un segment rapide dans le créateur, mais ne cochent pas la case rendre disponible, il s’agit toujours d’un segment de projet uniquement, mais il ne peut plus être ouvert dans le créateur QS. S’ils cochent la case et l’ENREGISTRER, il s’agit désormais d’un segment de liste de composants.