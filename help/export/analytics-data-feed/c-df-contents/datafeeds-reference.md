---
description: Tableau décrivant les colonnes du flux de données.
keywords: Data Feed;columns
subtopic: data feeds
title: Référence des colonnes de données
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Référence des colonnes de données

Utilisez cette page pour en savoir plus sur les données contenues dans chaque colonne. La plupart des implémentations n’utilisent pas toutes les colonnes. Aussi, vous pouvez vous référer à cette page lorsque vous souhaitez déterminer les colonnes à inclure dans un export de flux de données.

>[!IMPORTANT] Pour toute colonne donnée (par exemple, une colonne définie sur 255 caractères), un flux de données peut envoyer des caractères supplémentaires en raison de l’ajout de valeurs d’échappement de caractères dans une chaîne. N’oubliez pas de tenir compte de ces caractères supplémentaires potentiels si votre implémentation envoie régulièrement des valeurs dépassant les limites de caractères.

## Colonnes, descriptions et types de données

>[!NOTE] La plupart des colonnes contiennent une colonne similaire avec un préfixe `post_`. Les colonnes « Post » contiennent les valeurs suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. Pour plus d’informations, consultez la [FAQ sur les flux de données](../df-faq.md).

| Nom de colonne | Description de la colonne | Type de données |
| --- | --- | --- |
| `accept_language` | toutes les langues acceptées, comme indiqué dans l’en-tête HTTP Accept-Language dans une demande d’image. | char(20) |
| `aemassetid` | Variable à plusieurs valeurs correspondant aux ID de ressource (GUID) d’un ensemble de ressources Adobe Experience Manager. Incrémente le d’impression. | text |
| `aemassetsource` | Identifie la source du de ressources. Utilisée dans Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID de fichier d’un fichier Adobe Experience Manager. Incréments Cliquez sur . | varchar(255) |
| `browser` | ID numérique du navigateur. Fait référence à la table de recherche browser.tsv. | int sans signe |
| `browser_height` | Hauteur en pixels de la fenêtre du navigateur. | smallint sans signe |
| `browser_width` | Largeur en pixels de la fenêtre du navigateur. | smallint sans signe |
| `c_color` | Profondeur de la palette de couleurs. Utilisé dans le cadre du calcul de la dimension Profondeur de couleur. Utilise la fonction JavaScript screen.colorDepth(). | char(20) |
| `campaign` | Variable utilisée dans la dimension Code de suivi. | varchar(255) |
| `carrier` | Variable d’intégration d’Adobe Advertising Cloud. Indique l’opérateur de téléphonie mobile. Fait référence à la table de recherche de l’opérateur. | varchar(100) |
| `channel` | Variable utilisée dans la dimension Sections du site. | varchar(100) |
| `click_action` | N’est plus utilisé. Adresse du lien sur lequel l’utilisateur a cliqué dans l’outil ClickMap hérité. | varchar(100) |
| `click_action_type` | N’est plus utilisé. Type de lien de l’outil ClickMap hérité.<br>0 : URL HREF<br>1 : identifiant personnalisé<br>2 : événement JavaScript onClick<br>3 : élément de formulaire | tinyint sans signe |
| `click_context` | N’est plus utilisé. Nom de page où le clic sur le lien s&#39;est produit. Fait partie de l’outil ClickMap hérité. | varchar(255) |
| `click_context_type` | N’est plus utilisé. Indique si click_context avait un nom de page ou si l’URL de la page était utilisée par défaut.<br>0 : URL de la page<br>1 : Nom de la page | tinyint sans signe |
| `click_sourceid` | N’est plus utilisé. ID numérique de l’emplacement sur la page du lien sur lequel l’utilisateur a cliqué. Fait partie de l’outil ClickMap hérité. | int sans signe |
| `click_tag` | N’est plus utilisé. Type d’élément HTML sur lequel l’utilisateur a cliqué. | char(10) |
| `clickmaplink` | Activity Map lien | varchar(255) |
| `clickmaplinkbyregion` | Lien d’Activity Map par région | varchar(255) |
| `clickmappage` | Page d’Activity Map | varchar(255) |
| `clickmapregion` | Région d’Activity Map | varchar(255) |
| `code_ver` | Version de la bibliothèque AppMeasurement utilisée pour compiler et envoyer la demande d’image. | char(16) |
| `color` | ID de profondeur de couleur en fonction de la valeur de la colonne c_color. Fait référence à la table de recherche color_depth.tsv. | smallint sans signe |
| `connection_type` | ID numérique représentant le type de connexion. Variable utilisée dans la dimension Type de connexion. Fait référence à la table de recherche connection_type.tsv. | tinyint sans signe |
| `cookies` | Variable utilisée dans la dimension Prise en charge des cookies.<br>Y : activé<br>N : désactivé<br>U : inconnu | char(1) |
| `country` | Identifiant numérique représentant le pays d’où provient l’accès. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. Utilise la recherche country.tsv. | smallint sans signe |
| `ct_connect_type` | Lié à la colonne connection_type. Les valeurs les plus courantes sont LAN/Wifi, Opérateur de téléphonie mobile et Modem. | char(20) |
| `curr_factor` | Détermine la position décimale de la devise et est utilisé pour la conversion de devise. Par exemple, USD utilise deux décimales. La valeur de cette colonne serait donc 2. | tinyint |
| `curr_rate` | Taux de change au moment de la transaction. Adobe collabore avec XE pour déterminer le taux de change du jour. | decimal(24,12) |
| `currency` | Code de devise utilisé pendant la transaction. | char(8) |
| `cust_hit_time_gmt` | Suites de rapports horodatées uniquement. Horodatage envoyé avec l’accès, selon l’heure Unix. | int |
| `cust_visid` | Si un ID de personnalisé est défini, il est renseigné dans cette colonne. | varchar(255) |
| `daily_visitor` | Indicateur qui détermine si l’accès est un nouveau quotidien. | tinyint sans signe |
| `date_time` | Heure de l’accès dans un format lisible, en fonction du fuseau horaire de la suite de rapports. | datetime |
| `domain` | Variable utilisée dans la dimension Domaine. Basé sur le Internet (FAI) de l’utilisateur. | varchar(100) |
| `duplicate_events` |  chaque  qui a été compté comme un  del&#39;année. | varchar(255) |
| `duplicate_purchase` | Indicateur indiquant que le  d’achat pour cet accès doit être ignoré car il s’agit d’un . | tinyint sans signe |
| `duplicated_from` | Utilisé uniquement dans les suites de rapports contenant des règles VISTA de copie d’accès. Indique de quelle suite de rapports l’accès a été copié. | varchar(40) |
| `ef_id` | ef_id utilisé dans les intégrations d’Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variables personnalisées 1-250. Chaque organisation utilise les eVars différemment. Le meilleur endroit pour plus d’informations sur la manière dont votre entreprise remplit les eVars respectives serait un de conception de solution spécifique à votre entreprise. | varchar(255) |
| `event_list` | d’identifiants numériques séparés par des virgules représentant les  de déclenchés sur l’accès. Comprend à la fois les événements par défaut et les événements personnalisés 1-1000. Utilise la recherche .tsv. | text |
| `exclude_hit` | Indicateur indiquant que l’accès est exclu des  d’. La colonne visit_num n’est pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>2 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>3 : n’est plus utilisée. Exclusion de l’agent utilisateur<br>4 : Exclusion basée sur l’adresse IP<br>5 : Information indispensable sur l’accès manquante telle que page_url, pagename, page_event, ou event_list<br>6 : JavaScript n’a pas traité l’accès correctement<br>7 : Exclusion spécifique au compte, comme dans les règles VISTA<br>8 : Inutilisée. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>10 : Code de devise invalide<br>11 : Horodatage manquant sur un accès pour une suite de rapport avec horodatage ou l’accès contenait un horodatage sur une suite de rapport sans horodatage<br>12 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>13 : Inutilisée. Fait partie d’une fonctionnalité mise au rebut.<br>14 : Accès cible qui ne correspondait pas à un accès Analytics<br>15 : Inutilisé pour le moment.<br>16 : Accès Advertising Cloud qui ne correspondait pas à un accès Analytics | tinyint sans signe |
| `first_hit_page_url` | La toute première URL du. | varchar(255) |
| `first_hit_pagename` | Variable utilisée dans la dimension Originale de la page d’entrée. Nom de la page d’entrée d’origine du. | varchar(100) |
| `first_hit_ref_domain` | Variable utilisée dans la dimension Domaine référent d’origine. Basé sur first_hit_. Le tout premier domaine référent du. | varchar(100) |
| `first_hit_ref_type` | Identifiant numérique représentant le type de  du tout premier de l’. Utilise la recherche_type.tsv. | tinyint sans signe |
| `first_hit_referrer` | La toute première URL de référence du. | varchar(255) |
| `first_hit_time_gmt` | Horodatage du tout premier accès du dans l’heure Unix. | int |
| `geo_city` | Nom de la ville d’où provient l’accès, en fonction de l’adresse IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et la ville. | char(32) |
| `geo_country` | Abréviation du pays d’où provient l’accès, basée sur la propriété intellectuelle. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. | char(4) |
| `geo_dma` | ID numérique de la zone démographique d’où provient l’accès, en fonction de l’adresse IP. Adobe s’associe à Digital Envoy pour associer l’adresse IP à la zone démographique. | int sans signe |
| `geo_region` | Nom de l’état ou de la région d’où provient l’accès, en fonction de l’adresse IP. Adobe collabore avec Digital Envoy pour associer l’adresse IP à l’état/la région. | char(32) |
| `geo_zip` | Le code postal d’origine de l’accès, basé sur l’IP. Adobe collabore avec Digital Envoy pour associer l’adresse IP au code postal. | varchar(16) |
| `hier1 - hier5` | Utilisée par les variables de hiérarchie. Contient un de valeurs délimité. Le délimiteur est choisi sous les paramètres de la suite de rapports. | varchar(255) |
| `hit_source` | Indique la source de l’accès. <br>1 : Requête image standard sans horodatage <br>2 : Requête image standard avec horodatage <br>3 : Chargement de source de données actif avec horodatage <br>4 : Inutilisé <br>5 : Chargement de source de données générique <br>6 : Chargement de source de données de traitement complet <br>7 : Chargement de source de données TransactionID <br>8 : N’est plus utilisée ; Versions précédentes des sources de données Adobe Advertising Cloud <br>9: N’est plus utilisée ; mesures de résumé Adobe Social | tinyint sans signe |
| `hit_time_gmt` | L’horodatage des serveurs de collecte de données Adobe ayant reçu l’accès, basé sur l’heure Unix. | int |
| `hitid_high` | Utilisée en combinaison avec hitid_low pour identifier de manière unique un accès. | bigint sans signe |
| `hitid_low` | Utilisé en combinaison avec hitid_high pour identifier de manière unique un accès. | bigint sans signe |
| `homepage` | N’est plus utilisé. Indique si l’URL active est la page d’accueil du navigateur. | char(1) |
| `hourly_visitor` | Indicateur qui détermine si l’accès est un nouveau horaire. | tinyint sans signe |
| `ip` | Adresse IP, en fonction de l’en-tête HTTP de la demande d’image. | char(20) |
| `ip2` | Inutilisé. Variable de référence principale pour les suites de rapports contenant des règles VISTA basées sur l’adresse IP. | char(20) |
| `j_jscript` | Version de JavaScript prise en charge par le navigateur. | char(5) |
| `java_enabled` | Indicateur précisant si Java est activé. <br>Y : activé <br>N : désactivé <br>U : inconnu | char(1) |
| `javascript` | Identifiant de recherche de la version JavaScript, basé sur j_jscript. Utilise le tableau de recherche. | tinyint sans signe |
| `language` | ID numérique de la langue. Utilise la table de recherche languages.tsv. | smallint sans signe |
| `last_hit_time_gmt` | Horodatage (heure Unix) de l’accès précédent. Utilisé pour calculer la dimension Jours depuis la dernière visite. | int |
| `last_purchase_num` | Variable utilisée dans la dimension Fidélité de la clientèle. Indique le nombre d’achats précédents effectués par le visiteur. <br>0 : Aucun achat auparavant (n’est pas client) <br>1 : 1 achat précédent (nouveau client) <br>2 : 2 achats précédents (client de retour) <br>3: 3 achats précédents ou plus (client fidèle) | int sans signe |
| `last_purchase_time_gmt` | Utilisée dans la dimension Jours depuis le dernier achat. Horodatage (heure Unix) du dernier achat effectué. Pour les nouveaux achats et les qui n’ont effectué aucun achat auparavant, cette valeur est 0. | int |
| `latlon1` | Lieu (jusqu’à 10 km) | varchar(255) |
| `latlon23` | Lieu (jusqu’à 100 m) | varchar(255) |
| `latlon45` | Lieu (jusqu’à 1 m) | varchar(255) |
| `mc_audiences` |  de  ID de segment Gestionnaire de  auxquels appartient le. | text |
| `mcvisid` | Identifiant visiteur Experience Cloud. Numéro 128 bits composé de deux nombres concaténés de 64 bits ajoutés à 19 chiffres. | varchar(255) |
| `mobile_id` | Si l’utilisateur utilise un appareil mobile, il s’agit alors de l’identifiant numérique de l’appareil. | int |
| `mobileaction` | Action mobile. Collectée automatiquement lors d’un appel trackAction dans Mobile Services. Permet le cheminement d’action automatique dans l’application. | varchar(100) |
| `mobileappid` | ID de l’application mobile. Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Utilisé dans le connecteur de données Aptelignent. L’identifiant d’application utilisé dans Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Utilisé dans le connecteur de données Aptelignent. L’identifiant de plantage utilisé dans Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Utilisé dans le connecteur de données AppFigures. Identifiant de l’objet de la boutique d’applications | varchar(255) |
| `mobilebeaconmajor` | Relais Mobile Services majeur | varchar(100) |
| `mobilebeaconminor` | Relais Mobile Services mineur | varchar(100) |
| `mobilebeaconproximity` | Proximité du relais Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID du relais Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Nom ou ID du contenu qui a affiché le lien. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignmedium` | Support marketing, tel que bannière ou courrier électronique. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignname` | Nom de la campagne, également stocké dans la variable de campagne. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignsource` | d’origine, tel qu’un bulletin d’information ou un réseau de médias sociaux. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignterm` | Mots-clés payants ou autres termes dont vous souhaitez effectuer le suivi avec cette acquisition. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobiledayofweek` | Numéro du jour de semaine où l’application a été lancée. | varchar(255) |
| `mobiledayssincefirstuse` | Nombre de jours depuis la première exécution de l’application. | varchar(255) |
| `mobiledayssincelastupgrade` | Collecté à partir de la variable a.DaysSinceLastUpgrade des données de contexte. Nombre de jours écoulés depuis la session précédente. | varchar(255) |
| `mobiledayssincelastuse` | Nombre de jours depuis la dernière exécution de l’application. | varchar(255) |
| `mobiledeeplinkid` | Collecté à partir de la variable a.<span>deeplink</span>.id des données de contexte. Utilisé dans les rapports d’acquisition comme identifiant du lien d’acquisition mobile. | varchar(255) |
| `mobiledevice` | Nom du périphérique mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparée par des virgules. Le premier chiffre représente la génération de l’appareil et le second la famille de l’appareil. | varchar(255) |
| `mobilehourofday` | Définit l’heure du jour où l’application a été lancée. Suit le format numérique de 24 heures. | varchar(255) |
| `mobileinstalldate` | Date d’installation mobile. Indique la date de la première ouverture de l’application mobile par un utilisateur. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Collecté à partir de la variable a.LaunchesSinceUpgrade des données de contexte. Signale le nombre de lancements depuis la dernière mise à niveau. | varchar(255) |
| `mobilelaunchnumber` | Incrémente d’une unité chaque fois que l’application mobile est lancée. | varchar(255) |
| `mobileltv` | N’est plus utilisé. Renseignée par les méthodes trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Collecté à partir de la variable a.<span>message</span>.button.id des données de contexte. Utilisé pour la messagerie au sein de l’application afin d’identifier le bouton qui a fermé le message. | varchar(100) |
| `mobilemessageid` | Identifiant de message au sein de l’application | varchar(255) |
| `mobilemessageonline` | Message en ligne dans l’application | varchar(255) |
| `mobilemessagepushoptin` | Collecté à partir de la variable a.push.optin des données de contexte. Définissez cette valeur sur « true » lorsque l’utilisateur s’inscrit à la messagerie push ; dans le cas contraire, la valeur qui apparaît est « false ». | varchar(255) |
| `mobilemessagepushpayloadid` | Collecté à partir de la variable a.push.payloadid des données de contexte. Utilisé comme identifiant de paiement dans la messagerie push. | varchar(255) |
| `mobileosenvironment` | Collecté à partir de la variable a.OSEnvironment des données de contexte. Indique l’environnement du système d’exploitation, par exemple Andoid ou iOS. | varchar(255) |
| `mobileosversion` | Version du système d’exploitation Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Collecté à partir de la variable a.loc.acc des données de contexte. Indique la précision du GPS en mètres au moment de la collecte des données. | varchar(255) |
| `mobileplacecategory` | Collecté à partir de la variable a.loc.category des données de contexte. Décrit la catégorie d’un lieu en particulier. | varchar(255) |
| `mobileplaceid` | Collecté à partir de la variable a.<span>loc</span>.id des données de contexte. Identifiant d’un point ciblé donné. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenu du lancement Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Moyen de lancement de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Source de lancement de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Conditions de lancement de Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Collecté à partir de la variable a.launch.campaign.trackingcode des données de contexte. Utilisé au moment de l’acquisition comme code de suivi de la campagne de lancement. | varchar(255) |
| `mobileresolution` | Résolution du périphérique mobile. Largeur x hauteur en pixels. | varchar(255) |
| `monthly_visitor` | Indicateur indiquant que le est unique au mois en cours. | tinyint sans signe |
| `mvvar1` - `mvvar3` | Valeurs  variables. Contient un délimité de valeurs personnalisées en fonction de l’implémentation. | text |
| `namespace` | Inutilisé. Une partie d&#39;une fonction mise au rebut il y a de nombreuses années. | varchar(50) |
| `new_visit` | Indicateur qui détermine si l’accès actif est une nouvelle visite. Défini par les serveurs Adobe après 30 minutes d’inactivité de visite. | tinyint sans signe |
| `os` | ID numérique représentant le système d’exploitation du. Basé sur la colonne user_agent. Utilise la recherche OS. | int sans signe |
| `p_plugins` | N’est plus utilisé.  de modules externes disponibles pour le navigateur. Utilisé la fonction JavaScript navigator.plugins(). | text |
| `page_event` | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). Voir [Recherche d’événement de page](datafeeds-page-event.md). | tinyint sans signe |
| `page_event_var1` | Utilisé uniquement dans les demandes d’image de suivi de liens. URL du lien de téléchargement, du lien de sortie ou du lien personnalisé sur lequel l’utilisateur a cliqué. | text |
| `page_event_var2` | Utilisé uniquement dans les demandes d’image de suivi de liens. Nom personnalisé (le cas échéant) du lien. | varchar(100) |
| `page_event_var3` | N’est plus utilisé.  de et données du module média. Renseigné les rapports Vidéo hérités dans les versions précédentes d’Adobe Analytics. | text |
| `page_type` | Utilisé pour remplir la dimension Pages introuvables, utilisée exclusivement pour 404 pages. Cette variable doit être vide ou contenir &quot;ErrorPage&quot;. | char(20) |
| `page_url` | URL de l’accès. Non utilisé dans les demandes d’image de suivi de liens. | varchar(255) |
| `pagename` | Permet de renseigner la dimension Pages. Si la variable pagename est vide, Analytics utilise page_url à la place. | varchar(100) |
| `paid_search` | Indicateur défini si l’accès correspond à la détection de recherche payante. | tinyint sans signe |
| `partner_plugins` | Inutilisé. Une partie d&#39;une fonction mise au rebut il y a de nombreuses années. | varchar(255) |
| `persistent_cookie` | Utilisée par la dimension Prise en charge des cookies persistants. Indique si le prend en charge les cookies qui ne sont pas ignorés après chaque accès. | char(1) |
| `plugins` | N’est plus utilisé.  d’ID numériques correspondant aux modules externes disponibles dans le navigateur. Utilise la recherche plugins.tsv. | varchar(180) |
| `pointofinterest` | Nom du point ciblé Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distance du centre du point ciblé Mobile Services | varchar(255) |
| `post_ columns` | Contient la valeur finalement utilisée dans les rapports. Chaque colonne de publication est renseignée après la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. | Voir la colonne non post correspondante |
| `prev_page` | Inutilisé. Identifiant propriétaire Adobe de la page précédente. | int sans signe |
| `product_list` | de produits tel qu’il est transmis par le biais de la variable products. Les produits sont délimités par des virgules tandis que les propriétés individuelles des produits sont délimitées par des points-virgules. | text |
| `product_merchandising` | Inutilisé. Utilisez plutôt product_. | text |
| `prop1` - `prop75` | Variables de trafic personnalisées 1 - 75. | varchar(100) |
| `purchaseid` | Identificateur unique d’un achat, tel que défini à l’aide de la variable s_purchaseID. Utilisée par la colonne _purchase. | char(20) |
| `quarterly_visitor` | Indicateur qui détermine si l’accès est un nouveau trimestriel. | tinyint sans signe |
| `ref_domain` | Basé sur la colonne  du. Domaine référent de l’accès. | varchar(100) |
| `ref_type` | ID numérique représentant le type de référence pour l’accès.<br>1 : à l’intérieur de votre site<br>2 : autres sites Web <br>3 : moteurs de recherche <br>4 : disque dur <br>5 : USENET <br>6: saisi/marqué d’un signet (sans référent) <br>7 : courrier électronique <br>8 : sans JavaScript <br>9 : réseaux sociaux | tinyint sans signe |
| `referrer` | URL de la page précédente. Notez que, bien que `referrer` utilise un type de données de varchar(255), `post_referrer` utilise un type de données de varchar(244). | varchar(255) |
| `resolution` | Identifiant numérique représentant la résolution du moniteur. Remplit la dimension Résolution de l’écran. Utilise la table de recherche resolution.tsv. | smallint sans signe |
| `s_kwcid` | Identifiant du mot-clé dans les intégrations Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valeur de résolution d’écran brut. Regroupement à l’aide de la fonction JavaScript screen.width x screen.height. | char(20) |
| `sampled_hit` | N’est plus utilisé. Anciennement utilisée pour l’échantillonnage dans Ad Hoc Analysis. | char(1) |
| `search_engine` | ID numérique représentant le moteur de recherche qui a renvoyé le sur votre site. Utilise la recherche search_engine.tsv. | smallint sans signe |
| `search_page_num` | Utilisée par la dimension Classement de toutes les pages de recherche. Indique la page des résultats de recherche sur laquelle votre site est apparu avant que l’utilisateur n’ait cliqué sur votre site. | smallint sans signe |
| `secondary_hit` | Indicateur qui effectue le suivi des accès secondaires. Il est généralement issu du balisage multi-suite et des règles VISTA qui copient les accès. | tinyint sans signe |
| `service` | Inutilisé. Utilisez plutôt page_. | char(2) |
| `socialaccountandappids` | N’est plus utilisé. ID de compte et d’application sociaux | varchar(255) |
| `socialassettrackingcode` | N’est plus utilisé. Variable de campagne sociale | varchar(255) |
| `socialauthor` | N’est plus utilisé. Variable Auteurs de réseau social | varchar(255) |
| `socialcontentprovider` | N’est plus utilisé. Plateformes sociales/Propriétés | varchar(255) |
| `socialinteractiontype` | N’est plus utilisé. Type d’interaction sociale | varchar(255) |
| `sociallanguage` | N’est plus utilisé. Langue sociale | varchar(255) |
| `sociallatlong` | N’est plus utilisé. Latitude/Longitude sociale | varchar(255) |
| `socialowneddefinitioninsighttype` | N’est plus utilisé. Type d’informations sur la définition détenue sociale | varchar(255) |
| `socialowneddefinitioninsightvalue` | N’est plus utilisé. Valeur d’informations sur la définition détenue sociale | varchar(255) |
| `socialowneddefinitionmetric` | N’est plus utilisé. Mesure de définition détenue sociale | varchar(255) |
| `socialowneddefinitionpropertyvspost` | N’est plus utilisé. Propriété de définition détenue par Social par rapport à la publication | varchar(255) |
| `socialownedpostids` | N’est plus utilisé. Identifiants de publication détenus par Social | varchar(255) |
| `socialownedpropertyid` | N’est plus utilisé. ID de propriété détenue sociale | varchar(255) |
| `socialownedpropertyname` | N’est plus utilisé. Nom de propriété détenue par Social | varchar(255) |
| `socialownedpropertypropertyvsapp` | N’est plus utilisé. Propriété détenue par Social et application | varchar(255) |
| `state` | Variable d’état. | varchar(50) |
| `stats_server` | Pas d&#39;utilité. Serveur interne d’Adobe qui a traité l’accès. | char(30) |
| `t_time_info` | Heure locale du. Le format est le suivant : M/J/AAAA HH:MM:SS Mois (0-11, 0=Janvier) Fuseau horaire (en minutes) | varchar(100) |
| `tnt` | Utilisé dans les intégrations de  Adobe. | text |
| `tnt_action` | Utilisé dans les intégrations de  Adobe. | text |
| `tnt_post_vista` | N’est plus utilisé. Utilisez post_tnt à la place. | text |
| `transactionid` | Identifiant unique dans lequel plusieurs points de données peuvent être transférés ultérieurement par l’intermédiaire de sources de données. | text |
| `truncated_hit` | Indicateur indiquant que la demande d’image a été tronquée. Indique qu’un accès partiel a été reçu. <br>Y : l’accès a été tronqué ; accès partial reçu <br>N : l’accès n’a pas été tronqué ; accès complet reçu | char(1) |
| `ua_color` | N’est plus utilisé. Anciennement utilisé comme valeur de secours pour la profondeur de couleur. | char(20) |
| `ua_os` | N’est plus utilisé. Anciennement utilisé comme secours pour le système d’exploitation. | char(80) |
| `ua_pixels` | N’est plus utilisé. Anciennement utilisé comme secours pour la hauteur et la largeur du navigateur. | char(20) |
| `user_agent` | Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image. | text |
| `user_hash` | Pas d&#39;utilité. Hachage sur l’identifiant de la suite de rapports. Utilisez username à la place. | int sans signe |
| `user_server` | Variable utilisée dans la dimension Serveur. | varchar(100) |
| `userid` | Pas d&#39;utilité. ID numérique de l’identifiant de suite de rapports. Utilisez username à la place. | int sans signe |
| `username` | Identifiant de la suite de rapports pour l’accès. | char(40) |
| `va_closer_detail` | Variable utilisée dans la dimension Détails de la dernière touche. | varchar(255) |
| `va_closer_id` | ID numérique qui identifie la dimension  Dernière touche. La recherche de cet identifiant est disponible dans le Gestionnaire de  de Marketing Cloud. | tinyint sans signe |
| `va_finder_detail` | Variable utilisée dans la dimension Détails de la première touche. | varchar(255) |
| `va_finder_id` | ID numérique qui identifie la dimension  Première touche. La recherche de cet identifiant est disponible dans le Gestionnaire de  de Marketing Cloud. | tinyint sans signe |
| `va_instance_event` | Indicateur permettant d’identifier les instances de  Marketing. Utilisée par la mesure Instances de dernière touche du marketing. | tinyint sans signe |
| `va_new_engagement` | Indicateur permettant d’identifier le Marketing  les nouveaux engagements. Utilisée par la mesure Nouveaux engagements. | tinyint sans signe |
| `video` | Contenu vidéo | varchar(255) |
| `videoad` | Nom de la publicité vidéo | varchar(255) |
| `videoadinpod` | Position de la publicité vidéo dans la capsule | varchar(255) |
| `videoadlength` | Durée de la publicité vidéo | varchar(255) |
| `videoadload` | Chargements des publicités vidéo | varchar(255) |
| `videoadname` | Nom de la publicité vidéo | varchar(255) |
| `videoadplayername` | Nom du lecteur de publicités vidéo | varchar(255) |
| `videoadpod` | Capsule publicitaire vidéo | varchar(255) |
| `videoadvertiser` | Annonceur vidéo | varchar(255) |
| `videoaudioalbum` | Album audio vidéo | varchar(255) |
| `videoaudioartist` | Artiste audio vidéo | varchar(255) |
| `videoaudioauthor` | Auteur audio vidéo | varchar(255) |
| `videoaudiolabel` | Libellé audio vidéo | varchar(255) |
| `videoaudiopublisher` | Éditeur audio vidéo | varchar(255) |
| `videoaudiostation` | Station audio vidéo | varchar(255) |
| `videocampaign` | Campagne vidéo | varchar(255) |
| `videochannel` | Canal vidéo | varchar(255) |
| `videochapter` | Chapitre vidéo | varchar(255) |
| `videocontenttype` | Type de contenu vidéo. Défini automatiquement sur « Vidéo » pour toutes les consultations vidéo | varchar(255) |
| `videodaypart` | Moment de la journée de la vidéo | varchar(255) |
| `videoepisode` | Épisode de la vidéo | varchar(255) |
| `videofeedtype` | Type de flux vidéo | varchar(255) |
| `videogenre` | Genre de la vidéo | text |
| `videolength` | Longueur de la vidéo | varchar(255) |
| `videomvpd` | Vidéo MVPD | varchar(255) |
| `videoname` | Nom de la vidéo | varchar(255) |
| `videonetwork` | Réseau de la vidéo | varchar(255) |
| `videopath` | Chemin vidéo | varchar(100) |
| `videoplayername` | Nom du lecteur vidéo | varchar(255) |
| `videoqoebitrateaverageevar` | Vitesse moyenne de qualité vidéo | varchar(255) |
| `videoqoebitratechangecountevar` | Nombre de changements de qualité vidéo | varchar(255) |
| `videoqoebuffercountevar` | Nombre de tampons de qualité vidéo | varchar(255) |
| `videoqoebuffertimeevar` | Période tampon de la qualité vidéo | varchar(255) |
| `videoqoedroppedframecountevar` | Nombre d’images perdues de qualité vidéo | varchar(255) |
| `videoqoeerrorcountevar` | Nombre d’erreurs de qualité vidéo | varchar(255) |
| `videoqoeextneralerrors` | Erreurs externes de la qualité vidéo | text |
| `videoqoeplayersdkerrors` | Erreurs du SDK de la qualité vidéo | text |
| `videoqoetimetostartevar` | Durée de qualité de la vidéo au  | varchar(255) |
| `videoseason` | Saison de la vidéo | varchar(255) |
| `videosegment` | Segment de vidéo | varchar(255) |
| `videoshow` | Affichage de la vidéo | varchar(255) |
| `videoshowtype` | Type d’affichage de la vidéo | varchar(255) |
| `videostreamtype` | Type de flux vidéo | varchar(255) |
| `visid_high` | Utilisé en combinaison avec visid_low pour identifier de manière unique une visite. | bigint sans signe |
| `visid_low` | Utilisé en combinaison avec visid_high pour identifier de manière unique une visite. | bigint sans signe |
| `visid_new` | Indicateur qui identifie si l’accès contient un ID de nouvellement généré. | char(1) |
| `visid_timestamp` | Si l’ID de a été généré récemment, fournit l’horodatage (en heure Unix) du moment où l’ID de a été généré. | int |
| `visid_type` | Identifiant numérique représentant la méthode utilisée pour identifier le visiteur. <br>0 : visitorID personnalisé <br>1 : solution de secours de l’IP et de l’agent utilisateur <br>2 : en-tête de l’abonné mobile HTTP <br>3 : valeur du cookie hérité (s_vi) <br>4 : valeur du cookie de solution de secours (s_fid) <br>5 : service d’identité | tinyint sans signe |
| `visit_keywords` | Variable utilisée dans la dimension Mot-clé de recherche. Cette colonne utilise une limite de caractères non standard pour s’adapter à la logique de back-end utilisée par Adobe. | varchar(244) |
| `visit_num` | Variable utilisée dans la dimension Nombre de visites. à 1 et incrémente chaque fois qu’un nouveau de visite  par. | int sans signe |
| `visit_page_num` | Variable utilisée dans la dimension Profondeur d’accès. Augmente de 1 pour chaque accès généré par l’utilisateur. Réinitialise chaque visite. | int sans signe |
| `visit_ref_domain` | Basé sur la colonne visit_. Premier domaine référent de la visite. | varchar(100) |
| `visit_ref_type` | Identifiant numérique représentant le type de  du premier  de la visite. Utilise la table de recherche _type.tsv. | tinyint sans signe |
| `visit_referrer` | Premier de la visite. | varchar(255) |
| `visit_search_engine` | Identifiant numérique du premier moteur de recherche de la visite. Utilise la table de recherche search_engine.tsv. | smallint sans signe |
| `visit_start_page_url` | Première URL de la visite. | varchar(255) |
| `visit_start_pagename` | Nom de la première page de la visite. | varchar(100) |
| `visit_start_time_gmt` | Horodatage (heure Unix) du premier accès de la visite. | int |
| `weekly_visitor` | Indicateur qui détermine si l’accès est un nouveau hebdomadaire. | tinyint sans signe |
| `yearly_visitor` | Indicateur qui détermine si l’accès est un nouveau annuel. | tinyint sans signe |
| `zip` | Permet de renseigner la dimension Code postal. | varchar(50) |

## Colonnes vides

La liste de colonnes suivante n’est pas utilisée et ne contient pas de données :

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>device-manufacturer
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoreratingdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinkid<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (obsolète)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (obsolète)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (obsolète)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (obsolète)
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplayed
