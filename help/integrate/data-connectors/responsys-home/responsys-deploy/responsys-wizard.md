---
description: Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.
seo-description: Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.
seo-title: Exécution de l'assistant d'intégration Adobe
solution: Analytics
title: Exécution de l'assistant d'intégration Adobe
uuid: fb 106251-78 cf -4 a 2 a -8 ba 2-2 a 39188 ba 910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Marketing Cloud.
1. Lancez l'assistant d'intégration de Responsys.
1. Choisissez la suite de rapports souhaitée et attribuez un nom à l'intégration.
1. Configurez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal |
   | Description | (Facultatif) Description de cette configuration de l'intégration |
   | ID de compte | Obtenue en contactant l'équipe d'assistance Responsys à l'adresse support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | Élément | Description |
   |---|---|
   | ID de message | Sélectionnez une evar pour la collecte de l'ID de message en réel - heure. |
   | Recipient ID | Sélectionnez une evar pour la collecte de l'ID de destinataire en réel. |
   | Nombre total de rebonds | Sélectionnez un événement numérique pour recevoir quotidiennement des rebonds auprès de Responsys. |
   | Envoi par courrier électronique | Sélectionnez un événement numérique pour recevoir quotidiennement des envois de participants. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir les clics totaux quotidiens depuis l'élément Responsys. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir le total quotidien des ouvertures de sondes. |
   | Désabonné | Sélectionnez un événement numérique qui sera retiré quotidiennement de la fonction Responsys. |
   | Livré | Sélectionnez un événement numérique pour recevoir quotidiennement les remises de Responsys. |

1. Activez l'accès aux données et configurez la collecte de données.
   1. Renommez les classifications selon vos besoins.
   1. **[!UICONTROL Les segments]** partenaires sont des segments de remarketing standard inclus dans votre intégration.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. Configurez si vous collectez des identifiants en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
