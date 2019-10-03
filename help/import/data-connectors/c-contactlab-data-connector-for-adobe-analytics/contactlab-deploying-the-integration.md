---
description: valeur nulle
seo-description: valeur nulle
seo-title: Deploying the Integration
solution: Analytics
title: Deploying the Integration
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# Deploying the Integration{#deploying-the-integration}

Deploying this integration is a simple process that requires the following actions:

## Complete the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Steps to complete the integration wizard in the Data Connectors interface.

1. Navigate to the Data Connectors (formerly Genesis) area within the Adobe Experience Cloud.
1. Launch the ContactLab integration wizard.
1. Choose the desired Report Suite and provide a name for the integration.
1. Configure the following items:

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal |
   | Description | (Optional) Description for this integration setup |

1. Configurez les éléments **[!UICONTROL de mappage]** de variables suivants :

   | Élément | Description |
   |---|---|
   | ID de lien | Sélectionnez une eVar pour la collecte des ID de lien en temps réel. |
   | Message ID | Sélectionnez une eVar pour la collecte des ID de message en temps réel. |
   | Recipient ID | Sélectionnez une eVar pour la collecte des ID de destinataire en temps réel. |
   | Retours | Sélectionnez un événement numérique pour recevoir les rebonds quotidiens de ContactLab. |
   | Envoyé | Sélectionnez un événement numérique pour recevoir des envois quotidiens de ContactLab. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir le total quotidien des clics de ContactLab. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le total quotidien des ouvertures de ContactLab. |
   | Non abonné | Sélectionnez un événement numérique pour recevoir les désabonnements quotidiens de ContactLab. |

1. Activez l’accès aux données et configurez la collecte de données.
   1. Rename classifications as needed.
   1. **[!UICONTROL Les segments]** partenaires sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous **[!UICONTROL Vos segments]**, sélectionnez les segments personnalisés que vous souhaitez inclure dans cette intégration. Vous pouvez créer d’autres segments personnalisés sous le panneau d’administration.
   1. Sous Demandes **[!UICONTROL d’]** accès, cochez la case pour autoriser l’exportation des informations sur les produits vers ContactLab dans les segments de remarketing quotidien.
   1. Renommez les mesures calculées selon vos besoins.
   1. Configurez si vous collecterez des ID en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez Solution **** automatisée, vous devez inclure les paramètres utilisés dans les liens de courrier électronique pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Vérification de l’intégration{#verifying-the-integration}

Afficher votre configuration de l’intégration ContactLab dans Adobe Experience Cloud

1. Affichez le journal des activités d’intégration.
   1. Dans Adobe Experience Cloud, accédez à **[!UICONTROL Support]** &gt; Journal **[!UICONTROL d’activité]** d’intégration.

      ![](assets/integration_activity_log.png)

   1. Recherchez les entrées telles que Données **[!UICONTROL de classification importées avec succès]**, Données **[!UICONTROL de mesures importées avec succès]** et Données de **[!UICONTROL mesures exportées avec succès]**. Ces entrées doivent apparaître dans le délai d’un jour suivant le déploiement.
1. Affichez vos données de création de rapports dans Adobe Analytics.
   1. Accédez à Conversion **** personnalisée &gt; Conversion **[!UICONTROL personnalisée 1-10]** &gt; Rapports **[!UICONTROL d’ID de]** message.

      ![](assets/reporting.png)

   1. Recherchez la création de rapports ContactLab.  Ces données doivent apparaître dans les 24 à 48 heures suivant le déploiement.