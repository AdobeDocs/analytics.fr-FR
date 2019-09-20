---
description: Cette section décrit la procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des connecteurs de données.
seo-description: Cette section décrit la procédure à suivre pour exécuter l’assistant d’intégration dans l’interface des connecteurs de données.
seo-title: Fin de l’assistant d’intégration Adobe
solution: Analytics
title: Fin de l’assistant d’intégration Adobe
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Fin de l’assistant d’intégration Adobe{#completing-the-adobe-integration-wizard}

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
   1. Configurez si vous collecterez des ID en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez Solution **** automatisée, vous devez inclure les paramètres utilisés dans les liens de courrier électronique pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.
