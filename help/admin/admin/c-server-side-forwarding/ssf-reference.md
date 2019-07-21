---
description: Une liste complète et des descriptions des variables de configuration, des en-têtes HTTP et des signaux de données dans les appels au transfert côté serveur.
seo-description: Une liste complète et des descriptions des variables de configuration, des en-têtes HTTP et des signaux de données dans les appels au transfert côté serveur.
seo-title: Transfert de données et de référence côté serveur
title: Transfert de données et de référence côté serveur
uuid: 3 eb 3 ea 0 f-a 530-448 d-bba 5-6408 b 2490 dc 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Transfert de données et de référence côté serveur

Une liste complète et des descriptions des variables de configuration, des en-têtes HTTP et des signaux de données dans les appels au transfert côté serveur.

## Variables de configuration {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). Voir aussi [Supported Attributes for DCS API calls (Attributs pris en charge pour les appels de l’API DCS)](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Paramètre | Description |
|--- |--- |
| d_rs | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| d_dst_filter | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
| d_dst | Définissez d_dst=1<br> si la demande envoyée à Analytics s’attend à ce que du contenu relatif à la destination soit renvoyé au client. |
| d_mid | Experience Cloud ID transmis à Analytics. |

## En-têtes HTTP {#section_0549705E76004F9585224AEF872066C0}

Ces en-têtes sont des champs contenant des informations telles que des demandes de données et de réponses d’un appel HTTP.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| En-tête HTTP | Description |
|--- |--- |
| Hôte | Défini sur le nom d’hôte de la collecte de données spécifique du client indiqué dans le fichier de configuration de l’hôte Analytics. Il apparaît sous la forme   `host name .demdex.net` .  Voir Signification des appels vers le domaine Demdex (Understanding Calls to the Demdex Domain). |
| User-Agent | Défini sur l’en-tête User-Agent transmis à Analytics. |
| X-Original-User-Agent | Only set if an alternate user agent was specified by one of these headers: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | Défini sur l’adresse IP du client demandeur. Analytics a déjà analysé l’en-tête `X-Forwarded-For` entrant et déterminé l’adresse IP correcte à utiliser. |
| Accept-Language | Défini sur l’en-tête `Accept-Language` transmis à Analytics. |
| Referer | Défini l’URL de la page transmise à Analytics ou collectée à partir de l’en-tête Referer transmis à Analytics. |

## Signaux définis par le client {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_` identify customer-defined variables. Voir aussi [Attributs pris en charge pour les appels de l’API DCS](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Signal | Description |
|--- |--- |
| c_browserWidth et c_browserHeight | Largeur et hauteur de la fenêtre du navigateur. |
| c_campaign | Défini par s.campaign . |
| c_channel | Défini par s.channel . |
| c_clientDateTime | Horodatage au format jj/mm/aaa : mm : ss W TZ. TZ est exprimé en minutes et correspond au retour de la méthode Date.getTimezoneOffset. |
| c_colorDepth | Spécifié en tant que couleur 16 ou 32 bits. |
| c_connectionType | Indique le type de connexion. Les options incluent :<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Exemples :<ul><li>Appmeasurement : s. contextdata</li><li>[« category »] = « news » ;</li><li>Signal : c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Indique si les cookies peuvent être activés. Les options incluent : oui, non, inconnu |
| c_currencyCode | Type de devise utilisé pour la transaction. |
| c_evar# | eVars personnalisées |
| c_events | Défini par s.events . |
| c_hier# | Variables de hiérarchie personnalisées. |
| c_javaEnabled | Indique si Java peut être activé. Les options incluent : oui, non, inconnu |
| c_javaScriptVersion | Version de JavaScript prise en charge par un navigateur. |
| c_latitude | Latitude numérique |
| c_linkClick | Les options incluent : sortie personnalisée, sortie |
| c_linkCustomName | Nom personnalisé (le cas échéant) fourni pour le lien. |
| c_linkDownloadURL | URL des liens de téléchargement. |
| c_linkExitURL | URL du lien de sortie. |
| c_list# | Variables de liste personnalisées. |
| c_longitude | Longitude numérique. |
| c_mediaPlayerType | Pour les demandes de suivi du flux multimédia. Les options incluent :  other, primetime |
| c_pageName | Nom de la page (si défini). |
| c_pageURL | Adresse de la page dans la barre d’adresse du navigateur. |
| c_products | Chaîne de produit (définie par s.products ). |
| c_prop | Props personnalisées. |
| c_purchaseID | Identifiant unique pour l’achat. |
| c_referrer | Page précédant la page active. |
| c_screenResolution | Largeur et hauteur de l’écran (en pixels). |
| c_server | Nom du serveur web (défini par s.server ). |
| c_state | Région géographique (définie par s.state ). |
| c_timezone | Décalage horaire (en heures). |
| c_transactionID | Identifiant unique pour une transaction. |
| c_zip | Code postal (défini par s.zip ). |
