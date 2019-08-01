---
description: Après avoir exécuté l'assistant d'intégration, vous devez déployer l'objet de configuration d'intégration sur votre propriété Web.
seo-description: Après avoir exécuté l'assistant d'intégration, vous devez déployer l'objet de configuration d'intégration sur votre propriété Web.
seo-title: Déploiement de l'objet de configuration d'intégration
solution: Analytics
title: Déploiement de l'objet de configuration d'intégration
uuid: e 951 c 864-2914-4324-9 f 03-5069 d 4 f 75 d 99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploy the Integration Configuration Object{#deploy-the-integration-configuration-object}

Après avoir exécuté l'assistant d'intégration, vous devez déployer l'objet de configuration d'intégration sur votre propriété Web.

Dans de nombreux cas, la manière la plus simple de déployer l'objet de configuration d'intégration consiste à l'inclure avec votre code de déploiement Adobe Analytics.

>[!NOTE]
>
>Si vous utilisez Adobe tagmanager ou la gestion dynamique des balises pour déployer Adobe Analytics, vous pouvez facilement ajouter l'objet de configuration d'intégration à cet outil.

1. Navigate to the **[!UICONTROL Resources]** &gt; **[!UICONTROL Support]** tab of the integration.
1. Download and save the **[!UICONTROL Kampyle Integration Code (JS)]** resource. Le code ressemble à ceci :

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Déployez le code à l'aide de l'une des méthodes suivantes :

       | ** Vous utilisez Adobe tagmanager ou la gestion dynamique des balises.** | Utilisez l'interface de gestion des balises pour ajouter le code. |
       |---|---|
       | **In all other cases** | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |
   
