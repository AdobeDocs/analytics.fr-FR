---
description: valeur nulle
title: Déploiement de l’intégration
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration {#deploying-the-integration}

Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes :

## Finalisation de l’assistant d’intégration Adobe {#completing-the-adobe-integration-wizard}

Procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des Data Connectors.

1. Accédez à la zone des Data Connectors (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l’assistant d’intégration de Responsys.
1. Choisissez une suite de rapports et attribuez un nom à l’intégration.
1. Renseignez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique principale du contact. |
   | Description | (Facultatif) Description de cette configuration d’intégration. |
   | ID de compte | Obtenu en contactant l’équipe d’assistance de Reponsys à l’adresse support@responsys.com. |

1. Configurez les éléments de **[!UICONTROL mappage de variables]** suivants :

   | Élément | Description |
   |---|---|
   | ID de message | Sélectionnez une eVar pour la collecte des ID de message en temps réel. |
   | Recipient ID | Sélectionnez une eVar pour la collecte des ID de destinataire en temps réel. |
   | Rebonds au total | Sélectionnez un événement numérique pour recevoir les rebonds quotidiens de Responsys. |
   | E-mails envoyés | Sélectionnez un événement numérique pour recevoir les envois quotidiens de Responsys. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir le nombre de clics quotidiens total de Responsys. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le nombre d’ouvertures quotidiennes total de Responsys. |
   | Désabonné | Sélectionnez un événement numérique pour recevoir les désabonnements quotidiens de Responsys. |
   | Distribué | Sélectionnez un événement numérique pour recevoir les distributions quotidiennes de Responsys. |

1. Activez l’accès aux données et configurez la collecte de données.
   1. Renommez les classifications si nécessaire.
   1. Les **[!UICONTROL segments de partenaire]** sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous **[!UICONTROL Demandes d’accès]**, cochez la case pour autoriser l’exportation des informations sur les produits vers Responsys dans les segments de remarketing quotidien.
   1. Indiquez si vous souhaitez collecter les ID en mettant à jour manuellement votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez **[!UICONTROL Solution automatisée]**, vous devez inclure les paramètres utilisés dans les liens d’e-mail pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

## Configuration dans le système Responsys {#configuring-within-the-responsys-system}

Pour activer l’intégration, vous devez contacter l’assistance de Responsys.

Après avoir exécuté l’assistant d’intégration, vous devez activer l’intégration dans Responsys.

Pour ce faire, veuillez contacter l’équipe d’assistance de Responsys à l’adresse support@responsys.com.
