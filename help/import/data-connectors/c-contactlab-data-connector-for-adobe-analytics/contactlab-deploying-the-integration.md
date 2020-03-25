---
description: valeur nulle
title: Déploiement de l’intégration
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration {#deploying-the-integration}

Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes :

## Finalisation de l’assistant d’intégration Adobe {#completing-the-adobe-integration-wizard}

Procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des Data Connectors.

1. Accédez à la zone des Data Connectors (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l’assistant d’intégration de ContactLab.
1. Choisissez une suite de rapports et attribuez un nom à l’intégration.
1. Renseignez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique principale du contact. |
   | Description | (Facultatif) Description de cette configuration d’intégration. |

1. Configurez les éléments de **[!UICONTROL mappage de variables]** suivants :

   | Élément | Description |
   |---|---|
   | ID de lien | Sélectionnez une eVar pour la collecte des ID de lien en temps réel. |
   | ID de message | Sélectionnez une eVar pour la collecte des ID de message en temps réel. |
   | Recipient ID | Sélectionnez une eVar pour la collecte des ID de destinataire en temps réel. |
   | Retours | Sélectionnez un événement numérique pour recevoir les rebonds quotidiens de ContactLab. |
   | Envoyé | Sélectionnez un événement numérique pour recevoir les envois quotidiens de ContactLab. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir le nombre total de clics quotidiens de ContactLab. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le nombre total d’ouvertures quotidiennes de ContactLab. |
   | Désabonné | Sélectionnez un événement numérique pour recevoir les désabonnements quotidiens de ContactLab. |

1. Activez l’accès aux données et configurez la collecte de données.
   1. Renommez les classifications si nécessaire.
   1. Les **[!UICONTROL segments de partenaire]** sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous la section **[!UICONTROL Vos segments]**, sélectionnez les segments personnalisés que vous souhaitez inclure dans cette intégration. Vous pouvez créer d’autres segments personnalisés dans le panneau d’administration.
   1. Sous la section **[!UICONTROL Demandes d’accès]**, cochez la case pour autoriser l’exportation des informations sur les produits vers ContactLab dans les segments de remarketing quotidiens.
   1. Renommez les mesures calculées selon vos besoins.
   1. Indiquez si vous souhaitez collecter les ID en mettant à jour manuellement votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez **[!UICONTROL Solution automatisée]**, vous devez inclure les paramètres utilisés dans les liens d’e-mail pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Vérification de l’intégration {#verifying-the-integration}

Affichage de votre configuration d’intégration ContactLab dans Adobe Experience Cloud

1. Affichez le journal d’activité d’intégration.
   1. Dans Adobe Experience Cloud, accédez à **[!UICONTROL Assistance]** > **[!UICONTROL Journal d’activité d’intégration]**.

      ![](assets/integration_activity_log.png)

   1. Recherchez les entrées telles que **[!UICONTROL Données de classification importées]**, **[!UICONTROL Données de mesures importées]** et **[!UICONTROL Données de mesures exportées]**. Ces entrées doivent apparaître pendant la journée suivant le déploiement.
1. Affichez vos données de création de rapports dans Adobe Analytics.
   1. Accédez à **[!UICONTROL Conversion personnalisée]** > **[!UICONTROL Conversion personnalisée 1-10]** > **[!UICONTROL Rapports d’ID de message]**.

      ![](assets/reporting.png)

   1. Recherchez les rapports de ContactLab. Ces données doivent apparaître dans les 24 à 48 heures suivant le déploiement.
