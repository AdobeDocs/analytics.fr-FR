---
description: Pour activer l'intégration, vous devez terminer l'assistant d'intégration Qualtrics dans l'interface Connecteurs de données
seo-description: Pour activer l'intégration, vous devez terminer l'assistant d'intégration Qualtrics dans l'interface Connecteurs de données
seo-title: Exécution de l'assistant d'intégration Adobe
solution: Analytics
subtopic: Qualtrics
title: Exécution de l'assistant d'intégration Adobe
topic: Connecteurs de données
uuid: e 065 fba 4-1 fe 1-4 e 25-9 c 45-6 c 52 dc 20 f 81 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Exécution de l'assistant d'intégration Adobe{#completing-the-adobe-integration-wizard}

Pour activer l'intégration, vous devez terminer l'assistant d'intégration Qualtrics dans l'interface Connecteurs de données

1. Accédez aux connecteurs de données et lancez l'assistant d'intégration Qualtrics. ([Aide sur les connecteurs de données](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. Sélectionnez la suite de rapports à utiliser pour cette intégration et attribuez un nom.

   Terminez l'assistant d'intégration, en fournissant les informations décrites dans les étapes suivantes. 1. **Assistant Etape 1**

   | Email Address | Adresse électronique de contact principale. |
   |---|---|
   | Description | (Facultatif) Description de cette configuration de l'intégration. |
   | ID d'organisation Qualtrics | [Recherche de votre ID d'organisation Qualtrics](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Jeton Adobe sitecatalyst | [Génération de votre jeton Qualtrics Adobe Analytics](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. ** Assistant Etape 2 - Correspondances de variables**

   | Liste de réponses Qualtrics | Sélectionnez une variable de liste disponible dans votre suite de rapports. (Vous devrez peut-être activer une nouvelle variable listvar dans le Gestionnaire de Report Suites.) |
   |---|---|
   | Qualtrics Response ID | Sélectionnez une evar ou prop disponible dans votre suite de rapports. (Vous devrez peut-être activer une nouvelle variable listvar dans le Gestionnaire de Report Suites.) |
   | Serveur de suivi | Fournissez le paramètre de serveur de suivi (domaine) que vous utilisez pour effectuer le suivi des données Adobe Analytics. Utilisez le serveur `trackingServerSecure` de suivi s'il diffère du paramètre de serveur de suivi standard. |
   | Envois de Qualtrics Survey | Sélectionnez un événement disponible dans votre suite de rapports (vous devrez peut-être activer un nouvel événement depuis le Gestionnaire de Report Suites). |

1. **Assistant 3**: Rien n'est requis, informations uniquement.

   Résultat 1. ** Assistant Etape 4 - Paramètres d'exportation**

   | eVar | Sélectionnez jusqu'à cinq de vos evars à exposer pour l'exportation vers Qualtrics. |
   |---|---|
   | Requête  | Sélectionnez jusqu'à cinq de vos événements personnalisés à exposer pour l'exportation vers Qualtrics. |
   | Propriétés | Sélectionnez jusqu'à cinq de vos props à exposer pour l'exportation vers Qualtrics. |
   | Demandes d'accès | Cochez la case correspondant aux mesures et dimensions standard que vous souhaitez exporter vers Qualtrics. Le `visitor_id` paramètre est requis pour permettre à l'exportation de fonctionner correctement. |

1. **Assistant Etape 5**: Vérifiez la configuration, puis cliquez **[!UICONTROL sur Activer maintenant]**.
