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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Inclusion du module Integrate{#including-the-integrate-module}

Le code d'intégration requiert que le module Integrate existe dans votre déploiement Adobe Analytics.

Si vous ne disposez pas déjà du module Integrate dans le cadre de votre déploiement, suivez les étapes ci-après en fonction du type d'implémentation.

## Pour appmeasurement version 1.0 + {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Décompressez le fichier zip appmeasurement que vous avez téléchargé depuis **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL codemanager]**.

1. Ouvrez le fichier nommé [!DNL AppMeasurement_Module_Integrate.js].
1. Copiez et collez le contenu de ce fichier dans [!DNL AppMeasurement.js] votre fichier principal.

   >[!NOTE]
   >
   >Collez-le juste avant le commentaire DO NOT ALTER ANYTHING BELOW THIS LINE dans le fichier.

## Pour code hérité (code H) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Téléchargez le module Integrate à partir de la zone Ressources dans l'interface utilisateur des Connecteurs de données (sous l'onglet Assistance).

   ![](assets/h_code.png)

1. Copiez et collez le contenu de ce fichier dans [!DNL s_code] votre fichier.

   >[!NOTE]
   >
   >Collez-le juste avant le commentaire DO NOT ALTER ANYTHING BELOW THIS LINE dans le fichier.

