---
description: valeur nulle
title: Déploiement de l’intégration
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 47%

---


# Déploiement de l’intégration {#deploying-the-integration}

Le déploiement de cette intégration est un processus simple consistant à exécuter l’Assistant Intégration Adobe, à déployer le code du module externe (JavaScript) et à vérifier l’intégration.

## Finalisation de l’assistant d’intégration Adobe {#complete-the-adobe-integration-wizard}

Pour activer l’intégration, exécutez l’assistant de configuration dans l’interface Connecteurs de données.

1. Connectez-vous à Adobe Experience Cloud.
1. Accédez à Connecteurs **[!UICONTROL de]** données.
1. Lancez l’assistant d’intégration Kampyle.
1. Sélectionnez la suite de rapports de votre choix et attribuez un nom à l’intégration.
1. Renseignez les éléments suivants :
   1. **[!UICONTROL Adresse]**&#x200B;électronique : Adresse électronique du contact principal.
   1. **[!UICONTROL Description]** (facultatif) : Description de cette configuration d’intégration.
   1. **[!UICONTROL Clé]** Kampyle : Recherchez cette clé dans l’application Kampyle sous **[!UICONTROL Commentaires > Personnalisation]** du formulaire de **** commentaires.
   1. **[!UICONTROL Serveur]** de suivi : Valeur du serveur de suivi que vous utilisez pour effectuer le suivi des données Adobe Analytics.
   1. **[!UICONTROL Serveur de suivi sécurisé]**: Si votre serveur de suivi est différent pour le trafic sécurisé/https, indiquez ce paramètre ici.
1. Configurez les éléments de **[!UICONTROL mappage de variables]** suivants :
   1. **[!UICONTROL ID]** de commentaires Kampyle : Sélectionnez une variable eVar disponible dans votre suite de rapports.
   1. **[!UICONTROL Note]** de commentaires : Sélectionnez un événement de réussite disponible (tapez &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Commentaires]**: Sélectionnez un événement de réussite disponible (tapez &quot;compteur&quot;) dans votre suite de rapports.
   1. **[!UICONTROL Commentaires avec note]**: Sélectionnez un événement de réussite disponible (tapez &quot;compteur&quot;) dans votre suite de rapports.
1. Cochez la case pour que le tableau de bord d’intégration Kampyle soit automatiquement créé (recommandé).
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Déploiement de l’objet de configuration d’intégration {#deploy-the-integration-configuration-object}

Une fois l’assistant d’intégration terminé, déployez l’objet de configuration d’intégration sur votre propriété web. Dans de nombreux cas, le moyen le plus simple de déployer l’objet de configuration de l’intégration consiste à l’inclure dans votre code de déploiement Adobe Analytics.

>[!NOTE]
>
>Si vous utilisez le lancement d’Adobe Experience Platform, vous pouvez facilement ajouter l’objet de configuration d’intégration à l’aide de cet outil.

1. Accédez à l’onglet **[!UICONTROL Ressources]** > **[!UICONTROL Assistance]** de l’intégration.
1. Téléchargez et enregistrez la ressource **[!UICONTROL Code d’intégration Kampyle (JS)]**. Le code ressemble à ceci :

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Déployez le code à l’aide de l’une des méthodes suivantes :

   * Utiliser le lancement d&#39;Adobe Experience Platform.
   * Fournissez le code à la ressource organisationnelle qui gère le déploiement de Adobe Analytics.

## Vérification de l’intégration {#verify-the-integration}

Vérifiez que l’intégration transfère correctement les données en effectuant quelques vérifications.

### Journal d’activité d’intégration {#section-0472df9180db4f218db5f6040cab07af}

Affichez votre configuration de l’intégration Kampyle dans Adobe Experience Cloud en accédant à **[!UICONTROL Assistance]** > Journal **[!UICONTROL d’activité d’intégration]**. Sous l’onglet **[!UICONTROL Données dans]**, des entrées indiquent que les données de classification ont bien été importées.

>[!NOTE]
>
>Les entrées de journal s’affichent généralement dans les 24 heures suivant le déploiement réussi.

![Journal des activités d’intégration](assets/integration_activity_log.png)

### Données de création de rapports Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Affichez vos rapports de retour Kampyle avec Adobe Analytics en accédant aux rapports Kampyle dans la structure de menus appropriée.

>[!NOTE]
>
>Les données de création de rapports doivent apparaître dans les 24 à 48 heures suivant le déploiement réussi, en supposant que les formulaires de retour intégrés reçoivent activement des soumissions.

![Données du rapports Adobe](assets/adobe_reporting_data.png)
