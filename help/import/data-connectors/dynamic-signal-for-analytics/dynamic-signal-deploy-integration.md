---
description: valeur nulle
title: Déploiement de l’intégration
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Déploiement de l’intégration{#deploying-the-integration}

Le déploiement de cette intégration est un processus simple consistant à exécuter l’assistant d’intégration Adobe et à vérifier l’intégration.

## Fin de l’assistant d’intégration Adobe{#completing-the-adobe-integration-wizard}

Cette section décrit la procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l’assistant d’intégration du signal dynamique.
1. Choisissez une suite de rapports et nommez l’intégration.
1. Configurez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal. |
   | Description | (Facultatif) Description de cette configuration d’intégration. |
   | ID de communauté | Vous pouvez obtenir cet identifiant auprès de votre représentant de signal dynamique. |

1. Configurez les éléments **[!UICONTROL de mappage]** de variables suivants :

   | Élément | Description |
   |---|---|
   | Code de suivi | Sélectionnez une variable eVar disponible dans votre suite de rapports. |

1. Examinez les classifications qui seront créées pour cette intégration.
1. Cochez la case pour créer le tableau de bord de l’intégration du signal dynamique (facultatif, mais vivement recommandé).
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.
1. **Important**: Une fois que vous avez terminé l’assistant, vous devez en informer votre représentant de signal dynamique afin qu’il puisse activer l’intégration sur la plate-forme VoiceStorm.

## Vérification de l’intégration{#verifying-the-integration}

Etapes d’affichage de la configuration de l’intégration VoiceStorm de signal dynamique dans Adobe Experience Cloud

1. Affichez la configuration de l’intégration du signal dynamique dans le journal des activités d’intégration.
   1. Dans Adobe Experience Cloud, accédez à **[!UICONTROL Support]** &gt; Journal **[!UICONTROL d’activité]** d’intégration.

      ![](assets/integration_activity_log.png)

   1. Recherchez les entrées telles que Données **[!UICONTROL de classification importées avec succès]**. Ces entrées doivent apparaître dans les 24 heures suivant le déploiement.
1. Consultez vos rapports de signature dynamique dans Adobe Analytics à l’aide du tableau de bord qui a été automatiquement créé pour vous à l’aide de l’assistant d’intégration Adobe (Etape 7). Vous pouvez également accéder aux rapports Signal dynamique dans la structure de menu d’Adobe Analytics ; reportez-vous aux captures d’écran suivantes.

   **Remarque**:Ces données doivent apparaître dans les 24 à 48 heures suivant le déploiement.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
