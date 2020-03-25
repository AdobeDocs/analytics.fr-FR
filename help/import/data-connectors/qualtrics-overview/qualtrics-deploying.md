---
description: Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes.
subtopic: Qualtrics
title: Déploiement de l’intégration
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration {#deploying-the-integration}

Le déploiement de cette intégration est un processus simple qui nécessite les actions suivantes.

## Finalisation de l’assistant d’intégration Adobe {#completing-the-adobe-integration-wizard}

Pour activer l’intégration, vous devez exécuter l’assistant d’intégration Qualtrics dans l’interface des Data Connectors.

1. Accédez aux connecteurs de données et lancez l’assistant d’intégration Qualtrics.
1. Sélectionnez la suite de rapports que vous souhaitez utiliser pour cette intégration et attribuez-lui un nom.

   Finalisez l’assistant d’intégration en fournissant les informations indiquées dans les étapes suivantes. 1. **Étape 1 de l’assistant**

   | Adresse électronique | Adresse électronique principale du contact. |
   |---|---|
   | Description | (Facultatif) Description de cette configuration d’intégration. |
   | ID d’organisation Qualtrics | [Recherche de votre ID d’organisation Qualtrics](../qualtrics-overview/qualtrics-org-id.md) |
   | Jeton Adobe SiteCatalyst | [Génération de votre jeton Adobe Analytics Qualtrics](../qualtrics-overview/qualtrics-token.md) |

1. **Étape 2 de l’assistant : correspondances de variables**
|  Liste des réponses Qualtrics  | Sélectionnez une variable de liste disponible dans votre suite de rapports. (Vous aurez sans doute besoin d’activer une nouvelle listVar dans le Gestionnaire de suite de rapports.)  |
|---|---|
|  ID de réponse Qualtrics  | Sélectionnez une eVar ou une prop disponible dans votre suite de rapports. (Vous aurez sans doute besoin d’activer une nouvelle listVar dans le Gestionnaire de suite de rapports.)  |
|  Serveur de suivi  |Indiquez le paramètre du serveur de suivi (domaine) que vous utilisez pour effectuer le suivi des données Adobe Analytics. Utilisez le serveur de suivi `trackingServerSecure` s’il diffère du paramètre de serveur de suivi standard.  |
|  Envois d’enquête Qualtrics  | Sélectionnez un événement disponible dans votre suite de rapports (vous aurez sans doute besoin d’activer un nouvel événement dans le Gestionnaire de suite de rapports).  |

1. **Étape 3 de l’assistant** : aucune action n’est requise, étape informative uniquement.

   Résultat de l’étape 1. **Étape 4 de l’assistant : paramètres d’exportation**

   | eVar | Sélectionnez jusqu’à cinq de vos eVars à exposer pour l’exportation vers Qualtrics. |
   |---|---|
   | Événements | Sélectionnez jusqu’à cinq de vos événements personnalisés à exposer pour l’exportation vers Qualtrics. |
   | Propriétés | Sélectionnez jusqu’à cinq de vos Props à exposer pour l’exportation vers Qualtrics. |
   | Demandes d’accès | Cochez la case correspondant aux mesures et dimensions standard que vous souhaitez exporter vers Qualtrics. Le `visitor_id` est requis pour assurer le bon déroulement de l’exportation. |

1. **Étape 5 de l’assistant** : vérifiez la configuration, puis cliquez sur **[!UICONTROL Activer maintenant]**.

## Activation de l’intégration dans Qualtrics Research Suite {#enabling-the-integration-in-qualtrics-research-suite}

Après avoir finalisé l’assistant d’intégration, vous devez activer l’intégration pour chaque enquête Qualtrics que vous souhaitez connecter.

1. Connectez-vous à Qualtrics Research Suite.
1. Dans l’onglet **[!UICONTROL Mes enquêtes]**, cliquez sur le bouton **[!UICONTROL Modifier]** de l’enquête que vous souhaitez intégrer.
1. Cliquez sur le menu **[!UICONTROL Options avancées]**, puis sélectionnez **[!UICONTROL Adobe Analytics]**. (Si cette option n’apparaît pas, demandez à votre administrateur de vous octroyer les autorisations nécessaires.).

   ![](assets/advanced_options.png)

1. Sélectionnez la configuration d’Adobe Analytics, puis cliquez sur **[!UICONTROL Enregistrer]**. Si aucune configuration n’est disponible, il est probable que vous n’ayez pas encore finalisé l’assistant d’intégration Adobe.
   1. La case à cocher **[!UICONTROL Inclure les réponses partielles]** permet d’indiquer que vous souhaitez capturer des données dans Adobe Analytics après chaque écran d’enquête partielle. Si elle n’est pas cochée, les données sont transférées uniquement pour les enquêtes entièrement terminées.
   1. La case à cocher **[!UICONTROL Envoyer l’horodatage avec balise]** ne doit être utilisée que lors de l’intégration à une suite de rapports configurée pour recevoir des données horodatées (ce qui est rare).
   ![](assets/integration_config.png)

## Vérification de l’intégration {#verifying-the-integration}

Une fois toutes les étapes de déploiement terminées, vous pouvez vérifier que l’intégration transfère bien des données.

1. **Journal d’activité d’intégration** : dans l’interface utilisateur des Data Connectors, affichez l’onglet **[!UICONTROL Assistance]** sur l’intégration de Qualtrics. Sous l’en-tête **[!UICONTROL Journal d’activité d’intégration]**, vous devriez voir les entrées indiquant les données de classification importées.

   >[!NOTE]
   >
   >Ces entrées doivent apparaître dans l’heure suivant le déploiement.

   ![](assets/verify-1.png)

1. **Données de création de rapports** : affichez vos rapports d’enquête Qualtrics grâce à l’interface utilisateur de Marketing Reports and Analytics en accédant aux rapports d’enquête Qualtrics (sous **[!UICONTROL Variables de liste]**).

   >[!NOTE]
   >
   >Ces données doivent apparaître dans les 24 à 48 heures suivant le déploiement, en supposant que l’enquête intégrée reçoive activement des réponses.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


