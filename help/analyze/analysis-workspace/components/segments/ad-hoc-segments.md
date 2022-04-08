---
description: Utilisation de segments ad hoc dans Analysis Workspace.
title: Segments ad hoc
feature: Segmentation
role: User, Admin
exl-id: 1c189abc-ab9f-413c-9be6-0d2fc457230e
source-git-commit: f50e3d9a1d3c1705c55a14af0e42a0da3ac00955
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Segments de projet ad hoc

Les segments de projet ad hoc vous permettent de faire glisser et de déposer n’importe quel composant directement dans la zone de dépôt du panneau pour créer un segment. Le segment devient une [segment au niveau du projet](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?#what-are-project-only-segments%3F) local au projet en cours.

Regardez cette vidéo sur la création de segments de projet ad hoc :

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

1. Déplacez un type de composant (dimension, élément de dimension, événement, mesure, segment, modèle de segments, période) dans la zone de dépôt des segments en haut dʼun panneau. Les types de composants sont automatiquement convertis en segments ad hoc ou [Segments rapides](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/quick-segments.html?lang=fr) si compatible.
Regardez cet exemple sur la création dʼun segment pour le domaine référent Twitter :

   ![](assets/ad-hoc1.png)

   Ce segment est automatiquement appliqué à votre panneau et les résultats sont immédiatement affichés.

1. Vous pouvez ajouter un nombre illimité de segments à un panneau.
1. Si vous décidez dʼenregistrer ce segment, reportez-vous à la section ci-dessous.

Remarque :

* Vous **ne pouvez pas** déposer les types de composants suivants dans une zone de segment : les mesures calculées et les dimensions/mesures à partir desquelles vous ne pouvez pas créer de segments.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de chute « existe ». Exemples : `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépose, ils sont automatiquement transformés en segment « n’existe pas » afin d’être traités correctement dans la segmentation.

Pour une comparaison des différents segments que vous pouvez créer et appliquer dans un projet, accédez à [here](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

## Enregistrement des segments ad hoc {#ad-hoc-save}

Les segments ad hoc peuvent être mis à la disposition d’autres projets en les enregistrant.

1. Pointez sur le segment de la zone de dépôt, puis cliquez sur l’icône « i ».
1. Cliquez sur le crayon de modification pour accéder au créateur de segments.
1. Vérifier **[!UICONTROL Mettre tous les projets à disposition et ajouter à votre liste de composants]**.
1. Cliquez sur **[!UICONTROL ENREGISTRER]**.

Une fois enregistré, le segment est disponible dans votre liste de composants du rail de gauche et peut être partagé avec d’autres utilisateurs à partir du Gestionnaire de segments.
