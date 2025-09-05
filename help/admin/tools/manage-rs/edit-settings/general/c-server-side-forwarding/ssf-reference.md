---
description: Une liste complète et des descriptions des variables de configuration, des en-têtes HTTP et des signaux de données dans les appels au transfert côté serveur.
title: Données et référence de code du transfert côté serveur
feature: Report Suite Settings
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 99%

---

# Données et référence de code du transfert côté serveur

Une liste complète et des descriptions des variables de configuration, des en-têtes HTTP et des signaux de données dans les appels au transfert côté serveur.

## Variables de configuration {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Les paramètres dotés du préfixe `d_*` identifient des paires clé-valeur spéciales au niveau du système utilisées par nos [serveurs de collecte de données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=fr) (DCS). Voir aussi [Supported Attributes for DCS API calls (Attributs pris en charge pour les appels de l’API DCS)](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=fr).

| Paramètre | Description |
|--- |--- |
| `d_rs` | (Défini à l’aide du transfert côté serveur hérité/basé sur un serveur de suivi) <br>Défini sur les suites de rapports transmises avec l’accès à Analytics. |
| `d_dst_filter` | (Défini à l’aide du transfert côté serveur basé sur une suite de rapports) <br>Défini sur les ID de suite de rapports transmises avec l’accès à Analytics. |
| `d_dst` | Définit `d_dst=1`  <br>si la demande envoyée à Analytics s’attend à ce que du contenu relatif à la destination soit renvoyé au client. |
| `d_mid` | Experience Cloud ID transmis à Analytics. |

## En-têtes HTTP {#section_0549705E76004F9585224AEF872066C0}

Ces en-têtes sont des champs contenant des informations telles que des demandes de données et de réponses d’un appel HTTP.

| En-tête HTTP | Description | Clé h_ acceptée par Audience Manager |
| --- | --- | --- |
| Hôte | Défini sur le nom d’hôte de la collecte de données spécifique du client indiqué dans le fichier de configuration de l’hôte Analytics. Il apparaît sous la forme `host name .demdex.net`. Voir [Signification des appels vers le domaine Demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=fr). | `h_host` |
| User-Agent | Défini sur l’en-tête User-Agent transmis à Analytics. | `h_user-agent` |
| Accept-Language | Défini sur l’en-tête `Accept-Language` transmis à Analytics. | `h_accept-language` |
| Referer | Définit sur l’URL de la page transmise à Analytics ou collectée à partir de l’en-tête `Referer` transmis à Analytics. | `h_referer` |
| Référent | Définit sur l’URL de la page transmise à Analytics ou collectée à partir de l’en-tête `Referrer` transmis à Analytics. | `h_referrer` |
| Date | Définit sur l’en-tête `Date` transmis à Analytics. | `h_date` |

En outre, un signal `h_ip` est généré à partir de l’adresse IP de l’hôte qui envoie la requête au serveur de collecte de données.

## Signaux définis par le client {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Les paramètres dotés du préfixe `c_` identifient les variables définies par le client. Voir aussi [Attributs pris en charge pour les appels de l’API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=fr).

| Signal | Description |
| --- |--- |
| `c_browserWidth` et `c_browserHeight` | Largeur et hauteur de la fenêtre du navigateur. |
| `c_campaign` | Défini par `s.campaign`. |
| `c_channel` | Défini par `s.channel`. |
| `c_clientDateTime` | Horodatage au format `dd/mm/yyy hh:mm:ss  W TZ`. `TZ` est exprimé en minutes et correspond au retour de la méthode `Date.getTimezoneOffset`. |
| `c_colorDepth` | Spécifié en tant que couleur 16 ou 32 bits. |
| `c_connectionType` | Indique le type de connexion. Les options incluent :<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Exemples :<ul><li>AppMeasurement : `s.contextData`</li><li>[category] = « news » ;</li><li>Signal : `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Indique si les cookies peuvent être activés. Les options incluent : oui, non, inconnu |
| `c_currencyCode` | Type de devise utilisé pour la transaction. |
| `c_evar#` | eVars personnalisées |
| `c_events` | Défini par `s.events`. |
| `c_hier#` | Variables de hiérarchie personnalisées. |
| `c_javaEnabled` | Indique si Java peut être activé. Les options incluent : oui, non, inconnu |
| `c_javaScriptVersion` | Version de JavaScript prise en charge par un navigateur. |
| `c_latitude` | Latitude numérique |
| `c_linkClick` | Les options incluent : personnalisé, télécharger une sortie |
| `c_linkCustomName` | Nom personnalisé (le cas échéant) fourni pour le lien. |
| `c_linkDownloadURL` | URL des liens de téléchargement. |
| `c_linkExitURL` | URL du lien de sortie. |
| `c_list#` | Variables de liste personnalisées. |
| `c_longitude` | Longitude numérique. |
| `c_mediaPlayerType` | Pour les demandes de suivi du flux multimédia. Les options incluent : autre, primetime |
| `c_pageName` | Nom de la page (si défini). |
| `c_pageURL` | Adresse de la page dans la barre d’adresse du navigateur. |
| `c_products` | Chaîne de produit (définie par `s.products`). |
| `c_prop` | Props personnalisées. |
| `c_purchaseID` | ID unique pour l’achat. |
| `c_referrer` | Page précédant la page active. |
| `c_screenResolution` | Largeur et hauteur de l’écran (en pixels). |
| `c_server` | Nom du serveur web (défini par `s.server`). |
| `c_state` | Région géographique (définie par `s.state`). |
| `c_timezone` | Décalage horaire (en heures). |
| `c_transactionID` | ID unique pour une transaction. |
| `c_zip` | Code postal (défini par `s.zip`). |
