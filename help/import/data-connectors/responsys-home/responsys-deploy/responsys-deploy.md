---
description: valeur nulle
title: Déploiement de l’intégration
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration{#deploying-the-integration}

Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes :

## Fin de l’assistant d’intégration Adobe{#completing-the-adobe-integration-wizard}

Cette section décrit la procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l’assistant d’intégration de Responsys.
1. Choisissez une suite de rapports et nommez l’intégration.
1. Configurez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal |
   | Description | (Facultatif) Description de cette configuration d’intégration |
   | ID de compte | Obtenu en contactant l’équipe d’assistance de Réponsys à l’adresse support@responsys.com |

1. Configurez les éléments **[!UICONTROL de mappage]** de variables suivants :

   | Élément | Description |
   |---|---|
   | ID du message | Sélectionnez une eVar pour la collecte des ID de message en temps réel. |
   | Recipient ID | Sélectionnez une eVar pour la collecte des ID de destinataire en temps réel. |
   | Rebonds totaux | Sélectionnez un événement numérique pour recevoir les retours quotidiens de Responsys. |
   | Courrier électronique envoyé | Sélectionnez un événement numérique pour recevoir des envois quotidiens de Responsys. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir le total quotidien des clics à partir de Réponsys. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le total quotidien des ouvertures à partir de Responsys. |
   | Non abonné | Sélectionnez un événement numérique pour recevoir les désabonnements quotidiens de Responsys. |
   | Livré | Sélectionnez un événement numérique pour recevoir les livraisons quotidiennes de Responsys. |

1. Activez l’accès aux données et configurez la collecte de données.
   1. Renommez les classifications selon vos besoins.
   1. **[!UICONTROL Les segments]** partenaires sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous Demandes **[!UICONTROL d’]** accès, cochez la case pour autoriser l’exportation des informations sur le produit vers Responsys dans les segments de remarketing quotidien.
   1. Configurez si vous collecterez des ID en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez Solution **** automatisée, vous devez inclure les paramètres utilisés dans les liens de courrier électronique pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Configuration dans le système Responsys{#configuring-within-the-responsys-system}

L’activation de l’intégration implique de contacter l’assistance de Réponsys.

Après avoir exécuté l’assistant d’intégration, vous devez activer l’intégration dans Responsys.

Pour ce faire, veuillez contacter l’équipe d’assistance de Responsys à l’adresse support@responsys.com.
