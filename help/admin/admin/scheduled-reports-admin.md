---
description: Permet aux utilisateurs de niveau administrateur d’afficher et de gérer des rapports planifiés à l’échelle de l’organisation.
title: File d’attente des rapports planifiés
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# File d’attente des rapports planifiés

Permet aux utilisateurs de niveau administrateur d’afficher et de gérer des rapports planifiés à l’échelle de l’organisation.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

Les fonctionnalités de niveau administrateur dans le gestionnaire de rapports programmés incluent :

* L’option permettant d’ [afficher tous les rapports](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) planifiés de votre organisation.
* [Fonctionnalités](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) de filtrage avancées au sein de votre entreprise.
* Le nouvel onglet File d’attente [des](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) rapports qui  tous les rapports placés en file d’attente pour exécution sur les serveurs .
* Exposition de l’ID [de](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) planification dans l’interface de file d’attente des rapports.

## Affichage de tous les rapports planifiés {#section_3F167CAAEEC24140B476CF95B7402690}

Sur l’ **[!UICONTROL Report List]** onglet, vous pouvez **[!UICONTROL Show All Scheduled Reports]** faire partie de votre organisation, en plus de celles que vous avez personnellement planifiées.

>[!NOTE] La **[!UICONTROL Report Name]** colonne affiche le nom du rapport planifié et la **[!UICONTROL File Name]** colonne affiche le nom de fichier personnalisé que vous avez défini dans Options de avancées. Par conséquent, si vous planifiez plusieurs rapports du même type et spécifiez des noms personnalisés pour chacun d’eux, le Gestionnaire de rapports planifiés affichera plusieurs entrées avec le même nom de rapport, mais avec des noms de fichier différents. Cela est dû au fait que le rapport principal planifié est le même, de sorte que la colonne Nom du rapport aurait les mêmes noms de rapport pour tous les rapports sauf les noms de fichiers personnalisés (tels qu’ils sont définis).

![](assets/show_all_scheduled_reports.png)

## Fonctionnalités de filtrage avancées {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## File d’attente des rapports {#section_03C866115D354BB182E90BF4D52F1E0B}

Cette file d’attente vous permet de gérer et potentiellement de supprimer les rapports planifiés qui &quot;bloquent&quot; la file d’attente. (Généralement, les rapports expirent au bout de 4 heures.)

![](assets/scheduled_reports_2.png)

La file d’attente des rapports vous permet également d’ignorer un rapport planifié une fois. Just click the blue icon in the **[!UICONTROL Manage]** column.

## ID de planification {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
