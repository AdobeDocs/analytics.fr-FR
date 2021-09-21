---
description: Utilisez des segments rapides dans Analysis Workspace.
title: Segments rapides
feature: Workspace Basics
role: User, Admin
source-git-commit: 9622131ebd4a856cb7756e6844d7d7979029e70e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# Segments rapides

Vous pouvez créer des segments rapides dans un projet afin de contourner la complexité du [créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md) complet. Pour une comparaison des effets des segments rapides par rapport aux segments complets au niveau des composants, voir [ici](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Les segments rapides font actuellement l’objet de tests limités et ne sont pas encore disponibles dans l’ensemble.

## Création de segments rapides

1. Dans un tableau à structure libre, cliquez sur l’icône filter+ dans l’en-tête du panneau :

   ![](assets/quick-seg1.png)

   Notez que:

   - Il existe un seul conteneur de segments qui vous permet d’inclure une dimension/mesure/période dans le segment (ou de l’exclure).
   - Vous pouvez définir le conteneur sur le niveau Accès, Visite ou Visiteur. La valeur par défaut est Accès.

1. Ajoutez une dimension/mesure/période de l’une des trois façons suivantes :

   - Commencez la saisie et le créateur de segments rapides trouve automatiquement le composant approprié.
   - Utilisez la liste déroulante pour trouver le composant.
   - Faites glisser et déposez des composants à partir du rail de gauche.

1. Spécifiez la première règle, par exemple `Page equals workspace`. Les définitions de segment peuvent contenir jusqu’à trois règles. Cliquez simplement sur le signe &quot;+&quot; pour ajouter une autre règle. Vous pouvez ajouter des qualificateurs &quot;AND&quot; ou &quot;OR&quot; aux règles, mais vous ne pouvez pas mélanger &quot;AND&quot; et &quot;OR&quot; dans une seule définition de segment.

   Voici un exemple de segment qui combine des dimensions et des mesures :

   ![](assets/quick-seg2.png)

1. Cliquez sur **[!UICONTROL Appliquer]** pour appliquer ce segment au panneau.
Le segment s’affiche en haut. Notez sa barre latérale grise, par opposition à la barre bleue pour les segments au niveau du composant à gauche.

   ![](assets/quick-seg3.png)

## Rendre les segments rapides publics

Pour rendre ces segments publics (globaux), procédez comme suit :

1. Pointez sur le segment rapide, puis cliquez sur l’icône &quot;i&quot;.
1. Cliquez sur **[!UICONTROL Ouvrir le créateur]**.
Le segment s’ouvre alors dans le créateur de segments.
   >[!NOTE]
   >Une fois que vous avez appliqué ou enregistré le segment dans le créateur de segments, vous ne pouvez plus le modifier dans le créateur de segments rapide.
1. Cliquez sur **[!UICONTROL OK]**.
1. Dans le créateur de segments, cliquez sur **[!UICONTROL Appliquer]**.
1. Revenez à Workspace et remarquez que le segment comporte désormais une barre latérale bleue, signalant qu’il fait partie de la bibliothèque de composants.

   ![](assets/quick-seg4.png)

