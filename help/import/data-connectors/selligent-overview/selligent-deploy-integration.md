---
description: Le déploiement de cette intégration est un processus simple en trois étapes.
title: Déploiement de l’intégration
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration{#deploying-the-integration}

Le déploiement de cette intégration est un processus simple en trois étapes.

## Fin de l'Assistant d'intégration{#completing-the-integration-wizard}

Pour activer l’intégration, vous devez exécuter l’assistant d’intégration sélective dans l’interface des connecteurs de données.

1. Accédez à la zone Connecteurs de données dans Adobe Experience Cloud.

   ![](assets/selligent-data_connectors.png)

1. Sous **[!UICONTROL Ajouter des intégrations]**, faites glisser et déposez le module externe sélectif dans Adobe Experience Cloud.

   ![](assets/selligent-add_integration.png)

   Cela ouvrira l’intégration du connecteur de données sélectif.

1. **Paramètres** d’intégration : Choisissez une suite de rapports et nommez l’intégration sous Paramètres **[!UICONTROL d’]** intégration.

1. Sous Valeurs **** personnalisées, renseignez toutes vos informations de compte sélectif.

   ![](assets/selligent-general_settings.png)

1. **Mappage** de variables : Sélectionnez les eVars et événements réservés appropriés dans les menus déroulants :

   ![](assets/selligent-variables.png)

1. **Paramètres** des données : Vous pouvez choisir vos propres segments sous **[!UICONTROL Vos segments]** , à l’exception des trois segments automatisés **[!UICONTROL du partenaire]** .

1. Cette intégration peut nécessiter le téléchargement de quelques points de données vers votre compte sélectif. Vous pouvez choisir d’autoriser l’accès pour la même personne sous Demande **[!UICONTROL d’]** accès.
1. Sous Collecte **[!UICONTROL de]** données, choisissez une solution automatisée ou manuelle (module externe JavaScript) pour collecter les paramètres de chaîne de requête à partir de l’URL de la page d’entrée. Si vous choisissez une solution automatisée, entrez le paramètre de chaîne de requête pour l’ID de message et l’ID de destinataire, respectivement MID et RID. Pour le module externe JavaScript, contactez votre consultant Adobe.
1. **Paramètres** du rapport : Sous Génération **[!UICONTROL de]** tableau de bord, cochez la case pour que le tableau de bord Sigligent soit automatiquement généré.

   ![](assets/selligent-report_settings.png)

1. Passez en revue le résumé de l’intégration et cliquez sur **[!UICONTROL Activer]**.

## Configuration dans Selligent{#configuration-within-selligent}

Dès que l’intégration est activée dans Adobe Analytics, une configuration automatique est activée du côté sélectif.

Un outil de suivi a été créé pour effectuer le suivi de chaque e-mail. Au cas où vous souhaitez le limiter à un certain domaine, veuillez mettre à jour la configuration du suivi.

Nous vous recommandons vivement de déplacer le paramètre de suivi pour Adobe Analytics dans l’URL vers l’avant. Cela permet de s’assurer que les règles de traitement Adobe sélectionnent les paramètres de l’URL de la page d’entrée. Activez le suivi en cochant la case comme illustré ci-dessous.

![](assets/selligent-tracker.png)

## Vérification de l’intégration{#verifying-the-integration}

Une fois toutes les étapes du déploiement terminées, vous pouvez vérifier que l’intégration réussit à transférer des données.

L'échange de données prendra quelques jours. Assurez-vous de contacter Selligent après avoir activé l’intégration.

### Journal d’activité d’intégration {#section-927e270495db479fba9578915d9ae9c9}

Accédez à votre intégration sélective dans les connecteurs de données. Sous l’onglet **[!UICONTROL Assistance]** , vous devriez voir des événements tels que Données de mesure importées et/ou Données de classification importées avec succès :

![](assets/selligent-verifying.png)

### Données de création de rapports {#section-ebd481a162324e66bd6dc8cb4b8d2424}

Affichez vos rapports de messages intelligents avec les mesures appropriées.

1. Accédez à Rapports et analyses sous Adobe Experience Cloud.
1. Sélectionnez la suite de rapports appropriée.
1. Sous Conversion **** personnalisée, sélectionnez les rapports **[!UICONTROL d’ID de]** message et choisissez ID de **[!UICONTROL message/Nom]** du message.
