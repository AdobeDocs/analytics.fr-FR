---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
feature: Calculated Metrics
exl-id: bef185d6-72c0-4068-80f8-57261369573f
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 34%

---

# Création d’une mesure &quot;Participation&quot;

Les informations suivantes expliquent comment créer une mesure qui indique les pages qui ont contribué aux (ou participé aux) visites qui contenaient une commande.

Ce type d’informations peut s’avérer utile pour tout propriétaire de contenu.

>[!NOTE]
>
>Vous pouvez activer les mesures de participation dans les outils d’administration, mais uniquement pour les événements personnalisés 1 à 100.

1. Commencez à créer une mesure calculée, comme décrit dans la section [Créer des mesures](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. Dans le créateur de mesures calculées, nommez la mesure &quot;Participation&quot;.

1. Faites glisser l’événement de succès « Commandes » vers le canevas Définition.

1. Modifiez le [modèle d’attribution](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) de cet événement en **[!UICONTROL Participation]** sous l’engrenage **[!UICONTROL Paramètres]**. Sélectionnez la recherche en amont **[!UICONTROL Visite]**. La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Sélectionner [!UICONTROL **Enregistrer**] pour enregistrer la mesure.

1. Utilisez la mesure calculée dans un rapport **[!UICONTROL Pages]**.

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise, comme décrit dans la section [Partage des mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
