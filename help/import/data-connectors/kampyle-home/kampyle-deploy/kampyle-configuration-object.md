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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Déploiement de l'objet de configuration d'intégration{#deploy-the-integration-configuration-object}

Après avoir exécuté l'assistant d'intégration, vous devez déployer l'objet de configuration d'intégration sur votre propriété Web.

Dans de nombreux cas, la manière la plus simple de déployer l'objet de configuration d'intégration consiste à l'inclure avec votre code de déploiement Adobe Analytics.

>[!NOTE]
>
>Si vous utilisez Adobe tagmanager ou la gestion dynamique des balises pour déployer Adobe Analytics, vous pouvez facilement ajouter l'objet de configuration d'intégration à cet outil.

1. Accédez à **[!UICONTROL l'onglet Ressources]** &gt; **[!UICONTROL Assistance]** de l'intégration.
1. Téléchargez et enregistrez la ressource du code d'intégration **[!UICONTROL Kampyle]** (JS). Le code ressemble à ceci :

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Déployez le code à l'aide de l'une des méthodes suivantes :

       | ** Vous utilisez Adobe tagmanager ou la gestion dynamique des balises.** | Utilisez l'interface de gestion des balises pour ajouter le code. |
    |—|—|
    | ** Dans tous les autres cas** | Fournissez le code à la ressource organisationnelle responsable de la mise à jour du code de déploiement Adobe Analytics. |
   
