---
description: Tableau décrivant les colonnes du flux de données.
keywords: Flux de données ; colonnes
subtopic: data feeds
title: Référence des colonnes de données
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '3928'
ht-degree: 99%

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
| **`aemassetid`** | Variable à plusieurs valeurs correspondant aux ID de ressource (identificateurs globaux uniques) d’un ensemble de ressources d’Adobe Experience Manager. Incrémente l’événement Impression. | text |
| **`aemassetsource`** | Identifie la source de l’événement de ressources. Utilisée dans Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID de ressource d’une ressource Adobe Experience Manager. Incrémente l’événement Click. | varchar(255) |
| **`browser`** | Identifiant numérique du navigateur. Fait référence à la table de recherche `browser.tsv`. | int sans signe |
| **`browser_height`** | Hauteur en pixels de la fenêtre du navigateur. | smallint sans signe |
| **`browser_width`** | Largeur en pixels de la fenêtre du navigateur. | smallint sans signe |
| **`c_color`** | Codage en bits de la palette de couleurs. Utilisée dans le cadre du calcul de la dimension [Intensité des couleurs](/help/components/dimensions/color-depth.md). AppMeasurement utilise la fonction JavaScript `screen.colorDepth()`. | char(20) |
| **`campaign`** | Variable utilisée dans la dimension [Code de suivi](/help/components/dimensions/tracking-code.md). | varchar(255) |
| **`carrier`** | Variable d’intégration Adobe Advertising. Définit l’opérateur de téléphonie mobile. Valeur de clé pour la [recherche dynamique](dynamic-lookups.md) `carrier.tsv`. | varchar(100) |
| **`ch_hdr`** | Indications du client collectées via l’en-tête de requête HTTP. | text |
| **`ch_js`** | Indications du client collectées via l’API JavaScript User-Agent Client Hints. | text |
| **`channel`** | Variable utilisée dans la dimension [Sections du site](/help/components/dimensions/site-section.md). | varchar(100) |
| **`click_action`** | N’est plus utilisé. Adresse du lien ayant fait l’objet d’un clic dans l’outil hérité ClickMap. | varchar(100) |
| **`click_action_type`** | N’est plus utilisé. Type de lien de l’outil hérité ClickMap.<br>0 : URL HREF<br>1 : identifiant personnalisé<br>2 : événement JavaScript onClick<br>3 : élément de formulaire | tinyint sans signe |
| **`click_context`** | N’est plus utilisé. Nom de la page où un clic a été fait sur les liens. Partie de l’outil hérité ClickMap. | varchar(255) |
| **`click_context_type`** | N’est plus utilisé. Indique si `click_context` avait un nom de page ou une URL de page par défaut.<br>0 : URL de la page<br>1 : Nom de la page | tinyint sans signe |
| **`click_sourceid`** | N’est plus utilisé. Identifiant numérique pour l’emplacement sur la page du lien cliqué. Partie de l’outil hérité ClickMap. | int sans signe |
| **`click_tag`** | N’est plus utilisé. Type d’élément HTML sur lequel on a cliqué. | char(10) |
| **`clickmaplink`** | Lien d’Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Lien d’Activity Map par région | varchar(255) |
| **`clickmappage`** | Page d’Activity Map | varchar(255) |
| **`clickmapregion`** | Région d’Activity Map | varchar(255) |
| **`code_ver`** | Version du SDK client ou de l’API utilisée pour compiler et envoyer la demande d’image. | char(16) |
| **`color`** | Identifiant d’intensité des couleurs basé sur la valeur de la colonne `c_color`. Fait référence à la table de recherche `color_depth.tsv`. | smallint sans signe |
| **`connection_type`** | Identifiant numérique représentant le type de connexion. Variable utilisée dans la dimension [Type de connexion](/help/components/dimensions/connection-type.md). Fait référence à la table de recherche `connection_type.tsv`. | tinyint sans signe |
| **`cookies`** | Variable utilisée dans la dimension [Prise en charge des cookies](/help/components/dimensions/cookie-support.md).<br>Y : activé<br>N : désactivé<br>U : inconnu | char(1) |
| **`country`** | Identifiant numérique représentant les valeurs trouvées lors de la recherche dans `country.tsv`. | smallint sans signe |
| **`ct_connect_type`** | Liée à la colonne `connection_type`. Les valeurs les plus courantes sont LAN/Wi-Fi, Opérateur de téléphonie mobile et Modem. | char(20) |
| **`curr_factor`** | Détermine la décimale de la devise et est utilisée pour la conversion de devise. Par exemple, le dollar américain (USD) utilise deux décimales, donc cette valeur de colonne serait de 2. | tinyint |
| **`curr_rate`** | Taux de change au moment de la transaction. Adobe travaille en partenariat avec XE pour déterminer le taux de change du jour. | decimal(24,12) |
| **`currency`** | Le code de devise qui a été utilisé pendant la transaction. | char(8) |
| **`cust_hit_time_gmt`** | Suites de rapports avec horodatage uniquement. Date et l’heure envoyées avec l’accès, basées sur l’heure UNIX®. | int |
| **`cust_visid`** | Si un identifiant visiteur personnalisé est défini, il est indiqué dans cette colonne. | varchar(255) |
| **`daily_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur quotidien. | tinyint sans signe |
| **`dataprivacyconsentoptin`** | Variable utilisée dans la dimension [Accord préalable de gestion du consentement](/help/components/dimensions/cm-opt-in.md). Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `DMP` et `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | Variable utilisée dans la dimension [Droit d’opposition de gestion du consentement](/help/components/dimensions/cm-opt-out.md). Plusieurs valeurs peuvent être présentes par accès, séparées par une barre verticale (`\|`). Les valeurs valides comprennent `SSF`, `DMP` et `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Valeur identifiant si le consentement est acquis pour envoyer des données d’Adobe Analytics par Adobe Advertising à des fournisseurs publicitaires tiers (tels que Google). Pour plus d’informations, voir [Consentement pour la publicité](/help/components/dimensions/ad-consent.md). | varchar(100) |
| **`date_time`** | Heure de l’accès dans un format lisible, basée sur le fuseau horaire de la suite de rapports. | datetime |
| **`domain`** | Variable utilisée dans la dimension [Domaine](/help/components/dimensions/domain.md). Basée sur le point dʼaccès Internet du visiteur. | varchar(100) |
| **`duplicate_events`** | Répertorie chaque événement compté comme double. | varchar(255) |
| **`duplicate_purchase`** | Indicateur signifiant que l’événement d’achat pour cet accès doit être ignoré, car il s’agit d’un double. | tinyint sans signe |
| **`duplicated_from`** | Utilisée uniquement dans les suites de rapports contenant les règles VISTA de la copie de l’accès. Indique la suite de rapports à partir de laquelle l’accès a été copié. | varchar(40) |
| **`ef_id`** | Le `ef_id` utilisé dans les intégrations Adobe Advertising. | varchar(255) |
| **`evar1 - evar250`** | Variables personnalisées 1-250. Utilisées dans les dimensions [eVar](/help/components/dimensions/evar.md). Chaque organisation utilise les eVars différemment. Le meilleur outil pour obtenir plus d’informations sur la façon dont votre organisation renseigne les eVars respectifs serait un document de conception de solution spécifique à votre organisation. | varchar(255) |
| **`event_list`** | Liste séparée par des virgules d’identifiants numériques représentant les événements déclenchés lors de l’accès. Comprend à la fois les événements par défaut et les événements personnalisés 1-1000. Utilise la recherche de `event.tsv`. | text |
| **`exclude_hit`** | Indicateur signifiant que lʼaccès est exclu de la création de rapports. La colonne `visit_num` nʼest pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>2 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>3 : n’est plus utilisée. Exclusion de lʼagent utilisateur<br>4 : Exclusion basée sur lʼadresse IP<br>5 : Information indispensable sur lʼaccès manquante telle que `page_url`, `pagename`, `page_event`, ou `event_list`<br>6 : JavaScript nʼa pas traité lʼaccès correctement<br>7 : Exclusion spécifique au compte, comme dans les règles VISTA<br>8 : Inutilisée. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>10 : Code de devise invalide<br>11 : Horodatage manquant sur un accès pour une suite de rapport avec horodatage ou l’accès contenait un horodatage sur une suite de rapport sans horodatage<br>12 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>13 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>14 : Accès cible qui ne correspondait pas à un accès Analytics<br>15 : Inutilisé pour le moment.<br>16 : Accès Advertising Cloud qui ne correspondait pas à un accès Analytics | tinyint sans signe |
| **`first_hit_page_url`** | La toute première URL du visiteur. | varchar(255) |
| **`first_hit_pagename`** | Variable utilisée dans la dimension [Page d’accès dʼorigine](/help/components/dimensions/entry-dimensions.md). Le nom de la page d’entrée d’origine du visiteur. | varchar(100) |
| **`first_hit_ref_domain`** | Variable utilisée dans la dimension [Domaine référent initial](/help/components/dimensions/original-referring-domain.md). Basée sur `first_hit_referrer`. Le tout premier domaine référent du visiteur. | varchar(100) |
| **`first_hit_ref_type`** | Identifiant numérique représentant le type de référent du tout premier référent du visiteur. Utilise la recherche de `referrer_type.tsv`. | tinyint sans signe |
| **`first_hit_referrer`** | La toute première URL de référence du visiteur. | varchar(255) |
| **`first_hit_time_gmt`** | Date et heure du tout premier accès du visiteur ou de la visiteuse (heure UNIX®). | int |
| **`geo_city`** | Nom de la ville d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [Villes](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | Abréviation du pays d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [Pays](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | Identifiant numérique de la zone démographique d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [DMA États-Unis](/help/components/dimensions/us-dma.md). | int sans signe |
| **`geo_region`** | Nom de l’État ou de la région d’où provient l’accès, basé sur l’adresse IP. Utilisée dans la dimension [Régions](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | Code postal d’où provient l’accès, basé sur l’adresse IP. Aide à renseigner la dimension [Code postal](/help/components/dimensions/zip-code.md). Voir également `zip`. | varchar(16) |
| **`hier1 - hier5`** | Utilisé par les variables de hiérarchie. Contient une liste délimitée de valeurs. Le délimiteur est sélectionné dans les paramètres de la suite de rapports. | varchar(255) |
| **`hit_source`** | Indique la source de l’accès. Les sources d’accès 1, 2 et 6 sont facturées. <br>1 : demande d’image standard sans horodatage <br>2 : demande d’image standard avec horodatage <br>3 : chargement de source de données actif avec horodatage <br>4 : inutilisée <br>5 : chargement de source de données générique <br>6 : chargement de source de données de traitement complet <br>7 : chargement de source de données TransactionID <br>8 : n’est plus utilisée ; versions précédentes des sources de données Adobe Advertising Cloud <br>9 : n’est plus utilisée ; mesures de résumé Adobe Social <br>10 : transfert côté serveur Audience Manager utilisé | tinyint sans signe |
| **`hit_time_gmt`** | Date et l’heure des serveurs de collecte de données Adobe ayant reçu l’accès, basé sur l’heure UNIX®. | int |
| **`hitid_high`** | Utilisée en combinaison avec `hitid_low` pour identifier un accès. | bigint sans signe |
| **`hitid_low`** | Utilisé en combinaison avec `hitid_high` pour identifier un accès. | bigint sans signe |
| **`homepage`** | N’est plus utilisé. Indique si l’URL active est la page d’accueil du navigateur. | char(1) |
| **`hourly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur horaire. | tinyint sans signe |
| **`ip`** | L’adresse IPv4, basée sur l’en-tête HTTP de la demande d’image. Mutuellement exclusif à `ipv6`. Si cette colonne contient une adresse IP non masquée, `ipv6` est vide. | char(20) |
| **`ip2`** | Inutilisé. Variable de référence du serveur principal pour les suites de rapports contenant des règles VISTA basées sur l’adresse IP. | char(20) |
| **`ipv6`** | L’adresse IPv6 compressée, si disponible. Mutuellement exclusif à `ip`. Si cette colonne contient une adresse IP non masquée, `ip` est vide. | varchar(40) |
| **`j_jscript`** | Version de JavaScript prise en charge par le navigateur. | char(5) |
| **`java_enabled`** | Indicateur précisant si Java est activé. <br>Y : activé <br>N : désactivé <br>U : inconnu | char(1) |
| **`javascript`** | Identifiant de recherche de la version JavaScript, basé sur `j_jscript`. Fait référence à la table de recherche `javascript_version`. | tinyint sans signe |
| **`language`** | Identifiant numérique de la langue. Utilise la table de recherche `languages.tsv`. | smallint sans signe |
| **`last_hit_time_gmt`** | Date et heure (en heure UNIX®) de l’accès précédent. Utilisée pour calculer la dimension [Jours depuis la dernière visite](/help/components/dimensions/days-since-last-visit.md). | int |
| **`last_purchase_num`** | Variable utilisée dans la dimension [Fidélisation des clients](/help/components/dimensions/customer-loyalty.md). Indique le nombre dʼachats précédents effectués par le visiteur. <br>0 : Aucun achat auparavant (n’est pas client) <br>1 : 1 achat précédent (nouveau client) <br>2 : 2 achats précédents (client de retour) <br>3 : 3 achats précédents ou plus (client fidèle) | int sans signe |
| **`last_purchase_time_gmt`** | Utilisée dans la dimension [Jours depuis le dernier achat](/help/components/dimensions/days-since-last-purchase.md). Date et heure (en heure UNIX®) du dernier achat effectué. Pour les premiers achats et les visiteurs qui n’avaient jamais effectué d’achat auparavant, cette valeur est de `0`. | int |
| **`latlon1`** | Lieu (jusqu’à 10 km) | varchar(255) |
| **`latlon23`** | Lieu (jusqu’à 100 m) | varchar(255) |
| **`latlon45`** | Lieu (jusqu’à 1 m) | varchar(255) |
| **`mc_audiences`** | Liste des identifiants de segment Audience Manager auxquels le visiteur appartient. La colonne `post_mc_audiences` change le délimiteur en `--**--`. | text |
| **`mcvisid`** | Identifiant visiteur Experience Cloud. Nombre 128 bits constitué de deux nombres 64 bits concaténés complétés par 19 chiffres. | varchar(255) |
| **`mobile_id`** | Si l’utilisateur ou l’utilisatrice a recours à un appareil mobile, il s’agit alors de l’identifiant numérique de l’appareil. Valeur de clé pour la [recherche dynamique](dynamic-lookups.md) `mobile_attributes.tsv`. | int |
| **`mobileaction`** | Action mobile. Collectée automatiquement lors dʼun appel `trackAction` dans Mobile Services. Permet le cheminement d’action automatique dans l’application. | varchar(100) |
| **`mobileappid`** | ID de l’application mobile Stocke le nom et la version de l’application au format suivant : `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Utilisé dans le connecteur de données Aptelignent. L’identifiant d’application utilisé dans Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Utilisé dans le connecteur de données Aptelignent. L’identifiant de plantage utilisé dans Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Utilisé dans le connecteur de données AppFigures. Identifiant de l’objet de la boutique d’applications. | varchar(255) |
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
| **`mobiledayssincelastupgrade`** | MIS HORS SERVICE - Collecté à partir de la variable a.DaysSinceLastUpgrade des données de contexte. Nombre de jours écoulés depuis la session précédente. | varchar(255) |
| **`mobiledayssincelastuse`** | Nombre de jours depuis la dernière exécution de l’application. | varchar(255) |
| **`mobiledeeplinkid`** | Collecté à partir de la variable des données de contexte `a.deeplink.id`. Utilisé dans les rapports d’acquisition comme identifiant du lien d’acquisition mobile. | varchar(255) |
| **`mobiledevice`** | Nom de l’appareil mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparés par des virgules. Le premier chiffre représente la génération de l’appareil, le second la famille d’appareils. | varchar(255) |
| **`mobilehourofday`** | Définit l’heure du jour où l’application a été lancée. Suit un format numérique de 24 heures. | varchar(255) |
| **`mobileinstalldate`** | Date de l’installation mobile. Indique la date de la première ouverture d’une application mobile par un utilisateur ou une utilisatrice. | varchar(255) |
| **`mobilelaunchessincelastupgrade`** | MIS HORS SERVICE - Collecté à partir de la variable a.LaunchesSinceUpgrade des données de contexte. Signale le nombre de lancements depuis la dernière mise à niveau. | varchar(255) |
| **`mobilelaunchnumber`** | Est incrémentée d’une unité chaque fois que l’application mobile est lancée. | varchar(255) |
| **`mobileltv`** | N’est plus utilisé. Renseignée par les méthodes trackLifetimeValue. | varchar(255) |
| **`mobilemessagebuttonname`** | Collecté à partir de la variable des données de contexte `a.message.button.id`. Utilisé pour la messagerie au sein de l’application afin d’identifier le bouton qui a fermé le message. | varchar(100) |
| **`mobilemessageid`** | Identifiant de message au sein de l’application | varchar(255) |
| **`mobilemessageonline`** | Message en ligne dans l’application | varchar(255) |
| **`mobilemessagepushoptin`** | Collecté à partir de la variable des données de contexte `a.push.optin`. Définissez cette valeur sur « true » lorsque l’utilisateur s’inscrit à la messagerie push ; dans le cas contraire, la valeur qui apparaît est « false ». | varchar(255) |
| **`mobilemessagepushpayloadid`** | Collecté à partir de la variable des données de contexte `a.push.payloadid`. Utilisé comme identifiant de paiement dans la messagerie push. | varchar(255) |
| **`mobileosenvironment`** | MIS HORS SERVICE - Collecté à partir de la variable des données de contexte `a.OSEnvironment`. Indique l’environnement du système d’exploitation, par exemple Andoid ou iOS. | varchar(255) |
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
| **`monthly_visitor`** | Indicateur signifiant que le visiteur est unique pour le mois en cours. | tinyint sans signe |
| **`mvvar1`** - `mvvar3` | Valeurs des variables de liste. Contient une liste délimitée de valeurs personnalisées en fonction de l’implémentation. Les colonnes `post_mvvar1` - `post_mvvar3` remplacent le délimiteur dʼorigine par `--**--`. | text |
| **`mvvar1_instances`** - `mvvar3_instances` | Les valeurs de la variable de liste qui ont été définies sur l’accès actuel. Remplace le délimiteur d’origine par `--**--`. N’a pas de colonne `post`. | text |
| **`namespace`** | Inutilisé. Fait partie d’une fonctionnalité mise au rebut. | varchar(50) |
| **`new_visit`** | Indicateur qui détermine si l’accès actif est une nouvelle visite. Valeur définie par les serveurs d’Adobe après 30 minutes d’inactivité au niveau de la visite. | tinyint sans signe |
| **`os`** | Identifiant numérique représentant le système d’exploitation du visiteur. Basé sur la colonne `user_agent`. Valeur de clé pour la recherche standard `operating_system.tsv` et la [recherche dynamique](dynamic-lookups.md) `operating_system_type.tsv`. | int sans signe |
| **`p_plugins`** | N’est plus utilisé. Liste des plug-ins disponibles pour le navigateur. Utilisation de la fonction JavaScript `navigator.plugins()`. | text |
| **`page_event`** | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). Voir [Recherche d’événement de page](datafeeds-page-event.md). | tinyint sans signe |
| **`page_event_var1`** | Uniquement utilisée dans les demandes d’image de suivi des liens. URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. | text |
| **`page_event_var2`** | Uniquement utilisée dans les demandes d’image de suivi des liens. Nom personnalisé (le cas échéant) du lien. | varchar(100) |
| **`page_event_var3`** | N’est plus utilisé. Contient les données des modules Survey et Media. Rapports vidéo hérités générés dans les versions précédentes d’Adobe Analytics. | text |
| **`page_type`** | Utilisé pour renseigner la dimension [Pages introuvables](/help/components/dimensions/pages-not-found.md). Utilisé exclusivement pour les pages 404. Cette variable doit être vide ou contenir la valeur `ErrorPage`. | char(20) |
| **`page_url`** | URL de l’accès à la Notez que `post_page_url` est supprimé pour les demandes d’image de suivi de liens et utilise un type de données varchar(255). | text |
| **`pagename`** | Utilisé pour renseigner la dimension [Page](/help/components/dimensions/page.md). Si la variable [`pagename`](/help/implement/vars/page-vars/pagename.md) est vide, Analytics utilise la variable `page_url` en remplacement. | varchar(100) |
| **`pagename_no_url`** | Similaire à `pagename`, sauf qu’il ne retourne pas à `page_url`. Seule la colonne `post` est disponible. | varchar(100) |
| **`paid_search`** | Indicateur qui est défini si l’accès correspond à la détection de recherche payante. | tinyint sans signe |
| **`partner_plugins`** | Inutilisé. Fait partie d’une fonctionnalité mise au rebut. | varchar(255) |
| **`persistent_cookie`** | Utilisé dans la dimension [Prise en charge des cookies persistants](/help/components/dimensions/persistent-cookie-support.md). Indique si le visiteur prend en charge les cookies qui ne sont pas ignorés après chaque accès. | char(1) |
| **`plugins`** | N’est plus utilisé. Liste des identifiants numériques qui correspondent aux plug-ins disponibles dans le navigateur. Utilise la recherche de `plugins.tsv`. | varchar(180) |
| **`pointofinterest`** | Nom du point ciblé Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Distance du centre du point ciblé Mobile Services | varchar(255) |
| Colonnes **`post_`** | Contient la valeur finalement utilisée dans les rapports. Chaque colonne « Post » est renseignée suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. | Voir la colonne « Non post » correspondante. |
| **`prev_page`** | Inutilisé. Identifiant propriétaire Adobe de la page précédente. | int sans signe |
| **`product_list`** | Liste des produits telle que transmise par l’intermédiaire de la variable [`products`](/help/implement/vars/page-vars/products.md). Les produits sont délimités par des virgules, tandis que les propriétés des produits individuels sont délimitées par des points-virgules. | text |
| **`product_merchandising`** | Inutilisé. Utilisez `product_list` à la place. | text |
| **`prop1`** - `prop75` | Variables de trafic personnalisées 1 - 75. Utilisé dans les dimensions [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identifiant unique pour un achat, tel qu’il est défini à l’aide de la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Utilisé par la colonne `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur trimestriel. | tinyint sans signe |
| **`ref_domain`** | Basée sur la colonne Référent. Domaine référent de l’accès. Utilisé dans la dimension [Domaine référent](/help/components/dimensions/referring-domain.md). | varchar(100) |
| **`ref_type`** | Identifiant numérique représentant le type de référence pour l’accès. Utilisé dans la dimension [Type de référent](/help/components/dimensions/referrer-type.md). <br>1 : à l’intérieur de votre site<br>2 : autres sites Web <br>3 : moteurs de recherche <br>4 : disque dur <br>5 : USENET <br>6 : saisi/marqué d’un signet (sans référent) <br>7 : courrier électronique <br>8 : sans JavaScript <br>9 : réseaux sociaux | tinyint sans signe |
| **`referrer`** | URL de la page précédente. Utilisé dans la dimension [Référent](/help/components/dimensions/referrer.md). Notez que, bien que `referrer` utilise un type de données varchar(255), `post_referrer` utilise un type de données varchar(244). | varchar(255) |
| **`resolution`** | Identifiant numérique représentant la résolution du moniteur. Utilisé dans la dimension [Résolution d’écran](/help/components/dimensions/monitor-resolution.md). Utilise la table de recherche `resolution.tsv`. | smallint sans signe |
| **`s_kwcid`** | Identifiant du mot-clé dans les intégrations Adobe Advertising. | varchar(255) |
| **`s_resolution`** | Valeur brute de la résolution de l’écran. Collecté à l’aide de la fonction JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | Identifiant numérique représentant le moteur de recherche qui a référé le visiteur à votre site. Utilise la recherche de `search_engines.tsv`. | smallint sans signe |
| **`search_page_num`** | Utilisé par la dimension [Tout le classement des pages de recherche](/help/components/dimensions/all-search-page-rank.md). Indique sur quelle page de résultats de recherche votre site est apparu avant que l’utilisateur ou l’utilisatrice ne clique sur votre site. | smallint sans signe |
| **`secondary_hit`** | Indicateur qui suit les accès secondaires. Normalement, il provient du balisage multisuite et des règles VISTA qui copient les accès. | tinyint sans signe |
| **`service`** | Inutilisé. Utilisez `page_event` à la place. | char(2) |
| **`socialaccountandappids`** | N’est plus utilisé. Identifiants de comptes sociaux et d’application | varchar(255) |
| **`socialassettrackingcode`** | N’est plus utilisé. Variable de campagne sociale | varchar(255) |
| **`socialauthor`** | N’est plus utilisé. Variable des auteurs du module Social | varchar(255) |
| **`socialcontentprovider`** | N’est plus utilisé. Plateformes sociales/Propriétés | varchar(255) |
| **`socialinteractiontype`** | N’est plus utilisé. Type d’interaction sociale | varchar(255) |
| **`sociallanguage`** | N’est plus utilisé. Langage social | varchar(255) |
| **`sociallatlong`** | N’est plus utilisé. Latitude/Longitude sociale | varchar(255) |
| **`socialowneddefinitioninsighttype`** | N’est plus utilisé. Type d’informations sur la définition détenue sur réseau social | varchar(255) |
| **`socialowneddefinitioninsightvalue`** | N’est plus utilisé. Valeur d’informations sur la définition détenue sur réseau social | varchar(255) |
| **`socialowneddefinitionmetric`** | N’est plus utilisé. Mesure de définition détenue sur réseau social | varchar(255) |
| **`socialowneddefinitionpropertyvspost`** | N’est plus utilisé. Propriété de définition détenue sur réseau social/publication | varchar(255) |
| **`socialownedpostids`** | N’est plus utilisé. Identifiants de publications détenues sur réseau social | varchar(255) |
| **`socialownedpropertyid`** | N’est plus utilisé. Identifiant de propriété détenue sur réseau social | varchar(255) |
| **`socialownedpropertyname`** | N’est plus utilisé. Nom de propriété détenue sur réseau social | varchar(255) |
| **`socialownedpropertypropertyvsapp`** | N’est plus utilisé. Propriété détenue sur réseau social/application | varchar(255) |
| **`sourceid`** | ID Source | int sans signe |
| **`state`** | Variable d’état. | varchar(50) |
| **`stats_server`** | Inutilisable. Serveur interne d’Adobe qui a traité l’accès. | char(30) |
| **`survey`** | N’est plus utilisé. Variable Adobe Survey. Seule la colonne `post` est disponible. | text |
| **`survey_instances`** | N’est plus utilisé. Variable d’instances Adobe Survey. | text |
| **`t_time_info`** | Heure locale pour le visiteur. Le format est : `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Utilisée dans les intégrations Adobe Target. Représente tous les tests actuellement autorisés. Le format est : `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | text |
| **`tnt_action`** | Utilisée dans les intégrations Adobe Target. Représente tous les tests pour lesquels lʼaccès est qualifié. | text |
| **`tnt_instances`** | Utilisée dans les intégrations Adobe Target. Variable d’instances Target. | text |
| **`tnt_post_vista`** | N’est plus utilisé. Utilisez `post_tnt` à la place. | text |
| **`transactionid`** | Identifiant unique vers lequel plusieurs points de données pourront être chargés plus tard au moyen de sources de données. Collecté à l’aide de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | text |
| **`truncated_hit`** | Indicateur signifiant que la demande d’image a été tronquée. Indique qu’un accès partiel a été reçu. <br>Y : l’accès a été tronqué ; accès partial reçu <br>N : l’accès n’a pas été tronqué ; accès complet reçu | char(1) |
| **`ua_color`** | N’est plus utilisé. Anciennement utilisée comme solution de secours pour l’intensité de couleur. | char(20) |
| **`ua_os`** | N’est plus utilisé. Anciennement utilisée comme solution de secours pour le système d’exploitation. | char(80) |
| **`ua_pixels`** | N’est plus utilisé. Anciennement utilisée comme solution de secours pour la hauteur et la largeur du navigateur. | char(20) |
| **`user_agent`** | Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image. | text |
| **`user_hash`** | Inutilisable. Hachage de l’identifiant de suite de rapports. Utilisez `username` à la place. | int sans signe |
| **`user_server`** | Utilisé dans la dimension [Serveur](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Inutilisable. Identifiant numérique pour l’identifiant de suite de rapports. Utilisez `username` à la place. | int sans signe |
| **`username`** | Identifiant de suite de rapports pour l’accès. | char(40) |
| **`va_closer_detail`** | Variable utilisée dans la dimension [Détails de Dernière touche](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | Identifiant numérique qui identifie la dimension [Canal Dernière touche](/help/components/dimensions/last-touch-channel.md). La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| **`va_finder_detail`** | Variable utilisée dans la dimension [Détails de Première touche](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | Identifiant numérique qui identifie la dimension [Canal Première touche](/help/components/dimensions/first-touch-channel.md). La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| **`va_instance_event`** | Indicateur pour identifier les [instances](/help/components/metrics/instances.md) de canal marketing. | tinyint sans signe |
| **`va_new_engagement`** | Indicateur pour identifier les [nouveaux engagements](/help/components/metrics/new-engagements.md) de canal marketing. | tinyint sans signe |
| **`video`** | Contenu vidéo | varchar(255) |
| **`videoad`** | Nom de la publicité vidéo | varchar(255) |
| **`videoadinpod`** | Position de la publicité vidéo dans la capsule | varchar(255) |
| **`videoadlength`** | Durée de la publicité vidéo | entier |
| **`videoadload`** | Chargements des publicités vidéo | varchar(255) |
| **`videoadname`** | Nom de la publicité vidéo | varchar(255) |
| **`videoadplayername`** | Nom du lecteur de publicités vidéo | varchar(255) |
| **`videoadpod`** | Capsule publicitaire vidéo | varchar(255) |
| **`videoadvertiser`** | Annonceur vidéo | varchar(255) |
| **`videoaudioalbum`** | Album audio vidéo | varchar(255) |
| **`videoaudioartist`** | Artiste audio vidéo | varchar(255) |
| **`videoaudioauthor`** | Auteur audio vidéo | varchar(255) |
| **`videoaudiolabel`** | Libellé audio vidéo | varchar(255) |
| **`videoaudiopublisher`** | Éditeur audio vidéo | varchar(255) |
| **`videoaudiostation`** | Station audio vidéo | varchar(255) |
| **`videocampaign`** | Campagne vidéo | varchar(255) |
| **`videochannel`** | Canal vidéo | varchar(255) |
| **`videochapter`** | Chapitre vidéo | varchar(255) |
| **`videocontenttype`** | Type de contenu vidéo. Défini automatiquement sur « Vidéo » pour toutes les consultations vidéo | varchar(255) |
| **`videodaypart`** | Moment de la journée de la vidéo | varchar(255) |
| **`videoepisode`** | Épisode de la vidéo | varchar(255) |
| **`videofeedtype`** | Type de flux vidéo | varchar(255) |
| **`videogenre`** | Genre de la vidéo | text |
| **`videolength`** | Durée de la vidéo | entier |
| **`videomvpd`** | Vidéo MVPD | varchar(255) |
| **`videoname`** | Nom de la vidéo | varchar(255) |
| **`videonetwork`** | Réseau de la vidéo | varchar(255) |
| **`videopath`** | Chemin de la vidéo | varchar(100) |
| **`videoplayername`** | Nom du lecteur vidéo | varchar(255) |
| **`videotime`** | Durée de la vidéo | entier |
| **`videoqoebitrateaverageevar`** | Débit en bits moyen de la qualité vidéo | varchar(255) |
| **`videoqoebitratechangecountevar`** | Nombre de changements au niveau de la qualité vidéo | varchar(255) |
| **`videoqoebuffercountevar`** | Nombre de tampons pour la qualité vidéo | varchar(255) |
| **`videoqoebuffertimeevar`** | Période tampon de la qualité vidéo | varchar(255) |
| **`videoqoedroppedframecountevar`** | Nombre d’images perdues au niveau de la qualité vidéo | varchar(255) |
| **`videoqoeerrorcountevar`** | Comptage des erreurs de la qualité vidéo | varchar(255) |
| **`videoqoeextneralerrors`** | Erreurs externes de la qualité vidéo | text |
| **`videoqoeplayersdkerrors`** | Erreurs du SDK de la qualité vidéo | text |
| **`videoqoetimetostartevar`** | Temps de démarrage de la qualité vidéo | varchar(255) |
| **`videoseason`** | Saison de la vidéo | varchar(255) |
| **`videosegment`** | Segment de vidéo | varchar(255) |
| **`videoshow`** | Affichage de la vidéo | varchar(255) |
| **`videoshowtype`** | Type d’affichage de la vidéo | varchar(255) |
| **`videostreamtype`** | Type de flux vidéo | varchar(255) |
| **`visid_high`** | Utilisé en combinaison avec `visid_low` pour identifier un visiteur ou une visiteuse de manière unique. | bigint sans signe |
| **`visid_low`** | Utilisé en combinaison avec `visid_high` pour identifier un visiteur ou une visiteuse de manière unique. | bigint sans signe |
| **`visid_new`** | Indicateur pour identifier si l’accès contient un identifiant visiteur nouvellement généré. | char(1) |
| **`visid_timestamp`** | Si l’identifiant visiteur a été récemment généré, fournit la date et l’heure (en heure UNIX®) de la génération de l’identifiant visiteur. | int |
| **`visid_type`** | Uniquement destinée à un usage interne. Utilisée en interne par Adobe pour les optimisations de traitement. Identifiant numérique représentant la méthode utilisée pour identifier le visiteur.<br>`0` : identifiant visiteur personnalisé ou inconnu/non applicable <br>`1` : solution de secours de l’IP et de l’agent utilisateur <br>`2` : en-tête de l’abonné mobile HTTP <br>`3` : valeur du cookie hérité (`s_vi`) <br>`4` : valeur du cookie de secours (`s_fid`) <br>`5` : Service d’identités | tinyint sans signe |
| **`visit_keywords`** | Variable utilisée dans la dimension [Mot-clé de recherche](/help/components/dimensions/search-keyword.md). Cette colonne utilise une limite de caractères non standard pour varchar(244) pour s’adapter à la logique de back-end utilisée par Adobe. | varchar(244) |
| **`visit_num`** | Variable utilisée dans la dimension [Nombre de visites](/help/components/dimensions/visit-number.md). Commence à 1, et est incrémentée chaque fois qu’une nouvelle visite commence par visiteur. | int sans signe |
| **`visit_page_num`** | Variable utilisée dans la dimension [Détail des accès](/help/components/dimensions/hit-depth.md). Augmente de 1 pour chaque accès que l’utilisateur génère. Réinitialise chaque visite. | int sans signe |
| **`visit_ref_domain`** | Basé sur la colonne `visit_referrer`. Le premier domaine référent de la visite. | varchar(100) |
| **`visit_ref_type`** | Identifiant numérique, représentant le type de référent du premier référent du visiteur. Utilise la table de recherche `referrer_type.tsv`. | tinyint sans signe |
| **`visit_referrer`** | Premier référent de la visite. | varchar(255) |
| **`visit_search_engine`** | Identifiant numérique du premier moteur de recherche de la visite. Utilise la recherche de `search_engines.tsv`. | smallint sans signe |
| **`visit_start_page_url`** | La première URL de la visite. | varchar(255) |
| **`visit_start_pagename`** | Valeur Nom de page du premier accès de la visite. | varchar(100) |
| **`visit_start_time_gmt`** | Date et heure (en heure UNIX®) du premier accès de la visite. | int |
| **`weekly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur hebdomadaire. | tinyint sans signe |
| **`yearly_visitor`** | Indicateur qui détermine si l’accès est un nouveau visiteur annuel. | tinyint sans signe |
| **`zip`** | Aide à renseigner la dimension [Code postal](/help/components/dimensions/zip-code.md). Voir également `geo_zip`. | varchar(50) |

## Colonnes vides

La liste de colonnes suivante n’est pas utilisée et ne contient pas de données :

* `adclassificationcreative`
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
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
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
