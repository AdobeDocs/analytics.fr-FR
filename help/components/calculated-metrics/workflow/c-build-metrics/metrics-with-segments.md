---
description: Découvrez comment segmenter des mesures individuelles, ce qui vous permet d’effectuer des comparaisons de mesures dans la même visualisation.
title: Mesures Segmentées
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
TQID: https://experienceleague.adobe.com/t1HtjinGP02YSBQk1Z95t6wIQ0OhuFb14GKfpd8Y9Eg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 463
ht-degree: 1%

---

# Mesures segmentées

Dans le [créateur de mesures calculées](cm-build-metrics.md#definition-builder), vous pouvez appliquer des segments dans votre définition de mesure. L’application de segments s’avère utile si vous souhaitez utiliser des mesures pour un sous-ensemble de vos données dans votre analyse.

>[!NOTE]
>
>Les définitions de segment sont mises à jour via le [créateur de segments](/help/components/segmentation/segmentation-workflow/seg-build.md). Si vous apportez une modification à un segment, le segment est automatiquement mis à jour partout où il est utilisé, y compris si le segment fait partie d’une définition de mesure calculée.
>

Vous souhaitez comparer les mesures pour les Allemands qui interagissent avec votre marque par rapport aux personnes en dehors de l’Allemagne. Vous pouvez donc répondre à des questions telles que :

1. Combien de visiteurs allemands et internationaux visitent vos pages les plus [populaires](#popular-pages).
1. Combien de personnes allemandes par rapport aux personnes internationales au [total](#totals) ont interagi en ligne avec votre marque ce mois-ci ?
1. Quels sont les [pourcentages](#percentages) d&#39;Allemands et d&#39;internationaux qui ont visité vos pages populaires ?

Consultez les sections ci-dessous pour illustrer la manière dont les mesures segmentées peuvent vous aider à répondre à ces questions. Le cas échéant, il est fait référence à une documentation plus détaillée.

## Pages populaires

1. [Création d’une mesure calculée](../cm-workflow.md) à partir d’un projet Workspace appelé `Germany`.
1. Dans le [créateur de mesures calculées](cm-build-metrics.md), [créez un segment](/help/components/segmentation/segmentation-workflow/seg-build.md) intitulé `Germany`, qui utilise le champ Pays .

   >[!TIP]
   >
   >Dans le créateur de mesures calculées, vous pouvez créer un segment directement à l’aide du panneau Composants .
   >   

   Votre segment pourrait ressembler à ceci :

   ![Segment Allemagne](assets/segment-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le segment pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/germany-visits.png)

Répétez les étapes ci-dessus pour la version internationale de votre mesure calculée.

1. Créez une mesure calculée à partir de votre projet Workspace, intitulée `Non Germany visits`.
1. Dans le créateur de mesures calculées , créez un segment, appelé `Not Germany`, qui utilise le champ Pays CRM de vos données CRM pour déterminer la provenance d’une personne.

   Votre segment doit ressembler à ceci :

   ![Segment Allemagne](assets/segment-not-germany.png)

1. De retour dans le créateur de mesures calculées, utilisez le segment pour mettre à jour la mesure calculée.

   ![Mesure calculée Allemagne](assets/non-germany-visits.png)


1. Créez un projet dans Analysis Workspace, qui vous permet d’afficher les pages visitées par des visiteurs allemands et non allemands.

   ![Visualisation du tableau à structure libre de Workspace montrant les Allemands par rapport aux Internationaux](assets/workspace-german-vs-international.png)


## Totaux

1. Créez deux nouvelles mesures calculées basées sur le total général. Ouvrez chacun des segments créés précédemment, renommez le segment, définissez le **[!UICONTROL Type de mesure]** pour **[!UICONTROL Personnes]** sur **[!UICONTROL Total général]** puis utilisez **[!UICONTROL Enregistrer sous]** pour enregistrer le segment en utilisant le nouveau nom. Par exemple :

   ![Mesure totale pour l’Allemagne](assets/calculated-metric-germany-total.png)

1. Ajoutez une nouvelle visualisation de tableau à structure libre à votre projet Workspace, en affichant le nombre total de pages pour cette année.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals.png)


## Pourcentages

1. Créez deux nouvelles mesures calculées qui calculent un pourcentage à partir des mesures calculées que vous avez créées précédemment.

   Visualisation du tableau à structure libre de ![Workspace indiquant le pourcentage de personnes totales en Allemagne par rapport à l’international](assets/calculated-metric-germany-total-percentage.png)


1. Mettez à jour votre projet Workspace.

   Visualisation du tableau à structure libre de ![Workspace montrant le nombre total d’Allemands par rapport aux internationaux](assets/workspace-german-vs-international-totals-percentage.png)

