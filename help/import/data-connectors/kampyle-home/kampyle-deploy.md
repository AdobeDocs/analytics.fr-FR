---
description: Déployez le connecteur de données Kampyle dans Adobe Analytics.
title: Déploiement de l’intégration
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
exl-id: ac8e1f30-cefe-448a-bec6-cda58ee51025
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 47%

---

# Déploiement de l’intégration{#deploying-the-integration}

Le déploiement de cette intégration est un processus simple consistant à exécuter l’assistant d’intégration Adobe, à déployer le code du plug-in (JavaScript) et à vérifier l’intégration.

## Finalisation de l’assistant d’intégration Adobe {#complete-the-adobe-integration-wizard}

Pour activer l’intégration, exécutez l’assistant de configuration dans l’interface des Data Connectors.

1. Connectez-vous à [!DNL Adobe Experience Cloud].
1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Connecteurs de données]**.
1. Lancez l’assistant d’intégration Kampyle.
1. Sélectionnez la suite de rapports de votre choix et attribuez un nom à l’intégration.
1. Renseignez les éléments suivants :
   1. **[!UICONTROL Adresse électronique]** : Adresse électronique du Principal contact.
   1. **[!UICONTROL Description]**  (facultatif) : Description de cette configuration d’intégration.
   1. **[!UICONTROL Clé Kampyle]** : Recherchez cette clé dans l’application Kampyle sous  **[!UICONTROL Formulaire de retour]**  >  **[!UICONTROL Personnalisation du formulaire de retour]**.
   1. **[!UICONTROL Serveur]** de suivi : La valeur du serveur de suivi que vous utilisez pour effectuer le suivi des données Adobe Analytics.
   1. **[!UICONTROL Serveur de suivi sécurisé]** : Si votre serveur de suivi est différent pour le trafic sécurisé/https, indiquez ce paramètre ici.
1. Configurez les éléments de **[!UICONTROL mappage de variables]** suivants :
   1. **[!UICONTROL ID de retour Kampyle]** : Sélectionner une variable d’eVar disponible dans votre suite de rapports
   1. **[!UICONTROL Note]** de retour : Sélectionnez un événement de succès disponible (type &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Éléments de retour]** : Sélectionnez un événement de succès disponible (type &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Commentaires avec note]** : Sélectionnez un événement de succès disponible (type &quot;compteur&quot;) dans votre suite de rapports.
1. Cochez la case pour que le tableau de bord d’intégration Kampyle soit automatiquement créé (recommandé).
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Déploiement de l’objet de configuration d’intégration {#deploy-the-integration-configuration-object}

Une fois l’assistant d’intégration terminé, déployez l’objet de configuration de l’intégration sur votre propriété web. Dans de nombreux cas, le moyen le plus simple de déployer l’objet de configuration de l’intégration consiste à l’inclure dans votre code de déploiement Adobe Analytics.

>[!NOTE]
>
>Si vous utilisez des balises dans Adobe Experience Platform, vous pouvez facilement ajouter l’objet de configuration d’intégration via cet outil.

1. Accédez à l’onglet **[!UICONTROL Ressources]** > **[!UICONTROL Assistance]** de l’intégration.
2. Téléchargez et enregistrez la ressource **[!UICONTROL Code d’intégration Kampyle (JS)]**. Le code ressemble à ceci :

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

3. Déployez le code à l’aide de l’une des méthodes suivantes :

   * Utilisez des balises dans Adobe Experience Platform.
   * Envoyez le code à la ressource d’organisation qui gère votre déploiement Adobe Analytics.

## Vérification de l’intégration {#verify-the-integration}

Vérifiez que l’intégration transfère correctement les données en effectuant quelques vérifications.

### Journal d’activité d’intégration {#section-0472df9180db4f218db5f6040cab07af}

Affichez votre configuration de l’intégration Kampyle dans Adobe Experience Cloud en accédant à **[!UICONTROL Assistance]** > Journal **[!UICONTROL d’activité d’intégration]**. Sous l’onglet **[!UICONTROL Données dans]**, des entrées indiquent que les données de classification ont bien été importées.

>[!NOTE]
>
>Les entrées de journal s’affichent généralement dans les 24 heures suivant le déploiement.

![Journal d’activité d’intégration](assets/integration_activity_log.png)

### Données de création de rapports Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Affichez vos rapports de retour Kampyle avec Adobe Analytics en accédant aux rapports Kampyle dans la structure de menus appropriée.

>[!NOTE]
>
>Les données de création de rapports doivent apparaître dans les 24 à 48 heures suivant le déploiement réussi, en supposant que les formulaires de retour intégrés reçoivent activement des soumissions.

![Adobe des données de création de rapports](assets/adobe_reporting_data.png)
