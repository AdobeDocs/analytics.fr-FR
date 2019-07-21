---
description: Cette procédure décrit la configuration d’événements de succès.
seo-description: Cette procédure décrit la configuration d’événements de succès.
seo-title: Configurer des événements de succès
solution: Analytics
title: Configurer des événements de succès
topic: Outils d’administration
uuid: ca 3 d 3 f 46-5 fad -4481-aef 6-04 cad 6 bc 6 e 2 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Configurer des événements de succès

Cette procédure décrit la configuration d’événements de succès.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]**.

   ![Résultat de l’étape](assets/success_event_page.png)

1. Dans la colonne **Nom**, cochez la case en regard de chaque élément pour activer l’édition, puis indiquez le nom de votre choix.
1. Dans la colonne **Type**, cochez la case en regard de chaque élément pour activer la liste déroulante, puis sélectionnez le type de votre choix.

   >[!NOTE]
   >
   >Before you change an event type, see [Change event type](../../../admin/admin/c-success-events/event-type.md#concept_2A6FCC19E7FC429DBDFA65BC640BD448).

   Pour plus d’informations sur ces éléments, reportez-vous à la section [Page Événements de succès – Descriptions](../../../admin/admin/c-success-events/success-event.md#section_681ECEC981694CABBDBF00E18165B447).

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur. [Plus...](../../../admin/admin/metric-visibility.md#concept_A85EB68D27534C4581AF1DCF5702DDE5) 1. Fournissez une description.
1. Vérifiez si l’événement doit être toujours enregistré.
1. Enable or disable [participation metrics](/help/components/c-variables/c-metrics/metrics-participation.md).

   >[!NOTE]
   >
   >Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html).

1. Cliquez sur **[!UICONTROL Enregistrer]**.

