---
description: valeur nulle
title: Déploiement de l’intégration
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 61df62a6f7089ce7d0308e3b62664176b76e520e

---


# Déploiement de l’intégration {#deploying-the-integration}

Le déploiement de cette intégration consiste à exécuter l’assistant d’intégration Adobe, à déployer le code du module externe (JavaScript) et à vérifier l’intégration.

## Finalisation de l’assistant d’intégration Adobe {#complete-the-adobe-integration-wizard}

Pour activer l’intégration, exécutez l’assistant de configuration dans l’interface des connecteurs de données.

1. Connectez-vous à Adobe Experience Cloud.
1. Accédez à **[!UICONTROL Data Connectors]**.
1. Lancez l’assistant d’intégration Kampyle.
1. Sélectionnez la suite de rapports de votre choix et attribuez un nom à l’intégration.
1. Renseignez les éléments suivants :
   1. **[!UICONTROL Email address]**: Adresse électronique du contact principal.
   1. **[!UICONTROL Description]** (facultatif) : Description de cette configuration d’intégration.
   1. **[!UICONTROL Kampyle Key]**: Recherchez cette clé dans l’application Kampyle sous **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]**: Valeur du serveur de suivi que vous utilisez pour effectuer le suivi des données Adobe Analytics.
   1. **[!UICONTROL Tracking Server Secure]**: Si votre serveur de suivi est différent pour le trafic sécurisé/https, indiquez ce paramètre ici.
1. Configure the following **[!UICONTROL Variable Mappings]** items:
   1. **[!UICONTROL Kampyle Feedback ID]**: Sélectionnez une variable eVar disponible dans votre suite de rapports
   1. **[!UICONTROL Feedback Grade]**: Sélectionnez un  de réussite disponible (saisissez &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Feedback Items]**: Sélectionnez un  de réussite disponible (saisissez &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Feedback with Grade]**: Sélectionnez un  de réussite disponible (saisissez &quot;compteur&quot;) dans votre suite de rapports.
1. Cochez la case pour que le tableau de bord d’intégration Kampyle soit automatiquement créé (recommandé).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## Déploiement de l’objet de configuration d’intégration {#deploy-the-integration-configuration-object}

Une fois l’assistant d’intégration terminé, déployez l’objet de configuration d’intégration sur votre propriété web. Dans de nombreux cas, le moyen le plus simple de déployer l’objet de configuration de l’intégration consiste à l’inclure dans votre code de déploiement Adobe Analytics.

> [!NOTE] Si vous utilisez Adobe Experience Platform Launch, vous pouvez facilement ajouter l’objet de configuration de l’intégration à l’aide de cet outil.

1. Navigate to the **[!UICONTROL Resources]** > **[!UICONTROL Support]** tab of the integration.
1. Téléchargez et enregistrez la **[!UICONTROL Kampyle Integration Code (JS)]** ressource. Le code ressemble à ceci :

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Déployez le code à l’aide de l’une des méthodes suivantes :

   * Utilisez Adobe Experience Platform Launch.
   * Fournissez le code à la ressource d’organisation qui gère votre déploiement d’Adobe Analytics.

## Vérification de l’intégration {#verify-the-integration}

Vérifiez que l’intégration transfère correctement les données en effectuant quelques vérifications.

### Journal d’activité d’intégration {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Under the **[!UICONTROL Data In]** tab, you should see entries stating that classification data was successfully imported.

> [!NOTE] Les entrées de journal s’affichent généralement dans les 24 heures suivant le déploiement réussi.

![Journal  du d’intégration](assets/integration_activity_log.png)

### Données de création de rapports Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Affichez vos rapports de retour Kampyle avec Adobe Analytics en accédant aux rapports Kampyle dans la structure de menus appropriée.

> [!NOTE] Les données de création de rapports doivent apparaître dans les 24 à 48 heures suivant le déploiement réussi, en supposant que les formulaires de retour intégrés reçoivent activement des soumissions.

![Données  Adobe](assets/adobe_reporting_data.png)
