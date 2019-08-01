---
description: Le code d'intégration requiert que le module Integrate existe dans votre déploiement Adobe Analytics.
seo-description: Le code d'intégration requiert que le module Integrate existe dans votre déploiement Adobe Analytics.
seo-title: Inclusion du module Integrate
title: Inclusion du module Integrate
uuid: e 574 f 3 db -49 fa -4 f 72-bbcf-fd 98540 d 3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

Le code d'intégration requiert que le module Integrate existe dans votre déploiement Adobe Analytics.

Si vous ne disposez pas déjà du module Integrate dans le cadre de votre déploiement, suivez les étapes ci-après en fonction du type d'implémentation.

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >Collez-le juste avant le commentaire DO NOT ALTER ANYTHING BELOW THIS LINE dans le fichier.

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Téléchargez le module Integrate à partir de la zone Ressources dans l'interface utilisateur des Connecteurs de données (sous l'onglet Assistance).

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >Collez-le juste avant le commentaire DO NOT ALTER ANYTHING BELOW THIS LINE dans le fichier.

