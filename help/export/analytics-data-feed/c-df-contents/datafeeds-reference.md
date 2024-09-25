---
description: Tableau décrivant les colonnes du flux de données.
keywords: Flux de données ; colonnes
subtopic: data feeds
title: Référence des colonnes de données
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 9138a6ae20b5c74a5eaf3b11fb7fcc406d9605e7
workflow-type: tm+mt
source-wordcount: '3580'
ht-degree: 67%

---

# Référence des colonnes de données

Utilisez cette page pour en savoir plus sur les données contenues dans chaque colonne. La plupart des implémentations n’utilisent pas toutes les colonnes. Aussi, vous pouvez vous référer à cette page lorsque vous souhaitez déterminer les colonnes à inclure dans un export de flux de données.

>[!IMPORTANT]
>
>Pour toute colonne donnée (par exemple, une colonne définie sur 255 caractères), un flux de données peut envoyer des caractères supplémentaires en raison de l’ajout de valeurs d’échappement de caractères dans une chaîne. N’oubliez pas de tenir compte de ces caractères supplémentaires potentiels si votre implémentation envoie régulièrement des valeurs dépassant les limites de caractères.

## Colonnes, descriptions et types de données

>[!NOTE]
>
>La plupart des colonnes contiennent une colonne similaire avec un préfixe `post_`. Les colonnes « Post » contiennent les valeurs suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. Pour plus d’informations, consultez la [FAQ sur les flux de données](../df-faq.md).

Vous trouverez les mises à jour précédentes de ce tableau dans la section [historique de validation sur GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) de cette page.

| Nom de la colonne | Description de la colonne | Type de données |
| --- | --- | --- |
| **`accept_language`** | Liste toutes les langues acceptées, comme indiqué dans l’en-tête HTTP Accept-Language lors d’une demande d’image. | char(20) |
| **`adload`** | Chargements des publicités multimédia | varchar(255) |
| **`aemassetid`** | Variable à plusieurs valeurs correspondant aux ID de ressources (GUID) d’un ensemble d’Adobe Experience Manager Assets. Incrémente l’événement Impression. | text |
| **`aemassetsource`** | Identifie la source de l’événement de ressources. Utilisée dans Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID de ressource d’une ressource Adobe Experience Manager. Incrémente l’événement Click. | varchar(255) |
| **`browser`** | Identifiant numérique représentant le navigateur. Fait référence à la table de recherche `browser.tsv`. | int sans signe |
| **`browser_height`** | Dimension [Hauteur du navigateur](/help/components/dimensions/browser-height.md). | smallint sans signe |
| **`browser_width`** | [ Largeur du navigateur ](/help/components/dimensions/browser-width.md) | smallint sans signe |
| **`c_color`** | Codage en bits de la palette de couleurs. Utilisée dans le cadre du calcul de la dimension [Intensité des couleurs](/help/components/dimensions/color-depth.md). AppMeasurement utilise la fonction JavaScript `screen.colorDepth()`. | char(20) |
| **`campaign`** | Dimension [de Code](/help/components/dimensions/tracking-code.md) suivi. | varchar(255) |
| **`carrier`** | Variable d’intégration Adobe Advertising. Définit l’opérateur de téléphonie mobile. Valeur de clé pour la [recherche dynamique](dynamic-lookups.md) `carrier.tsv`. | varchar(100) |
| **`ch_hdr`** | Indications du client collectées via l’en-tête de requête HTTP. | text |
| **`ch_js`** | Indications du client collectées via l’API JavaScript User-Agent Client Hints. | text |
| **`channel`** | Dimension [Sections du site](/help/components/dimensions/site-section.md). | varchar(100) |
| **`clickmaplink`** | Lien d’Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Lien d’Activity Map par région | varchar(255) |
| **`clickmappage`** | Page d’Activity Map | varchar(255) |
| **`clickmapregion`** | Région d’Activity Map | varchar(255) |
| **`code_ver`** | Version du SDK client ou de l’API utilisée pour compiler et envoyer la demande d’image. | char(16) |
| **`color`** | Identifiant d’intensité des couleurs basé sur la valeur de la colonne `c_color`. Fait référence à la table de recherche `color_depth.tsv`. | smallint sans signe |
| **`connection_type`** | Identifiant numérique représentant le type de connexion. La dimension [Type de connexion](/help/components/dimensions/connection-type.md). Fait référence à la table de recherche `connection_type.tsv`. | tinyint sans signe |
| **`cookies`** | La dimension [Prise en charge des cookies](/help/components/dimensions/cookie-support.md).<br>Y : activé<br>N : désactivé<br>U : inconnu | char(1) |
| **`country`** | Identifiant numérique qui représente le pays du visiteur. Fait référence à la table de recherche `country.tsv`. | smallint sans signe |
| **`ct_connect_type`** | Liée à la colonne `connection_type`. Les valeurs les plus courantes sont LAN/Wi-Fi, Opérateur de téléphonie mobile et Modem. | char(20) |
| **`curr_factor`** | Détermine la décimale de la devise et est utilisée pour la conversion de devise. Par exemple, le dollar américain (USD) utilise deux décimales, donc cette valeur de colonne serait `2`. | tinyint |
| **`curr_rate`** | Taux de change au moment de la transaction. Adobe travaille en partenariat avec XE pour déterminer le taux de change du jour. | decimal(24,12) |
| **`currency`** | Code de devise utilisé pendant la transaction. Défini à l’aide de [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Suites de rapports avec horodatage uniquement. Date et l’heure envoyées avec l’accès, basées sur l’heure UNIX®. | int |
| **`cust_visid`** | Identifiant visiteur personnalisé, s’il est défini à l’aide de [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| **`daily_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur quotidien. | tinyint sans signe |
| **`dataprivacyconsentoptin`** | La dimension [Accord préalable de la gestion du consentement](/help/components/dimensions/cm-opt-in.md). Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `DMP` et `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | La dimension [Désinscription de la gestion du consentement](/help/components/dimensions/cm-opt-out.md). Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `SSF`, `DMP` et `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Valeur qui identifie si le consentement est acquis pour envoyer des données d’Adobe Analytics par Adobe Advertising à des fournisseurs publicitaires tiers (tels que Google). Pour plus d’informations, voir [Consentement pour la publicité](/help/components/dimensions/ad-consent.md). | varchar(100) |
| **`date_time`** | Heure de l’accès dans un format lisible, basée sur le fuseau horaire de la suite de rapports. | datetime |
| **`domain`** | Dimension [Domaine](/help/components/dimensions/domain.md) ; En fonction du point d’accès Internet du visiteur. | varchar(100) |
| **`duplicate_events`** | Répertorie chaque événement compté comme double. | varchar(255) |
| **`duplicate_purchase`** | Indicateur qui détermine si l’événement d’achat pour cet accès est ignoré, car il s’agit d’un doublon. | tinyint sans signe |
| **`duplicated_from`** | Utilisée uniquement dans les suites de rapports contenant les règles VISTA de la copie de l’accès. Indique la suite de rapports à partir de laquelle l’accès a été copié. | varchar(40) |
| **`ef_id`** | Le `ef_id` utilisé dans les intégrations Adobe Advertising. | varchar(255) |
| **`evar1 - evar250`** | Variables personnalisées 1-250. Utilisées dans les dimensions [eVar](/help/components/dimensions/evar.md). Chaque organisation utilise les eVars différemment. Pour plus d’informations sur la manière dont votre organisation renseigne les eVars respectives, le meilleur endroit serait un [document de conception de solution](/help/implement/prepare/solution-design.md) spécifique à votre organisation. | varchar(255) |
| **`event_list`** | Liste d’ID numériques séparés par des virgules qui représentent les événements déclenchés sur l’accès. Comprend à la fois les événements par défaut et [les événements personnalisés 1-1000](/help/components/metrics/custom-events.md). Utilise la recherche de `event.tsv`. | text |
| **`exclude_hit`** | Indicateur qui détermine si l’accès est exclu de la création de rapports. La colonne `visit_num` nʼest pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>2 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>3 : n’est plus utilisée. Exclusion de lʼagent utilisateur<br>4 : Exclusion basée sur lʼadresse IP<br>5 : Information indispensable sur lʼaccès manquante telle que `page_url`, `pagename`, `page_event`, ou `event_list`<br>6 : JavaScript nʼa pas traité lʼaccès correctement<br>7 : Exclusion spécifique au compte, comme dans les règles VISTA<br>8 : Inutilisée. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>10 : Code de devise invalide<br>11 : Horodatage manquant sur un accès pour une suite de rapport avec horodatage ou l’accès contenait un horodatage sur une suite de rapport sans horodatage<br>12 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>13 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>14 : Accès cible qui ne correspondait pas à un accès Analytics<br>15 : Inutilisé pour le moment.<br>16 : Accès Advertising Cloud qui ne correspondait pas à un accès Analytics | tinyint sans signe |
| **`first_hit_page_url`** | La toute première URL du visiteur. | varchar(255) |
| **`first_hit_pagename`** | Dimension [Page d’accès d’origine](/help/components/dimensions/entry-dimensions.md). Le nom de la page d’entrée d’origine du visiteur. | varchar(100) |
| **`first_hit_ref_domain`** | La dimension [Domaine référent initial](/help/components/dimensions/original-referring-domain.md) . Basée sur `first_hit_referrer`. Le tout premier domaine référent du visiteur. | varchar(100) |
| **`first_hit_ref_type`** | Identifiant numérique qui représente le type de référent du tout premier référent du visiteur. Fait référence à la table de recherche `referrer_type.tsv`. | tinyint sans signe |
| **`first_hit_referrer`** | La toute première URL de référence du visiteur. | varchar(255) |
| **`first_hit_time_gmt`** | Date et heure du tout premier accès du visiteur ou de la visiteuse (heure UNIX®). | int |
| **`geo_city`** | Nom de la ville d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [Villes](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | Abréviation du pays d’où provient l’accès, selon l’adresse IP. Utilisée dans la dimension [Pays](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | Identifiant numérique de la zone démographique d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [DMA États-Unis](/help/components/dimensions/us-dma.md). | int sans signe |
| **`geo_region`** | Nom de l’état ou de la région d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [Régions](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | Code postal d’où provient l’accès, basé sur l’adresse IP. Aide à renseigner la dimension [Code postal](/help/components/dimensions/zip-code.md). Voir également `zip`. | varchar(16) |
| **`hit_source`** | Source de l’accès. Les sources d’accès 1, 2 et 6 sont facturées. <br>1 : demande d’image standard sans horodatage <br>2 : demande d’image standard avec horodatage <br>3 : chargement de source de données actif avec horodatage <br>4 : inutilisée <br>5 : chargement de source de données générique <br>6 : chargement de source de données de traitement complet <br>7 : chargement de source de données TransactionID <br>8 : n’est plus utilisée ; versions précédentes des sources de données Adobe Advertising Cloud <br>9 : n’est plus utilisée ; mesures de résumé Adobe Social <br>10 : transfert côté serveur Audience Manager utilisé | tinyint sans signe |
| **`hit_time_gmt`** | Date et l’heure des serveurs de collecte de données Adobe ayant reçu l’accès, basé sur l’heure UNIX®. | int |
| **`hitid_high`** | Utilisée en combinaison avec `hitid_low` pour identifier un accès. | bigint sans signe |
| **`hitid_low`** | Utilisé en combinaison avec `hitid_high` pour identifier un accès. | bigint sans signe |
| **`hourly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur horaire. | tinyint sans signe |
| **`ip`** | L’adresse IPv4, basée sur l’en-tête HTTP de la demande d’image. Mutuellement exclusif à `ipv6`. Si cette colonne contient une adresse IP non masquée, `ipv6` est vide. | char(20) |
| **`ipv6`** | L’adresse IPv6 compressée, si disponible. Mutuellement exclusif à `ip`. Si cette colonne contient une adresse IP non masquée, `ip` est vide. | varchar(40) |
| **`j_jscript`** | Version de JavaScript prise en charge par le navigateur. | char(5) |
| **`java_enabled`** | [[!UICONTROL Java activé]](/help/components/dimensions/java-enabled.md). <br>Y : activé <br>N : désactivé <br>U : inconnu | char(1) |
| **`javascript`** | Identifiant de recherche de JavaScript version, basé sur `j_jscript` Fait référence à la table de recherche `javascript_version`. | tinyint sans signe |
| **`language`** | Identifiant numérique représentant la langue du visiteur. Fait référence à la table de recherche `languages.tsv`. | smallint sans signe |
| **`last_hit_time_gmt`** | Date et heure (en heure UNIX®) de l’accès précédent. Utilisée pour calculer la dimension [[!UICONTROL Jours depuis la dernière visite]](/help/components/dimensions/days-since-last-visit.md). | int |
| **`last_purchase_num`** | La dimension [Fidélité de la clientèle](/help/components/dimensions/customer-loyalty.md). Indique le nombre dʼachats précédents effectués par le visiteur. <br>0 : Aucun achat auparavant (n’est pas client) <br>1 : 1 achat précédent (nouveau client) <br>2 : 2 achats précédents (client de retour) <br>3 : 3 achats précédents ou plus (client fidèle) | int sans signe |
| **`last_purchase_time_gmt`** | Utilisée dans la dimension [[!UICONTROL Jours depuis le dernier achat]](/help/components/dimensions/days-since-last-purchase.md). Date et heure (en heure UNIX®) du dernier achat effectué. Pour les premiers achats et les visiteurs qui n’avaient jamais effectué d’achat auparavant, cette valeur est de `0`. | int |
| **`latlon1`** | Lieu (jusqu’à 10 km) | varchar(255) |
| **`latlon23`** | Lieu (jusqu’à 100 m) | varchar(255) |
| **`latlon45`** | Lieu (jusqu’à 1 m) | varchar(255) |
| **`mc_audiences`** | Liste des identifiants de segment Audience Manager auxquels le visiteur appartient. La colonne `post_mc_audiences` change le délimiteur en `--**--`. | text |
| **`mcvisid`** | Identifiant visiteur Experience Cloud. Nombre 128 bits constitué de deux nombres 64 bits concaténés complétés par 19 chiffres. | varchar(255) |
| **`mobile_id`** | Si l’utilisateur ou l’utilisatrice a recours à un appareil mobile, il s’agit alors de l’identifiant numérique de l’appareil. Valeur de clé pour la [recherche dynamique](dynamic-lookups.md) `mobile_attributes.tsv`. | int |
| **`mobileaction`** | Action mobile. Collectée automatiquement lorsque `trackAction` est appelé dans les implémentations mobiles. Permet le cheminement d’action automatique dans l’application. | varchar(100) |
| **`mobileappid`** | ID de l’application mobile Stocke le nom et la version de l’application au format suivant : `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Utilisé dans le connecteur de données Aptelignent. L’identifiant d’application utilisé dans Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Utilisé dans le connecteur de données Aptelignent. L’identifiant de plantage utilisé dans Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Utilisé dans le connecteur de données [!DNL Appfigures]. Identifiant de l’objet de la boutique d’applications. | varchar(255) |
| **`mobilebeaconmajor`** | Relais Mobile Services majeur | varchar(100) |
| **`mobilebeaconminor`** | Relais Mobile Services mineur | varchar(100) |
| **`mobilebeaconproximity`** | Proximité du relais Mobile Services | varchar(255) |
| **`mobilebeaconuuid`** | UUID du relais Mobile Services | varchar(100) |
| **`mobilecampaigncontent`** | Le nom ou l’identifiant du contenu qui a affiché le lien. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| **`mobilecampaignmedium`** | Support marketing, une bannière ou un courrier électronique par exemple. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| **`mobilecampaignname`** | Nom de la campagne, également stocké dans la variable de campagne. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| **`mobilecampaignsource`** | Référent original, comme la newsletter ou les médias sociaux. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| **`mobilecampaignterm`** | Mots-clés ou autres termes payés dont vous souhaitez effectuer le suivi avec cette acquisition. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| **`mobiledayofweek`** | Numéro du jour de la semaine où l’application a été lancée. | varchar(255) |
| **`mobiledayssincefirstuse`** | Nombre de jours depuis que l’application a été lancée pour la première fois. | varchar(255) |
| **`mobiledayssincelastuse`** | Nombre de jours depuis la dernière exécution de l’application. | varchar(255) |
| **`mobiledeeplinkid`** | Collecté à partir de la variable des données de contexte `a.deeplink.id`. Utilisé dans les rapports d’acquisition comme identifiant du lien d’acquisition mobile. | varchar(255) |
| **`mobiledevice`** | Nom de l’appareil mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparés par des virgules. Le premier chiffre représente la génération de l’appareil, le second la famille d’appareils. | varchar(255) |
| **`mobilehourofday`** | Définit l’heure du jour où l’application a été lancée. Suit un format numérique de 24 heures. | varchar(255) |
| **`mobileinstalldate`** | Date de l’installation mobile. Indique la date de la première ouverture d’une application mobile par un utilisateur ou une utilisatrice. | varchar(255) |
| **`mobilelaunchnumber`** | Est incrémentée d’une unité chaque fois que l’application mobile est lancée. | varchar(255) |
| **`mobilemessagebuttonname`** | Collecté à partir de la variable des données de contexte `a.message.button.id`. Utilisé pour la messagerie au sein de l’application afin d’identifier le bouton qui a fermé le message. | varchar(100) |
| **`mobilemessageid`** | Identifiant de message au sein de l’application | varchar(255) |
| **`mobilemessageonline`** | Message en ligne dans l’application | varchar(255) |
| **`mobilemessagepushoptin`** | Collecté à partir de la variable des données de contexte `a.push.optin`. Définissez cette valeur sur « true » lorsque l’utilisateur s’inscrit à la messagerie push ; dans le cas contraire, la valeur qui apparaît est « false ». | varchar(255) |
| **`mobilemessagepushpayloadid`** | Collecté à partir de la variable des données de contexte `a.push.payloadid`. Utilisé comme identifiant de paiement dans la messagerie push. | varchar(255) |
| **`mobileosversion`** | Version du système d’exploitation Mobile Services | varchar(255) |
| **`mobileplaceaccuracy`** | Collecté à partir de la variable des données de contexte `a.loc.acc`. Indique la précision du GPS en mètres au moment de la collecte des données. | varchar(255) |
| **`mobileplacecategory`** | Collecté à partir de la variable des données de contexte `a.loc.category`. Décrit la catégorie d’un lieu en particulier. | varchar(255) |
| **`mobileplaceid`** | Collecté à partir de la variable des données de contexte `a.loc.id`. Identifiant d’un point ciblé donné. | varchar(255) |
| **`mobilepushoptin`** | Abonnement push de Mobile Services | varchar(255) |
| **`mobilepushpayloadid`** | ID de payload push Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Contenu du lancement Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Moyen de lancement de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Source de lancement de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Conditions de lancement de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Collecté à partir de la variable des données de contexte `a.launch.campaign.trackingcode`. Utilisé au moment de l’acquisition comme code de suivi de la campagne de lancement. | varchar(255) |
| **`mobileresolution`** | Résolution de l’appareil mobile. `[Width] x [Height]` en pixels. | varchar(255) |
| **`monthly_visitor`** | Indicateur qui détermine si le visiteur est unique au mois en cours. | tinyint sans signe |
| **`mvvar1`** - `mvvar3` | Valeurs [Variable de liste](/help/implement/vars/page-vars/list.md). Contient une liste délimitée de valeurs personnalisées en fonction de l’implémentation. Les colonnes `post_mvvar1` - `post_mvvar3` remplacent le délimiteur dʼorigine par `--**--`. | text |
| **`mvvar1_instances`** - `mvvar3_instances` | Les valeurs de la variable de liste qui ont été définies sur l’accès actuel. Remplace le délimiteur d’origine par `--**--`. En `post` règle générale, les colonnes ne contiennent pas de données. | text |
| **`new_visit`** | Indicateur qui détermine si l’accès actif est une nouvelle visite. Défini par Adobe après 30 minutes d’inactivité de la visite. | tinyint sans signe |
| **`os`** | Identifiant numérique représentant le système d’exploitation du visiteur. Basé sur la colonne `user_agent`. Valeur de clé pour la recherche standard `operating_system.tsv` et la [recherche dynamique](dynamic-lookups.md) `operating_system_type.tsv`. | int sans signe |
| **`page_event`** | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). Voir [Recherche d’événement de page](datafeeds-page-event.md). | tinyint sans signe |
| **`page_event_var1`** | Uniquement utilisée dans les demandes d’image de suivi des liens. URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. | text |
| **`page_event_var2`** | Uniquement utilisée dans les demandes d’image de suivi des liens. Nom personnalisé (le cas échéant) du lien. Définit le [lien personnalisé](/help/components/dimensions/custom-link.md), le [lien de téléchargement](/help/components/dimensions/download-link.md) ou le [lien de sortie](/help/components/dimensions/exit-link.md) en fonction de la valeur de `page_event`. | varchar(100) |
| **`page_type`** | La [dimension Pages introuvables](/help/components/dimensions/pages-not-found.md) , qui est généralement utilisée pour 404 pages. | char(20) |
| **`page_url`** | URL de l’accès à la Notez qu’il `post_page_url` est supprimé pour les demandes d’image de suivi de lien ([`tl()`](/help/implement/vars/functions/tl-method.md)) et utilise le type de données varchar(255). | text |
| **`pagename`** | Dimension [Page](/help/components/dimensions/page.md). Si la variable [`pagename`](/help/implement/vars/page-vars/pagename.md) est vide, Analytics utilise la variable `page_url` en remplacement. | varchar(100) |
| **`pagename_no_url`** | Similaire à `pagename`, sauf qu’il ne retourne pas à `page_url`. Seule la colonne `post` est disponible. | varchar(100) |
| **`paid_search`** | Indicateur qui détermine si l’accès correspond à la détection de référencement payant. | tinyint sans signe |
| **`persistent_cookie`** | Utilisé dans la dimension [Prise en charge des cookies persistants](/help/components/dimensions/persistent-cookie-support.md). Indique si le visiteur prend en charge les cookies qui ne sont pas ignorés après chaque accès. | char(1) |
| **`pointofinterest`** | Nom du point ciblé Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Distance du centre du point ciblé Mobile Services | varchar(255) |
| Colonnes **`post_`** | Contient la valeur finalement utilisée dans les rapports. Chaque colonne « Post » est renseignée suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. | Voir la colonne « Non post » correspondante. |
| **`product_list`** | La variable de page [`products`](/help/implement/vars/page-vars/products.md). Permet de renseigner plusieurs dimensions et mesures, y compris [Category](/help/components/dimensions/category.md), [Product](/help/components/dimensions/product.md), [Units](/help/components/metrics/units.md) et [Revenue](/help/components/metrics/revenue.md). | text |
| **`prop1`** - `prop75` | Variables de trafic personnalisées 1 - 75. Utilisé dans les dimensions [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identifiant unique pour un achat, tel qu’il est défini à l’aide de la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Utilisé par la colonne `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur trimestriel. | tinyint sans signe |
| **`ref_domain`** | La dimension [Domaine référent](/help/components/dimensions/referring-domain.md). Basé sur la colonne `referrer`. | varchar(100) |
| **`ref_type`** | Identifiant numérique qui représente le type de référence pour l’accès. Utilisé dans la dimension [Type de référent](/help/components/dimensions/referrer-type.md). <br>1 : à l’intérieur de votre site<br>2 : autres sites Web <br>3 : moteurs de recherche <br>4 : disque dur <br>5 : USENET <br>6 : saisi/marqué d’un signet (sans référent) <br>7 : courrier électronique <br>8 : sans JavaScript <br>9 : réseaux sociaux | tinyint sans signe |
| **`referrer`** | Dimension [Référent](/help/components/dimensions/referrer.md). Notez que, bien que `referrer` utilise un type de données varchar(255), `post_referrer` utilise un type de données varchar(244). | varchar(255) |
| **`resolution`** | Identifiant numérique représentant la résolution du moniteur. Utilisé dans la dimension [Résolution d’écran](/help/components/dimensions/monitor-resolution.md). Utilise la table de recherche `resolution.tsv`. | smallint sans signe |
| **`s_kwcid`** | Identifiant du mot-clé dans les intégrations Adobe Advertising. | varchar(255) |
| **`s_resolution`** | Valeur brute de la résolution de l’écran. Collecté à l’aide de la fonction JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | Identifiant numérique qui représente le moteur de recherche qui a renvoyé le visiteur sur votre site. Utilisé dans les dimensions [Moteur de recherche](/help/components/dimensions/search-engine.md). Fait référence à la table de recherche `search_engines.tsv`. | smallint sans signe |
| **`search_page_num`** | Utilisé par la dimension [Tout le classement des pages de recherche](/help/components/dimensions/all-search-page-rank.md). Indique sur quelle page de résultats de recherche votre site est apparu avant que l’utilisateur ou l’utilisatrice ne clique sur votre site. | smallint sans signe |
| **`secondary_hit`** | Indicateur qui détermine si l’accès est un accès secondaire. Cet indicateur provient généralement du balisage multisuite et des règles VISTA qui copient les accès. | tinyint sans signe |
| **`sourceid`** | ID Source | int sans signe |
| **`state`** | Variable d’état. | varchar(50) |
| **`stats_server`** | Inutilisable. Serveur interne d’Adobe qui a traité l’accès. | char(30) |
| **`t_time_info`** | Heure locale pour le visiteur. Le format est : `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Utilisée dans les intégrations Adobe Target. Représente tous les tests actuellement autorisés. Le format est : `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`tnt_action`** | Utilisée dans les intégrations Adobe Target. Représente tous les tests pour lesquels lʼaccès est qualifié. | text |
| **`tnt_instances`** | Utilisée dans les intégrations Adobe Target. Variable d’instances Target. | text |
| **`transactionid`** | Identifiant unique vers lequel plusieurs points de données pourront être chargés plus tard au moyen de sources de données. Collecté à l’aide de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | text |
| **`truncated_hit`** | Indicateur qui indique que la demande d’image a été tronquée. Indique qu’un accès partiel a été reçu. <br>Y : l’accès a été tronqué ; accès partial reçu <br>N : l’accès n’a pas été tronqué ; accès complet reçu | char(1) |
| **`user_agent`** | Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image. | text |
| **`user_hash`** | Inutilisable. Hachage de l’identifiant de suite de rapports. Utilisez `username` à la place. | int sans signe |
| **`user_server`** | Utilisé dans la dimension [Serveur](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Inutilisable. Identifiant numérique pour l’identifiant de suite de rapports. Utilisez `username` à la place. | int sans signe |
| **`username`** | Identifiant de suite de rapports pour l’accès. | char(40) |
| **`va_closer_detail`** | Dimension [Détails Dernière touche](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | Identifiant numérique qui identifie la dimension [Canal Dernière touche](/help/components/dimensions/last-touch-channel.md). La recherche de cet ID se trouve dans le Gestionnaire de canaux marketing. | tinyint sans signe |
| **`va_finder_detail`** | Dimension [Détails Première touche](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | Identifiant numérique qui identifie la dimension [Canal Première touche](/help/components/dimensions/first-touch-channel.md). La recherche de cet ID se trouve dans le Gestionnaire de canaux marketing. | tinyint sans signe |
| **`va_instance_event`** | Indicateur qui identifie le canal marketing [Instances](/help/components/metrics/instances.md). | tinyint sans signe |
| **`va_new_engagement`** | Indicateur qui identifie le canal marketing [Nouveaux engagements](/help/components/metrics/new-engagements.md). | tinyint sans signe |
| **`video`** | La dimension [Contenu](/help/components/dimensions/sm-core.md) des médias en flux continu. | varchar(255) |
| **`videoad`** | Dimension [Ad](/help/components/dimensions/sm-ads.md) Streaming Media. | varchar(255) |
| **`videoadinpod`** | Dimension [ Position de la publicité dans la capsule ](/help/components/dimensions/sm-ads.md) Média en flux continu. | varchar(255) |
| **`videoadlength`** | La dimension [Durée de la publicité (variable)](/help/components/dimensions/sm-ads.md) des médias en flux continu. | entier |
| **`videoadload`** | La dimension [Ad loads](/help/components/dimensions/sm-ads.md) Streaming Media. | varchar(255) |
| **`videoadname`** | La dimension [Nom de la publicité (variable)](/help/components/dimensions/sm-ads.md) Média en flux continu. | varchar(255) |
| **`videoadplayername`** | La dimension [Nom du lecteur de publicités](/help/components/dimensions/sm-ads.md) Média en flux continu. | varchar(255) |
| **`videoadpod`** | La dimension [Ad Pod](/help/components/dimensions/sm-ads.md) Streaming Media. | varchar(255) |
| **`videoadvertiser`** | Dimension Diffusion multimédia en continu de l’annonceur[](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoaudioalbum`** | Dimension [Album](/help/components/dimensions/sm-audio-metadata.md) en flux continu de médias. | varchar(255) |
| **`videoaudioartist`** | Dimension [Artiste](/help/components/dimensions/sm-audio-metadata.md) du média en flux continu. | varchar(255) |
| **`videoaudioauthor`** | La dimension [Auteur](/help/components/dimensions/sm-audio-metadata.md) de média en flux continu. | varchar(255) |
| **`videoaudiolabel`** | La dimension [Libellé](/help/components/dimensions/sm-audio-metadata.md) Média en flux continu. | varchar(255) |
| **`videoaudiopublisher`** | La dimension [Éditeur](/help/components/dimensions/sm-audio-metadata.md) des médias en flux continu. | varchar(255) |
| **`videoaudiostation`** | Dimension [Station](/help/components/dimensions/sm-audio-metadata.md) du média en flux continu. | varchar(255) |
| **`videocampaign`** | La dimension [ID de campagne](/help/components/dimensions/sm-ads.md) Média en flux continu. | varchar(255) |
| **`videochannel`** | La dimension [Canal de contenu](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(255) |
| **`videochapter`** | Dimension [Chapitre](/help/components/dimensions/sm-chapters.md) des médias en flux continu. | varchar(255) |
| **`videocontenttype`** | La [dimension Type de contenu](/help/components/dimensions/sm-core.md) Diffusion multimédia en continu. | varchar(255) |
| **`videodaypart`** | Partie [de la journée](/help/components/dimensions/sm-video-metadata.md) Diffusion multimédia en continu. | varchar(255) |
| **`videoepisode`** | Dimension [Épisode](/help/components/dimensions/sm-video-metadata.md) de média en flux continu. | varchar(255) |
| **`videofeedtype`** | La dimension [Type de flux multimédia](/help/components/dimensions/sm-video-metadata.md) Média en flux continu. | varchar(255) |
| **`videogenre`** | Dimension [Genre](/help/components/dimensions/sm-video-metadata.md) Diffusion multimédia en continu. Cette dimension autorise plusieurs valeurs dans le même accès, délimitées par une virgule. | text |
| **`videolength`** | La dimension [Durée du contenu (variable)](/help/components/dimensions/sm-core.md) des médias en flux continu. | entier |
| **`videomvpd`** | Dimension [MVPD](/help/components/dimensions/sm-video-metadata.md) des médias en flux continu. | varchar(255) |
| **`videoname`** | La dimension [Nom du contenu (variable)](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(255) |
| **`videonetwork`** | Dimension [Réseau](/help/components/dimensions/sm-video-metadata.md) de médias en flux continu. | varchar(255) |
| **`videopath`** | La dimension [Chemin du média](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(100) |
| **`videoplayername`** | La dimension [Nom du lecteur de contenu](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(255) |
| **`videotime`** | La mesure [Temps passé sur le contenu](/help/components/metrics/sm-core.md) des médias en flux continu. | entier |
| **`videoqoebitrateaverageevar`** | Dimension [Débit moyen](/help/components/dimensions/sm-quality.md) des médias en flux continu. | varchar(255) |
| **`videoqoebitratechangecountevar`** | La dimension [Débit de débit](/help/components/dimensions/sm-quality.md) des médias en flux continu. | varchar(255) |
| **`videoqoebuffercountevar`** | La dimension [ Événements de mémoire tampon ](/help/components/dimensions/sm-quality.md) Média en flux continu. | varchar(255) |
| **`videoqoebuffertimeevar`** | La dimension [Durée totale de la mémoire tampon](/help/components/dimensions/sm-quality.md) des médias en flux continu. | varchar(255) |
| **`videoqoedroppedframecountevar`** | La dimension [Images perdues](/help/components/dimensions/sm-quality.md) Média en flux continu. | varchar(255) |
| **`videoqoeerrorcountevar`** | La dimension [Erreurs](/help/components/dimensions/sm-quality.md) des médias en flux continu. | varchar(255) |
| **`videoqoeextneralerrors`** | La dimension [ID d’erreur externe](/help/components/dimensions/sm-quality.md) des médias en flux continu. Cette dimension permet plusieurs valeurs dans le même accès. | text |
| **`videoqoeplayersdkerrors`** | La [dimension Identifiant d’erreur du SDK du](/help/components/dimensions/sm-quality.md) lecteur Diffusion multimédia en continu. Cette dimension autorise plusieurs valeurs dans le même accès. | text |
| **`videoqoetimetostartevar`** | Dimension [Heure pour commencer](/help/components/dimensions/sm-quality.md) Diffusion multimédia en continu. | varchar(255) |
| **`videoseason`** | La [dimension Diffusion multimédia de saison](/help/components/dimensions/sm-video-metadata.md) en continu. | varchar(255) |
| **`videosegment`** | La dimension [Segment de contenu](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(255) |
| **`videoshow`** | Dimension [Afficher](/help/components/dimensions/sm-video-metadata.md) de médias en flux continu. | varchar(255) |
| **`videoshowtype`** | La dimension [Type de programme](/help/components/dimensions/sm-video-metadata.md) Média en flux continu. | varchar(255) |
| **`videostreamtype`** | La dimension [Type de diffusion](/help/components/dimensions/sm-core.md) Média en flux continu. | varchar(255) |
| **`visid_high`** | Utilisé en combinaison avec `visid_low` pour identifier un visiteur ou une visiteuse de manière unique. | bigint sans signe |
| **`visid_low`** | Utilisé en combinaison avec `visid_high` pour identifier un visiteur ou une visiteuse de manière unique. | bigint sans signe |
| **`visid_new`** | Indicateur qui détermine si l’accès contient un identifiant visiteur nouvellement généré. | char(1) |
| **`visid_timestamp`** | Si un identifiant visiteur est nouvellement généré, fournit l’horodatage sous UNIX® du moment où l’identifiant visiteur a été généré. | int |
| **`visid_type`** | Uniquement destinée à un usage interne. Utilisée en interne par Adobe pour les optimisations de traitement. Identifiant numérique qui représente la méthode utilisée pour identifier le visiteur.<br>`0` : identifiant visiteur personnalisé ou inconnu/non applicable <br>`1` : solution de secours de l’IP et de l’agent utilisateur <br>`2` : en-tête de l’abonné mobile HTTP <br>`3` : valeur du cookie hérité (`s_vi`) <br>`4` : valeur du cookie de secours (`s_fid`) <br>`5` : Service d’identités | tinyint sans signe |
| **`visit_keywords`** | La dimension [Mot-clé de recherche](/help/components/dimensions/search-keyword.md). Cette colonne utilise une limite de caractères non standard pour varchar(244) pour s’adapter à la logique de back-end utilisée par Adobe. | varchar(244) |
| **`visit_num`** | Dimension [Nombre de](/help/components/dimensions/visit-number.md) visites. Commence à 1, et est incrémentée chaque fois qu’une nouvelle visite commence par visiteur. | int sans signe |
| **`visit_page_num`** | Dimension [Détail](/help/components/dimensions/hit-depth.md) des accès. Augmente de 1 pour chaque accès généré par le visiteur. Réinitialise chaque visite. | int sans signe |
| **`visit_ref_domain`** | Basé sur la colonne `visit_referrer`. Le premier domaine référent de la visite. | varchar(100) |
| **`visit_ref_type`** | Un identifiant numérique qui représente le type de référent du premier référent de la visite. Fait référence à la table de recherche `referrer_type.tsv`. | tinyint sans signe |
| **`visit_referrer`** | Premier référent de la visite. | varchar(255) |
| **`visit_search_engine`** | Identifiant numérique qui représente le premier moteur de recherche de la visite. Fait référence à la table de recherche `search_engines.tsv`. | smallint sans signe |
| **`visit_start_page_url`** | La première URL de la visite. | varchar(255) |
| **`visit_start_pagename`** | Valeur Nom de page du premier accès de la visite. | varchar(100) |
| **`visit_start_time_gmt`** | Date et heure (en heure UNIX®) du premier accès de la visite. | int |
| **`weekly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur hebdomadaire. | tinyint sans signe |
| **`yearly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur annuel. | tinyint sans signe |
| **`zip`** | Aide à renseigner la dimension [Code postal](/help/components/dimensions/zip-code.md). Voir également `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Colonnes inutilisées ou retirées

La liste de colonnes suivante n’est pas utilisée et ne contient généralement pas de données. Les colonnes qui ne contiennent pas de données ne sont pas prises en charge par les bibliothèques de collecte de données actives et ne sont pas des dimensions disponibles dans Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
