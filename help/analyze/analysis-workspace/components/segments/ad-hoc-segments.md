---
description: Utilisation de segments ad hoc dans Analysis Workspace.
title: Segments ad hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: ht
source-wordcount: '369'
ht-degree: 100%

---


# Segments de projet ad hoc

Regardez cette vidéo sur la création de segments de projet ad hoc :

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Vous pouvez créer des segments de projet ad hoc si vous souhaitez examiner rapidement la manière dont un segment peut affecter votre projet, sans passer par le Créateur de segments. Considérez ces segments comme des segments temporaires limités au projet en cours. Ils ne font généralement pas partie de votre « bibliothèque » de segments comme les segments dans la liste des composants du rail de gauche. Vous pouvez toutefois les enregistrer, comme illustré ci-dessous.

Pour une comparaison des effets des segments ad hoc par rapport aux segments complets de la liste des composants, rendez-vous [ici](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

1. Déplacez un type de composant (dimension, élément de dimension, événement, mesure, segment, modèle de segments, période) dans la zone de dépôt des segments en haut dʼun panneau. Les types de composants sont automatiquement transformés en segments.
Regardez cet exemple sur la création dʼun segment pour le domaine référent Twitter :

   ![](assets/ad-hoc1.png)

   Ce segment est automatiquement appliqué à votre panneau et les résultats sont immédiatement affichés.

1. Vous pouvez ajouter un nombre illimité de composants à un panneau.
1. Si vous décidez dʼenregistrer ce segment, reportez-vous à la section ci-dessous.

Remarque :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de segment : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de segments.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de chute « existe ». Exemples : `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépose, ils sont automatiquement transformés en segment « n’existe pas » afin d’être traités correctement dans la segmentation.

>[!NOTE]
>
>Les segments créés de cette façon sont internes au projet.

## Enregistrement des segments de projet ad hoc {#ad-hoc-save}

Pour enregistrer ces segments, procédez comme suit :

1. Pointez sur le segment de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Dans le panneau Informations qui sʼaffiche, cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/segment-info.png)

## Que sont les segments réservés à un projet unique ?

Les segments applicables au projet uniquement sont des segments rapides ou des segments de projet Workspace ad hoc. Lorsque vous les modifiez/ouvrez dans le créateur de segments, la boîte qui sʼapplique uniquement à ce projet sʼaffiche. En cas dʼAPPLICATION dʼun segment rapide dans le créateur sans cocher la case Rendre disponible, il sʼagit toujours dʼun segment qui sʼapplique uniquement à ce projet, mais dorénavant il ne peut plus être ouvert dans le créateur de segments rapides. Si la case est cochée et que le segment est ENREGISTRÉ, il sʼagit désormais dʼun segment de la liste de composants.