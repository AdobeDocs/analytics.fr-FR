---
description: Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.
seo-description: Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.
seo-title: Exécution de l'assistant d'intégration Adobe
solution: Analytics
title: Exécution de l'assistant d'intégration Adobe
uuid: a 8135 be 3-fba 3-436 d -8959-faed 40 b 15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Exécution de l'assistant d'intégration Adobe{#completing-the-adobe-integration-wizard}

Etapes permettant de terminer l'assistant d'intégration dans l'interface des Connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Marketing Cloud.
1. Lancez l'assistant d'intégration contactlab.
1. Choisissez la suite de rapports souhaitée et attribuez un nom à l'intégration.
1. Configurez les éléments suivants :

   | Élément | Description |
   |---|---|
   | Adresse électronique | Adresse électronique du contact principal |
   | Description | (Facultatif) Description de cette configuration de l'intégration |

1. Configurez les éléments Mappages **[!UICONTROL de variables]** suivants :

   | Élément | Description |
   |---|---|
   | ID de lien | Sélectionnez une evar pour la collecte de l'ID de lien en réel - heure. |
   | ID de message | Sélectionnez une evar pour la collecte de l'ID de message en réel - heure. |
   | Recipient ID | Sélectionnez une evar pour la collecte de l'ID de destinataire en réel. |
   | Rebonds | Sélectionnez un événement numérique pour recevoir quotidiennement des rebonds à partir de contactlab. |
   | Envoyé | Sélectionnez un événement numérique pour recevoir des envois quotidiens de contactlab. |
   | Cliqué | Sélectionnez un événement numérique pour recevoir les clics totaux quotidiens depuis contactlab. |
   | Ouvert | Sélectionnez un événement numérique pour recevoir un total quotidien des ouvertures de contactlab. |
   | Désabonné | Sélectionnez un événement numérique qui sera retiré quotidiennement de contactlab. |

1. Activez l'accès aux données et configurez la collecte de données.
   1. Renommez les classifications selon vos besoins.
   1. **[!UICONTROL Les segments]** partenaires sont des segments de remarketing standard inclus dans votre intégration.
   1. Sous **[!UICONTROL Vos segments]**, sélectionnez les segments personnalisés que vous souhaitez inclure dans cette intégration. Vous pouvez créer d'autres segments personnalisés sous le panneau d'administration.
   1. Sous **[!UICONTROL Demandes d'accès]**, cochez la case permettant d'exporter les informations sur les produits vers contactlab dans les segments de remarketing quotidiens.
   1. Renommez les mesures calculées selon vos besoins.
   1. Configurez si vous collectez des identifiants en mettant manuellement à jour votre code de collecte Analytics ou en utilisant la solution automatisée. Si vous sélectionnez **[!UICONTROL Solution automatisée]**, vous devez inclure les paramètres utilisés dans les liens de courriel pour transmettre les ID.
1. Vérifiez tous les éléments de configuration et cliquez **[!UICONTROL sur Activer maintenant]**.
