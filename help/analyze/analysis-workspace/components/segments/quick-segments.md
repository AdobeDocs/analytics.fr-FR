---
description: Utilisez des segments rapides dans Analysis Workspace.
title: Segments rapides
feature: Workspace Basics
role: User, Admin
source-git-commit: f3185f1ee341348fb7bdbaab8b68d421e7c79076
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---


# Segments rapides

Vous pouvez créer des segments rapides dans un projet afin de contourner la complexité du [créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md) complet. Pour une comparaison des effets des segments rapides par rapport aux segments de liste de composants complète, accédez à [ici](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> Les segments rapides font actuellement l’objet de tests limités et ne sont pas encore disponibles dans l’ensemble.

## Création de segments rapides

1. Dans un tableau à structure libre, cliquez sur l’icône filter+ dans l’en-tête du panneau :

   ![](assets/quick-seg1.png)

   Notez que:

   - Il existe un seul conteneur de segments qui vous permet d’inclure une dimension/mesure/période dans le segment (ou de l’exclure).
   - Vous pouvez définir le conteneur sur le niveau Accès, Visite ou Visiteur. La valeur par défaut est Accès.

1. Ajoutez une dimension/mesure/période de l’une des trois façons suivantes :

   - Commencez la saisie et le [!UICONTROL créateur de segments rapide] recherche automatiquement le composant approprié.
   - Utilisez la liste déroulante pour trouver le composant.
   - Faites glisser et déposez des composants à partir du rail de gauche.

1. Spécifiez la première règle, par exemple `Page equals workspace`. Vous pouvez avoir jusqu’à trois règles dans une définition de segment. Cliquez simplement sur le signe &quot;+&quot; pour ajouter une autre règle. Vous pouvez ajouter des qualificateurs &quot;AND&quot; ou &quot;OR&quot; aux règles, mais vous ne pouvez pas mélanger &quot;AND&quot; et &quot;OR&quot; dans une seule définition de segment.

   Voici un exemple de segment qui combine des dimensions et des mesures :

   ![](assets/quick-seg2.png)

1. Cliquez sur **[!UICONTROL Appliquer]** pour appliquer ce segment au panneau.
Le segment s’affiche en haut. Notez sa barre latérale grise, par opposition à la barre latérale bleue pour les segments au niveau du composant dans la bibliothèque de segments sur la gauche.

   ![](assets/quick-seg3.png)

## Modification des segments rapides

1. Pointez sur le segment rapide et sélectionnez l’icône en forme de crayon.
1. Modifiez la définition de segment ou le nom du segment.

## Enregistrement des segments rapides

Pour enregistrer des segments rapides, procédez comme suit.

>[!IMPORTANT]
>Une fois que vous avez enregistré ou appliqué le segment, vous ne pouvez plus le modifier dans le Créateur de segments rapide, uniquement dans le Créateur de segments normal.

1. Pointez sur le segment rapide et sélectionnez l’icône d’information (&quot;i&quot;).
1. Sélectionnez **[!UICONTROL Enregistrer le segment]**.

   ![](assets/save-quick-seg.png)

1. Laissez le nom en l’état ou renommez le segment.

   Revenez à Workspace et remarquez que le segment comporte désormais une barre latérale bleue. Cela indique qu’il ne peut plus être modifié/ouvert dans le Créateur de segments rapide. Et en l&#39;enregistrant, il devient une partie de la liste des composants.

   ![](assets/quick-seg4.png)

Après avoir appliqué le segment, vous pouvez choisir de l’ajouter à votre liste de composants de segment et de le rendre disponible pour tous vos projets.

1. Pointez sur le segment enregistré et sélectionnez l’icône représentant un crayon.

1. Dans la partie supérieure du créateur de segments, observez cette boîte de dialogue :

   ![](assets/project-only.png)

1. Cochez la case en regard de **[!UICONTROL Mettre ce segment à la disposition de tous vos projets et ajoutez-le à votre liste de composants.]**
1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Le segment apparaît désormais dans la liste des composants de segment pour tous vos projets.
1. Vous pouvez également [partager le segment](/help/components/segmentation/segmentation-workflow/t-seg-share.md) avec d’autres personnes de votre entreprise.

## Que sont les segments de projet uniquement ?

Les segments de projet uniquement sont des segments rapides ou des segments de projet Workspace ad hoc. Lorsque vous les modifiez/ouvrez dans le créateur de segments, la zone Projet uniquement s’affiche. S’ils APPLIQUENT un segment rapide dans le créateur, mais ne cochent pas la case rendre disponible, il s’agit toujours d’un segment de projet uniquement, mais il ne peut plus être ouvert dans le créateur QS. S’ils cochent la case et l’ENREGISTRER, il s’agit désormais d’un segment de liste de composants.