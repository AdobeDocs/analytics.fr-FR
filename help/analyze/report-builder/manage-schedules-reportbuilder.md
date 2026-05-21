---
title: Gestion Des Classeurs Planifiés Dans Report Builder
description: Découvrez comment gérer les classeurs planifiés dans Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fc0357f7-1762-47e4-9691-5fbdb177d45b
TQID: https://experienceleague.adobe.com/QbA2xh07-E4WMt70tLIoR-TL30qfnvFSCToTVi3COXU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 6%

---

# Gérer les classeurs planifiés

Vous pouvez planifier le partage d’un classeur par e-mail ou en l’exportant vers une destination cloud, comme décrit dans les articles suivants :

* [Planification de classeurs par partage via e-mail](/help/analyze/report-builder/schedule-reportbuilder.md)

* [Planifier des classeurs en exportant vers des destinations cloud](/help/analyze/report-builder/report-builder-export.md)

Les sections suivantes décrivent comment gérer les classeurs après leur planification :

## Afficher et gérer les classeurs planifiés

Vous pouvez afficher et gérer tous les classeurs planifiés dans l’onglet **[!UICONTROL Classeurs]**.

1. Sélectionnez **[!UICONTROL Planifier]** dans le hub Report Builder

1. Sélectionnez l’onglet **[!UICONTROL Classeurs]**. La liste de tous les classeurs planifiés s’affiche. (Vous pouvez également sélectionner l’onglet **[!UICONTROL Hérité]** pour afficher la liste des classeurs hérités qui doivent être migrés vers le nouveau Report Builder.)

   ![Classeur planifié](assets/scheduled-workbooks.png){zoomable="yes"}

1. Effectuez l’une des opérations suivantes :

   * Pointez sur l’icône pour afficher le statut d’un classeur planifié.

   * Dans le champ de recherche ![Rechercher](/help/assets/icons/Search.svg), recherchez des classeurs planifiés spécifiques.

   * Sélectionnez l’icône de colonne ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour définir les colonnes à afficher.

   * Sélectionnez l’icône de filtre ![icône de filtre](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), puis sélectionnez [!UICONTROL **Tout afficher**] pour afficher tous les classeurs planifiés pour une organisation donnée.

1. Sélectionnez un ou plusieurs classeurs.

   ![Planifier les classeurs sélectionnés](assets/scheduled-workbooks-selected.png){zoomable="yes"}

   Les options disponibles sont les suivantes :

   | Option | Description |
   |---|---|
   | ![Modifier](/help/assets/icons/Edit.svg) | Modifiez la planification d’un classeur sélectionné. |
   | ![Historique](/help/assets/icons/History.svg) | Afficher l’historique des classeurs sélectionnés. |
   | ![Pause](/help/assets/icons/Pause.svg) | Mettre en pause le planning des classeurs sélectionnés. |
   | ![Lecture](/help/assets/icons/Play.svg) | Reprenez la planification des classeurs sélectionnés. |
   | ![Télécharger](/help/assets/icons/Download.svg) | Téléchargez le classeur sélectionné dans un nouveau classeur. |
   | ![Supprimer](/help/assets/icons/Delete.svg) | Supprimez la planification des classeurs sélectionnés. |


## Historique et statut des classeurs planifiés

Vous pouvez afficher l’historique et le statut des classeurs planifiés dans l’onglet **[!UICONTROL Historique]**.

1. Sélectionnez **[!UICONTROL Planifier]** dans le hub Report Builder.

1. Sélectionnez l’onglet **[!UICONTROL Historique]**. La liste de tous les classeurs planifiés s’affiche.

   ![Historique planifié](assets/scheduled-workbooks-history.png){zoomable="yes"}

   Utilisez ![Rechercher](/help/assets/icons/Search.svg) pour rechercher des classeurs spécifiques dans la liste.
Utilisez ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) pour définir les colonnes à afficher.

   L’onglet **[!UICONTROL Historique]** vous permet de consulter le statut de chaque tâche planifiée. Une ligne distincte documente le changement d’état pour chaque tâche planifiée.

   * Un ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg) indique que le classeur a bien été envoyé.
   * Un ![AlertRed](/help/assets/icons/AlertRed.svg) indique qu&#39;une erreur s&#39;est produite.

Vous pouvez également sélectionner ![Historique](/help/assets/icons/History.svg) pour un ou plusieurs classeurs sélectionnés dans l’onglet **[!UICONTROL Classeurs]**. Cette action affiche l’onglet **[!UICONTROL Historique]** avec une liste filtrée par votre sélection. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer un filtre.
