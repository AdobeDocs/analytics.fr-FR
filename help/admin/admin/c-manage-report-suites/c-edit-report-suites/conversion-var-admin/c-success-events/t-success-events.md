---
description: Cette procédure décrit la configuration d’événements de succès.
title: Configurer des événements de succès
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---

# Configurer des événements de succès

Pour configurer des événements de succès :

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Événements de succès]**.

   ![Résultat de l’étape](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Dans la colonne **[!UICONTROL Nom]**, cochez la case en regard de chaque élément pour activer l’édition, puis indiquez le nom de votre choix.
1. Dans la colonne **[!UICONTROL Type]**, cochez la case en regard de chaque élément pour activer la liste déroulante, puis sélectionnez le type de votre choix.

   >[!NOTE]
   >
   >Avant de modifier un type d’événement, voir [Modifier le type d’événement](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md).

   Pour plus d’informations sur ces éléments, reportez-vous à la section [Page Événements de succès – Descriptions](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md).

1. Dans la colonne **[!UICONTROL Polarité]**, indiquez si une tendance à la hausse pour cette mesure est bénéfique ou mauvais signe.
1. Dans la colonne **[!UICONTROL Visibilité]**, vous pouvez masquer les mesures (intégrées) standard, les événements personnalisés et les événements intégrés dans le menu, les sélecteurs de mesure, le créateur de mesures calculées et le créateur de segments.

   Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur, comme suit :


   | Paramètre | Visible dans | Masqué dans |
   |---------|----------|---------|
   | [!UICONTROL **Visible partout**] | <ul><li>Reports &amp; Analytics (menu et sélecteur de mesure)</li><li>Analysis Workspace</li><li>Créateur de segments</li><li>Créateur de mesures calculées</li></ul> | S.O. |
   | [!UICONTROL **Créateurs**] | <ul><li>Créateur de segments</li><li>Créateur de mesures calculées</li></ul> | <ul><li>Reports &amp; Analytics (menu et sélecteur de mesure)</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Masqué partout**] | S.O. | <ul><li>Reports &amp; Analytics (menu et sélecteur de mesure)</li><li>Analysis Workspace</li><li>Créateur de segments</li><li>Créateur de mesures calculées</li></ul> |

1. Fournissez une description.
1. Vérifiez si l’événement doit être toujours enregistré.
1. Activez ou désactivez les mesures de participation.

   >[!NOTE]
   >
   >Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Cliquez sur **[!UICONTROL Enregistrer]**.
