---
description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
seo-description: Avec le créateur de mesures calculées, tout le monde peut créer une mesure de participation.
seo-title: Mesure de participation
title: Mesure de participation
uuid: 7 cb 191 be-bc 4 e -46 ef -8 a 20-ccba 5355 e 253
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mesure de participation

Voici un cas d'utilisation simple : Vous êtes propriétaire du contenu et souhaitez savoir quelles pages ont contribué aux visites qui ont contenu une commande. Procédez comme suit :

>[!NOTE]
>
>Vous deviez le faire via les outils d'administration. Vous pouvez continuer à activer les mesures de participation dans Outils d’administration, mais uniquement pour les événements personnalisés de 1 à 100.

Voici un cas d’utilisation simple : vous êtes propriétaire de contenu et souhaitez déterminer quelles pages ont contribué aux (participé dans) visites qui contenaient une inscription aux courriers électroniques. Voici comment procéder :

1. Créez une mesure dans le créateur de mesures calculées.
1. Faites glisser l'événement de réussite « Commandes » dans le canevas Définition.
1. Change the [attribution model](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) of that event to **[!UICONTROL Participation]** under the **[!UICONTROL Settings]** gear. Select **[!UICONTROL Visit]** lookback. La définition doit ressembler à celle-ci :

   ![](assets/participation.png)

1. Enregistrez la mesure.
1. Use the calculated metric in a **[!UICONTROL Pages]** report.

   ![](assets/participation-pages.png)

1. (Facultatif) Partagez la mesure avec d'autres utilisateurs de votre organisation.

