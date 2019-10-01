---
description: valeur nulle
seo-description: valeur nulle
seo-title: Déploiement de l’intégration
solution: Analytics
title: Déploiement de l’intégration
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# Déploiement de l’intégration{#deploying-the-integration}

Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes :

## Fin de l’assistant d’intégration Adobe{#completing-the-adobe-integration-wizard}

Cette section décrit la procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l'assistant d'intégration ContactLab.
1. Choisissez une suite de rapports et nommez l’intégration.
1. Configurez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal |
   | Description | (Facultatif) Description de cette configuration d’intégration |

1. Configurez les éléments **[!UICONTROL de mappage]** de variables suivants :

   | Élément | Description |
   |---|---|
   | ID de lien | Sélectionnez une eVar pour la collecte des ID de lien en temps réel. |
   | ID du message | Sélectionnez une eVar pour la collecte des ID de message en temps réel. |
   | Recipient ID | Sélectionnez une eVar pour la collecte des ID de destinataire en temps réel. |
   | Retours | Sélectionnez un événement numérique pour recevoir les rebonds quotidiens de ContactLab. |
   | Envoyé | Sélectionnez un événement numérique pour recevoir des envois quotidiens de ContactLab. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir le total quotidien des clics de ContactLab. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le total quotidien des ouvertures de ContactLab. |
   | Non abonné | Sélectionnez un événement numérique pour recevoir les désabonnements quotidiens de ContactLab. |

1. Activez l’accès aux données et configurez la collecte de données.
   1. Renommez les classifications selon vos besoins.
   1. **[!UICONTROL Les segments]** partenaires sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous **[!UICONTROL Vos segments]**, sélectionnez les segments personnalisés que vous souhaitez inclure dans cette intégration. Vous pouvez créer d’autres segments personnalisés sous le panneau d’administration.
   1. Sous Demandes **[!UICONTROL d’]** accès, cochez la case pour autoriser l’exportation des informations sur les produits vers ContactLab dans les segments de remarketing quotidien.
   1. Renommez les mesures calculées selon vos besoins.
   1. Configurez si vous collecterez des ID en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. If you select Automated Solution, you must include the parameters that are used in email links to pass ID’s.****
1. Review all configuration items and click Activate Now.****

## Verify the Integration{#verifying-the-integration}

View your ContactLab integration setup within the Adobe Experience Cloud

1. View the integration activity log.

   1. In the Adobe Experience Cloud, navigate to Support &gt; Integration Activity Log.********

      ![](assets/integration_activity_log.png)

   1. Look for entries like Classification Data imported successfully, Metrics Data imported successfully, and Metric Data exported successfully. ************ These entries should appear within 1 day of successful deployment.
1. View your reporting data within Adobe Analytics.

   1. Navigate to Custom Conversion &gt; Custom Conversion 1-10 &gt; Message ID Reports.************

      ![](assets/reporting.png)

   1. Look for ContactLab reporting. This data should appear within 24-48 hours of successful deployment.