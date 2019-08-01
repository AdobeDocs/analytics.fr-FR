---
description: Après avoir exécuté l'assistant d'intégration, vous devez activer l'intégration pour chaque enquête Qualtrics que vous souhaitez connecter.
seo-description: Après avoir exécuté l'assistant d'intégration, vous devez activer l'intégration pour chaque enquête Qualtrics que vous souhaitez connecter.
seo-title: Activation de l'intégration dans Qualtrics Research Suite
solution: Analytics
subtopic: Qualtrics
title: Activation de l'intégration dans Qualtrics Research Suite
topic: Connecteurs de données
uuid: 2 cc 6 fa 4 a-d 17 e -4560-bd 5 b -1790851 d 6274
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

Après avoir exécuté l'assistant d'intégration, vous devez activer l'intégration pour chaque enquête Qualtrics que vous souhaitez connecter.

1. Connectez-vous à Qualtrics Research Suite.
1. On the **[!UICONTROL My Surveys]** tab, click the **[!UICONTROL Edit]** button for the survey that you want to integrate.
1. Click the **[!UICONTROL Advanced Options]** menu and select **[!UICONTROL Adobe Analytics]**. (si vous ne voyez pas cette option, demandez à votre administrateur comment obtenir les autorisations requises).

   ![](assets/advanced_options.png)

1. Select the Adobe Analytics Configuration, then click **[!UICONTROL Save]**. Si aucune configuration n'est disponible, il est probable que vous n'ayez pas encore terminé l'assistant d'intégration Adobe.
   1. The **[!UICONTROL Include Partial Responses]** checkbox can be used to indicate that you’d like to capture data into Adobe Analytics after each partial survey screen is completed. Si cette option n'est pas cochée, les données sont transférées uniquement pour les enquêtes entièrement terminées.
   1. The **[!UICONTROL Send Timestamp With Beacon]** checkbox should be used only when integrating with a Report Suite that is configured to receive time-stamped data (not common).
   ![](assets/integration_config.png)

