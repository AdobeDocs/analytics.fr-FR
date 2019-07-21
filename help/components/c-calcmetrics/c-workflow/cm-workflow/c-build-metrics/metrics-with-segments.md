---
description: La segmentation de mesures individuelles permet d’effectuer des comparaisons de mesures dans le même rapport. (Mesures dérivées uniquement)
seo-description: La segmentation de mesures individuelles permet d’effectuer des comparaisons de mesures dans le même rapport. (Mesures dérivées uniquement)
seo-title: Mesures segmentées
title: Mesures segmentées
uuid: 88 f 9829 b -76 e 4-4598-9494-084 a 91602 bc 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mesures segmentées

La segmentation de mesures individuelles permet d’effectuer des comparaisons de mesures dans le même rapport. (Mesures dérivées uniquement)

## Comparaison de segments {#section_29A6E0070F084BFDB6228FA9CE106F48}

Imaginons que vous souhaitez comparer différents aspects du segment « Visiteurs E.U. » à ceux du segment « Visiteurs internationaux ». Vous pouvez créer des mesures qui vous donneront des informations telles que :

* Qu’obtient-on en termes de comparaison du comportement de navigation du contenu entre ces deux groupes ? (Un autre exemple : qu’obtient-on en termes de comparaison du taux de conversion entre ces deux segments ?)
* En termes de pourcentage du nombre de visiteurs total, combien de visiteurs E.U. parcourent certaines pages par rapport aux visiteurs internationaux ?
* Quelles sont les différences majeures en termes de contenu parcouru par ces différents segments ?

Explorons la première question : qu’obtient-on en termes de comparaison du comportement de navigation du contenu entre ces deux groupes ?

1. Si vous ne disposez pas d’un segment à comparer, créez un segment interne directement dans le créateur de mesures calculées nommé « Visiteurs allemands », où « Pays » est « Allemagne ». Faites simplement glisser la dimension Pays dans le canevas Définition et sélectionnez Allemagne comme valeur :

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >You can also do this in the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html), but we have simplified the workflow by making dimensions available in the Calculated Metric Builder.

   >[!NOTE]
   >
   >"Internal" means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. Vous pouvez néanmoins le rendre public en pointant sur l’icône « i » en regard et en cliquant sur **[!UICONTROL Rendre public]**.

1. Si vous n’avez pas de segment à comparer, créez un segment appelé « Visiteurs internationaux » où « Pays » n’est pas « Allemagne ».
1. Créez et enregistrez une mesure appelée « Visiteurs allemands » en faisant glisser le segment Allemagne dans le canevas Définition et en y faisant glisser la mesure Visiteurs uniques :

   ![](assets/german-visitors.png)

1. Répétez l’étape 3 avec le segment Visiteurs internationaux et la mesure Visiteurs uniques afin de créer une mesure Visiteurs internationaux.
1. Dans Analysis Workspace, faites glisser la dimension **[!UICONTROL Page]dans un tableau à structure libre, puis faites glisser les 2 nouvelles mesures calculées l’une à côté de l’autre dans la partie supérieure :**

   ![](assets/workspace-pages.png)

1. Or, in [!UICONTROL Reports &amp; Analytics], open the [!UICONTROL Pages] report and click **[!UICONTROL Show Metrics]**, then apply the new US Visitors and International Visitors segmented metrics to see how their content browsing behavior compares.

   ![](assets/pages-report.png)

## Comparaison des pourcentages des totaux {#section_846CB89725F04388AE0352DB20189EE8}

Vous pouvez introduire un autre niveau de requête en comparant le comportement de navigation des visiteurs sous la forme de pourcentages normalisés. Pour ce faire, créez deux nouvelles mesures, « % du total des visiteurs allemands » et « % du total des visiteurs internationaux » :

1. Déposez le segment Visiteurs allemands (ou internationaux) dans le canevas.
1. Déposez un autre segment Visiteurs allemands (ou internationaux) dessous. Néanmoins, cette fois-ci, cliquez sur l’icône (engrenage) de configuration pour sélectionner le type de mesure « Total ». Le format doit être « Pourcentage ». L’opérateur doit être « divisé par ». Vous terminez avec cette définition de mesure :

   ![](assets/cm_metric_total.png)

1. Appliquez cette mesure à votre projet :

   ![](assets/cm_percent_total.png)

## Comparaison des différences en pourcentages (en utilisant des conteneurs) {#section_13D6353259B74C09B37BA6378A501938}

Si vous souhaitez visualiser les plus grandes différences de comportement de navigation entre les visiteurs E.U. et internationaux en un coup d’œil, vous pouvez créer une autre mesure qui soustrait les pourcentages les uns des autres. Pour ce faire, vous pouvez utiliser la fonctionnalité Conteneur qui agit effectivement comme des parenthèses autour des 2 ensembles de mesures.

1. In the [!UICONTROL Definition] canvas, click **[!UICONTROL Add]** &gt; **[!UICONTROL Container]**:

   ![](assets/cm_add_container.png)

1. Déposez la mesure « % du total des visiteurs E.U. » que vous avez créée précédemment dans le premier conteneur - elle se développe à sa définition complète :

   ![](assets/cm_container_us.png)

1. Créez un autre conteneur dessous et déposez-y la mesure « % du total des visiteurs E.U. ».
1. Modifiez l’opérateur entre les 2 conteneurs sur un signe moins (-).

   ![](assets/cm_container_intl.png)

1. Enregistrez la mesure (assurez-vous que vous l’avez nommée « Différence en % entre E.U. et international » ou une dénomination similaire).
1. Lorsque vous l’appliquez au rapport, vous pouvez facilement déterminer où se trouvent les plus grandes différences en pourcentage et vous pouvez trier le rapport en conséquence.

   ![](assets/cm_diff_percent.png)

