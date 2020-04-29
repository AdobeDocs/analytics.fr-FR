---
description: Cette procédure décrit la configuration d’événements de succès.
title: Configurer des événements de succès
topic: Admin tools
uuid: ca3d3f46-5fad-4481-aef6-04cad6bc6e2d
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Configurer des événements de succès

Cette procédure décrit la configuration d’événements de succès.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Résultat de l’étape](assets/success_event_page.png)

1. In the **[!UICONTROL Name]** column, select the checkbox next each item to enable editing, then specify the desired name.
1. Dans la colonne **[!UICONTROL Type]**, cochez la case en regard de chaque élément pour activer la liste déroulante, puis sélectionnez le type de votre choix.

   >[!NOTE]
   >
   >Avant de modifier un type d’événement, voir [Modifier le type d’événement](/help/admin/admin/c-success-events/event-type.md).

   Pour plus d’informations sur ces éléments, reportez-vous à la section [Page Événements de succès – Descriptions](/help/admin/admin/c-success-events/success-event.md).

1. In the **[!UICONTROL Polarity]** column, specify whether an upward trend for this metric is good or bad.
1. In the **[!UICONTROL Visibility]** column, you can hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur. [Plus...](/help/admin/admin/metric-visibility.md)
1. Fournissez une description.
1. Vérifiez si l’événement doit être toujours enregistré.
1. Activez ou désactivez [les mesures de participation](/help/components/c-variables/c-metrics/metrics-participation.md).

   >[!NOTE]
   >
   >Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/participation-metric.html).

1. Cliquez sur **[!UICONTROL Save]**.

