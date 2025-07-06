---
description: Découvrez le type de mesure et l’attribution.
title: Type De Mesure Et Attribution
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 98%

---

# Type de mesure et attribution {#metric-type-attribution}

Vous pouvez configurer le type de mesure et le [modèle d’attribution](#attribution-models) pour une mesure dans une définition de mesure calculée.

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans le composant de mesure.
1. Dans la boîte de dialogue contextuelle, réalisez les actions suivantes :

   ![Type de mesure et attribution](assets/cm-type-alloc.png)

   * Spécifiez le **[!UICONTROL type de mesure]** :

     | Type de mesure | Définition |
     |---|---|
     | **[!UICONTROL Standard]** | Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque élément de ligne. <p>Par exemple, ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Visites]** divise les commandes de cet élément de ligne spécifique par le nombre de visites correspondantes. |
     | **[!UICONTROL Total général]** | Utilisez le **[!UICONTROL Total général]** à la période de création de rapports de chaque élément de ligne. Si une formule est composée d’une mesure Total général, la mesure calculée affiche le même Total général sur chaque élément de ligne. Les mesures Total général sont utiles lorsque vous souhaitez créer des mesures calculées qui se comparent aux données totales. <p>Par exemple, ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Nombre total de visites]** indique la proportion de commandes par rapport à toutes les visites, et pas seulement par rapport à l’élément de ligne spécifique. Dans cet exemple, vous spécifiez **[!UICONTROL Total général]** pour la mesure ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Visites]** dans votre mesure calculée, qui la transformera automatiquement en ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Nombre total de visites]**. |

   * Spécifiez **[!UICONTROL Attribution]**.

      1. Vous pouvez effectuer l’une des actions suivantes :

         * Désactivez **[!UICONTROL Utiliser un modèle d’attribution différent du modèle par défaut]** pour utiliser le modèle d’attribution de colonne par défaut, à savoir Dernière touche, avec un intervalle de recherche en amont de 30 jours.
         * Activez **[!UICONTROL Utiliser un modèle d’attribution différent du modèle par défaut]**. Dans la boîte de dialogue **[!UICONTROL Modèle d’attribution de colonne]**,

            * sélectionnez un **[!UICONTROL Modèle]** parmi les [modèles d’attribution](#attribution-models).
            * sélectionnez un **[!UICONTROL Conteneur]** parmi les options de [conteneur](#container).
            * sélectionnez un **[!UICONTROL Intervalle de recherche en amont]** dans les options d’[intervalle de recherche en amont](#lookback-window). Si vous sélectionnez **[!UICONTROL Durée personnalisée]**, vous pouvez définir la période avec un granularité allant de **[!UICONTROL minute(s)]** à **[!UICONTROL trimestre(s)]**.

      1. Sélectionnez **[!UICONTROL Appliquer]** pour appliquer le modèle d’attribution différent du modèle par défaut. Sélectionnez Annuler pour annuler.

     Si vous avez déjà défini un modèle d’attribution différent du modèle par défaut, sélectionnez **[!UICONTROL Modifier]** pour modifier la sélection.

Consultez [Exemple](#example) pour un exemple d’utilisation d’un modèle d’attribution, d’un conteneur et d’un intervalle de recherche en amont.


## Modèles d’attribution {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Utilisation d’un modèle d’attribution différent du modèle par défaut"
>abstract="Activez un modèle d’attribution autre que celui par défaut pour la mesure sélectionnée."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modèle"
>abstract="Sélectionnez un modèle d’attribution pour la mesure."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Dernière touche"
>abstract="100 % du crédit est attribué à la dernière valeur de dimension vue par un visiteur ou une visiteuse."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Première touche"
>abstract="100 % du crédit est attribué à la première valeur de dimension vue par un visiteur ou une visiteuse."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linéaire"
>abstract="Le crédit est réparti uniformément sur toutes les valeurs de dimension."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participation"
>abstract="Crédit 100 % à chaque valeur de dimension vue par un visiteur ou une visiteuse.<br/>Les totaux des colonnes sont surestimés."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Même touche"
>abstract="Le crédit est attribué uniquement aux valeurs de dimension survenant sur le même événement que la conversion."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Même touche"
>abstract="Le crédit est attribué uniquement aux valeurs de dimension survenant sur le même événement que la conversion."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="En forme de U"
>abstract="40 % du crédit à la première valeur de dimension, 40 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Courbe en J"
>abstract="60 % du crédit à la dernière valeur de dimension, 20 % à la première, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Courbe en J"
>abstract="60 % du crédit à la dernière valeur de dimension, 20 % à la première, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="En forme de J inversé"
>abstract="60 % du crédit à la première valeur de dimension, 20 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="En forme de J inversé"
>abstract="60 % du crédit à la première valeur de dimension, 20 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Atténuation temporelle"
>abstract="Les valeurs de dimension les plus proches dans le temps d’une conversion obtiennent le plus de crédit."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personnalisé"
>abstract="Définissez votre propre pondération d’attribution basée sur la position."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personnalisé"
>abstract="Définissez votre propre pondération d’attribution basée sur la position."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmique"
>abstract="Le crédit est déterminé dynamiquement à l’aide d’un algorithme statistique."

{{attribution-models-details}}


## Conteneur {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Conteneur"
>abstract="Sélectionnez un conteneur pour définir la portée souhaitée pour l’attribution."

{{attribution-container}}


## Intervalle de recherche en amont {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervalle de recherche en amont"
>abstract="Ce paramètre détermine la fenêtre d’attribution des données qui sera appliquée à chaque conversion."

{{attribution-lookback-window}}

## Exemple

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->