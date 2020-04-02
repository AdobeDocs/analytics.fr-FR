---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
title: Mesure de participation
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Mesure de participation

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une commande. Procédez comme suit :

> [!NOTE] Auparavant, vous deviez effectuer cette opération via Outils d’administration. Vous pouvez continuer à activer les mesures de participation dans Outils d’administration, mais uniquement pour les événements personnalisés de 1 à 100.

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une inscription aux courriers électroniques. Procédez comme suit :

1. Créez une mesure dans le créateur de mesures calculées.
1. Faites glisser l’événement de succès « Commandes » vers le canevas Définition.
1. Modifiez le [modèle d’attribution](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) de cet événement en **[!UICONTROL Participation]** sous l’engrenage **[!UICONTROL Paramètres]**. Sélectionnez la recherche en amont **[!UICONTROL Visite]**. La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Enregistrez la mesure.
1. Utilisez la mesure calculée dans un rapport **[!UICONTROL Pages]**.

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise.

