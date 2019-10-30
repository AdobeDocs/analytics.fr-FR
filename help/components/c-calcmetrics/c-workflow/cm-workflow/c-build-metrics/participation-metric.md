---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
seo-description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
seo-title: Mesure de participation
title: Mesure de participation
uuid: 7cb191be-bc4e-46ef-8a20-ccba5355e253
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Mesure de participation

Voici un exemple simple d’utilisation : Vous êtes propriétaire du contenu et vous souhaitez savoir quelles pages ont contribué (c.-à-d. participé) aux visites qui contenaient une commande. Procédez comme suit :

> [!NOTE] Vous deviez le faire via les outils d’administration. Vous pouvez continuer à activer les mesures de participation dans Outils d’administration, mais uniquement pour les événements personnalisés de 1 à 100.

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une inscription aux courriers électroniques. Procédez comme suit :

1. Créez une mesure dans le créateur de mesures calculées.
1. Faites glisser l’événement de réussite "Commandes" dans le canevas Définition.
1. Modifiez le modèle [d’](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) attribution de cet événement en **[!UICONTROL Participation]** sous l’engrenage **[!UICONTROL Paramètres]** . Sélectionnez **[!UICONTROL Consultation de visite]** . La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Enregistrez la mesure.
1. Utilisez la mesure calculée dans un rapport **[!UICONTROL Pages]** .

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d’autres utilisateurs de votre entreprise.

