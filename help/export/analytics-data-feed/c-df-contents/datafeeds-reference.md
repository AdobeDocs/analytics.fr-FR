---
description: Tableau décrivant les colonnes du flux de données.
keywords: Data Feed;columns
subtopic: data feeds
title: Référence des colonnes de données
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: e9158f4c1ea2fc338116df34d6c6edf93ff7050e

---


# Référence des colonnes de données

Utilisez cette page pour savoir quelles données sont contenues dans chaque colonne. La plupart des implémentations n’utilisent pas toutes les colonnes. Cette page peut donc être référencée lors de la détermination des colonnes à inclure dans une exportation de flux de données.

> [!IMPORTANT] Pour une colonne donnée (par exemple, une colonne définie à 255 caractères), un flux de données peut envoyer des caractères supplémentaires en raison de l’ajout de caractères qui échappent aux valeurs dans une chaîne. Gardez ces caractères supplémentaires potentiels à l’esprit si votre implémentation envoie régulièrement des valeurs dépassant les limites de caractères.

## Colonnes, descriptions et types de données

> [!NOTE] La plupart des colonnes contiennent une colonne similaire avec un préfixe de `post_`. Les colonnes « Post » contiennent les valeurs suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. Pour plus d’informations, voir FAQ [sur les flux de](../df-faq.md) données.

| Nom de la colonne | Description de la colonne | Type de données |
| --- | --- | --- |
| `accept_language` | Liste toutes les langues acceptées, comme indiqué dans l’en-tête HTTP Accept-Language lors d’une demande d’image. | char(20) |
| `aemassetid` | Variable à plusieurs valeurs correspondant aux ID de ressource (identificateurs globaux uniques) d’un ensemble de ressources d’Adobe Experience Manager. Incrémente l’événement Impression. | text |
| `aemassetsource` | Identifie la source de l’événement de ressources. Utilisée dans Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID de ressource d’une ressource Adobe Experience Manager. Incrémente l’événement Click. | varchar(255) |
| `browser` | Identifiant numérique du navigateur. Fait référence à la table de recherche de browser.tsv. | int non signé |
| `browser_height` | Hauteur en pixels de la fenêtre du navigateur. | petit entier non signé |
| `browser_width` | Largeur en pixels de la fenêtre du navigateur. | petit entier non signé |
| `c_color` | Codage en bits de la palette de couleurs. Utilisée dans le cadre du calcul de la dimension Intensité de couleur. Utilise la fonction JavaScript screen.colorDepth(). | char(20) |
| `campaign` | Variable utilisée dans la dimension Code de suivi. | varchar(255) |
| `carrier` | Variable d’intégration Adobe Advertising Cloud. Définit l’opérateur de téléphonie mobile. Fait référence à la table de recherche des opérateurs. | varchar(100) |
| `channel` | Variable utilisée dans la dimension Sections du site. | varchar(100) |
| `click_action` | N’est plus utilisé. Adresse du lien cliqué dans l’outil hérité Clickmap. | varchar(100) |
| `click_action_type` | N’est plus utilisé. Type de lien de l’outil hérité Clickmap.<br>0 : URL<br>HREF 1 : ID<br>personnalisé 2 : Événement<br>onClick JavaScript 3 : Elément de formulaire | tinyint sans signe |
| `click_context` | N’est plus utilisé. Nom de la page où un clic a été fait sur les liens. Partie de l’outil hérité Clickmap. | varchar(255) |
| `click_context_type` | N’est plus utilisé. Indique si click_context avait un nom de page ou une URL de page par défaut.<br>0 : URL<br>de page 1 : Nom de page | tinyint sans signe |
| `click_sourceid` | N’est plus utilisé. Identifiant numérique pour l’emplacement sur la page du lien cliqué. Partie de l’outil hérité Clickmap. | int non signé |
| `click_tag` | N’est plus utilisé. Type d’élément HTML sur lequel on a cliqué. | char(10) |
| `clickmaplink` | Lien de Carte d’activités | varchar(255) |
| `clickmaplinkbyregion` | Lien Carte d’activités par région | varchar(255) |
| `clickmappage` | Page Carte d’activités | varchar(255) |
| `clickmapregion` | Région Carte d’activités | varchar(255) |
| `code_ver` | Version de la bibliothèque AppMeasurement utilisée pour compiler et envoyer la demande d’image. | char(16) |
| `color` | Identifiant de l’intensité des couleurs basé sur la valeur de la colonne c_color. Fait référence à la table de recherche de color_depth.tsv. | petit entier non signé |
| `connection_type` | Identifiant numérique représentant le type de connexion. Variable utilisée dans la dimension Type de connexion. Fait référence à la table de recherche de connection_type.tsv. | tinyint sans signe |
| `cookies` | Variable utilisée dans la dimension Prise en charge des cookies.<br>Y :<br>EnabledN :<br>DisabledU : Inconnu | char(1) |
| `country` | Identifiant numérique représentant le pays d’où provient l’accès. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. Utilise la recherche de country.tsv. | petit entier non signé |
| `ct_connect_type` | Liée à la colonne connection_type. Les valeurs les plus courantes sont LAN/Wi-Fi, Opérateur de téléphonie mobile et Modem. | char(20) |
| `curr_factor` | Détermine la décimale de la devise et est utilisée pour la conversion de devise. Par exemple, le dollar américain (USD) utilise deux décimales, donc cette valeur de colonne serait de 2. | tinyint |
| `curr_rate` | Taux de change au moment de la transaction. Adobe travaille en partenariat avec XE pour déterminer le taux de change du jour. | decimal(24,12) |
| `currency` | Le code de devise qui a été utilisé pendant la transaction. | char(8) |
| `cust_hit_time_gmt` | Suites de rapports avec horodatage uniquement. Horodatage envoyé avec l’accès, basé sur l’heure Unix. | int |
| `cust_visid` | Si un identifiant visiteur personnalisé est défini, il est indiqué dans cette colonne. | varchar(255) |
| `daily_visitor` | Indicateur qui détermine si l’accès est un nouveau visiteur quotidien. | tinyint sans signe |
| `date_time` | Heure de l’accès dans un format lisible, basée sur le fuseau horaire de la suite de rapports. | Heure du jour |
| `domain` | Variable utilisée dans la dimension Domaine. Basée sur le fournisseur d’accès Internet (FAI) de l’utilisateur. | varchar(100) |
| `duplicate_events` | Répertorie chaque événement compté comme double. | varchar(255) |
| `duplicate_purchase` | Indicateur signifiant que l’événement d’achat pour cet accès doit être ignoré, car il s’agit d’un double. | tinyint sans signe |
| `duplicated_from` | Utilisée uniquement dans les suites de rapports contenant les règles VISTA de la copie de l’accès. Indique la suite de rapports à partir de laquelle l’accès a été copié. | varchar(40) |
| `ef_id` | ef_id utilisée dans les intégrations Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variables personnalisées 1-250. Chaque organisation utilise les eVars différemment. Le meilleur outil pour obtenir plus d’informations sur la façon dont votre organisation renseigne les eVars respectifs serait un document de conception de solution spécifique à votre organisation. | varchar(255) |
| `event_list` | Liste séparée par des virgules d’identifiants numériques représentant les événements déclenchés lors de l’accès. Comprend à la fois les événements par défaut et les événements personnalisés 1-1000. Utilise la recherche d’event.tsv. | text |
| `exclude_hit` | Indicateur signifiant que l’accès est exclu de la création de rapports. La colonne visit_num n’est pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Fait partie d’une fonction mise à l’écart.<br>2 : Inutilisée. Fait partie d’une fonction mise à l’écart.<br>3 : Plus utilisé. Exclusion<br>de l’agent utilisateur 4 : Exclusion basée sur l’adresse<br>IP 5 : Informations d’accès vitales manquantes, telles que page_url, pagename, page_event ou event_list<br>6 : JavaScript n’a pas correctement traité l’accès<br>7 : Exclusion spécifique au compte, telle que dans les règles<br>VISTA 8 : Non utilisé. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Fait partie d’une fonction mise à l’écart.<br>10 : Code<br>de devise11 non valide : Accès manquant d’un horodatage sur une suite de rapports horodatée uniquement ou accès contenant un horodatage sur une suite<br>de rapports non horodatée12 : Non utilisé. Fait partie d’une fonction mise à l’écart.<br>13 : Inutilisée. Fait partie d’une fonction mise à l’écart.<br>14 : Accès cible qui ne correspondait pas à un accès<br>Analytics15 : Non utilisé actuellement.<br>16 : Accès à Advertising Cloud qui ne correspondait pas à un accès Analytics | tinyint sans signe |
| `first_hit_page_url` | La toute première URL du visiteur. | varchar(255) |
| `first_hit_pagename` | Variable utilisée dans la dimension Page d’accès d’origine. Le nom de la page d’entrée d’origine du visiteur. | varchar(100) |
| `first_hit_ref_domain` | Variable utilisée dans la dimension Domaine référent initial. Basée sur first_hit_referrer. Le tout premier domaine référent du visiteur. | varchar(100) |
| `first_hit_ref_type` | Identifiant numérique représentant le type de référent du tout premier référent du visiteur. Utilise la recherche de referrer_type.tsv. | tinyint sans signe |
| `first_hit_referrer` | La toute première URL de référence du visiteur. | varchar(255) |
| `first_hit_time_gmt` | Horodatage du tout premier accès du visiteur en heure Unix. | int |
| `geo_city` | Nom de la ville d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et la ville. | char(32) |
| `geo_country` | Abréviation du pays d’origine de l’accès, basée sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. | char(4) |
| `geo_dma` | Identifiant numérique de la zone démographique d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et la zone démographique. | int non signé |
| `geo_region` | Nom de l’état ou de la région d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et l’état/la région. | char(32) |
| `geo_zip` | Code postal d’où provient l’accès, en fonction de l’adresse IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le code postal. | varchar(16) |
| `hier1 - hier5` | Utilisée par les variables hiérarchiques. Contient une liste délimitée de valeurs. Le délimiteur est sélectionné dans les paramètres de la suite de rapports. | varchar(255) |
| `hit_source` | Indique la source de l’accès. <br>1 : Demande d’image standard sans horodatage <br>2 : Demande d’image standard avec horodatage <br>3 : Téléchargement de la source de données en direct avec horodatage <br>4 : Non utilisé <br>5 : Transfert de source de données générique <br>6 : Transfert de source de données en traitement complet <br>7 : Transfert de la source de données TransactionID <br>8 : Plus utilisé; Versions précédentes des sources de données Adobe Advertising Cloud <br>9 : Plus utilisé; Mesures de résumé d’Adobe Social | tinyint sans signe |
| `hit_time_gmt` | L’horodatage des serveurs de collecte de données Adobe d’accès a reçu l’accès, selon l’heure Unix. | int |
| `hitid_high` | Utilisée en combinaison avec hitid_low pour identifier de manière unique un accès. | bigent non signé |
| `hitid_low` | Utilisée en combinaison avec hitid_high pour identifier de manière unique un accès. | bigent non signé |
| `homepage` | N’est plus utilisé. Indique si l’URL active est la page d’accueil du navigateur. | char(1) |
| `hourly_visitor` | Indicateur qui détermine si l’accès est un nouveau visiteur horaire. | tinyint sans signe |
| `ip` | Adresse IP, basée sur l’en-tête HTTP de la demande d’image. | char(20) |
| `ip2` | Inutilisé. Variable de référence du serveur principal pour les suites de rapports contenant des règles VISTA basées sur l’adresse IP. | char(20) |
| `j_jscript` | Version de JavaScript prise en charge par le navigateur. | char(5) |
| `java_enabled` | Indicateur précisant si Java est activé. <br>Y : Activé <br>N : Désactivé <br>U : Inconnu | char(1) |
| `javascript` | Identifiant de recherche de la version JavaScript, basé sur j_jscript. Utilise une table de recherche. | tinyint sans signe |
| `language` | Identifiant numérique de la langue. Utilise la table de recherche de languages.tsv. | petit entier non signé |
| `last_hit_time_gmt` | Horodatage (en heure Unix) de l’accès précédent. Utilisé pour calculer la dimension Jours depuis la dernière visite. | int |
| `last_purchase_num` | Variable utilisée dans la dimension Fidélisation des clients. Indique le nombre d’achats précédents effectués par le visiteur. <br>0 : Aucun achat préalable (pas client) <br>1 : 1 achat préalable (nouveau client) <br>2 : 2 achats antérieurs (client régulier) <br>3 : 3 achats antérieurs ou plus (client fidèle) | int non signé |
| `last_purchase_time_gmt` | Utilisée dans la dimension Jours depuis le dernier achat. Horodatage (en heure Unix) du dernier achat effectué. Pour les premiers achats et les visiteurs qui n’avaient jamais effectué d’achat auparavant, cette valeur est de 0. | int |
| `latlon1` | Lieu (jusqu’à 10 km) | varchar(255) |
| `latlon23` | Lieu (jusqu’à 100 m) | varchar(255) |
| `latlon45` | Lieu (jusqu’à 1 m) | varchar(255) |
| `mc_audiences` | Liste des identifiants de segment Audience Manager auxquels le visiteur appartient. | text |
| `mcvisid` | Identifiant visiteur Experience Cloud. Nombre 128 bits constitué de deux nombres 64 bits concaténés complétés par 19 chiffres. | varchar(255) |
| `mobile_id` | Si l’utilisateur utilise un périphérique mobile, l’ID numérique du périphérique. | int |
| `mobileaction` | Action mobile. Collectée automatiquement lorsque trackAction est appelé dans Mobile Services. Permet le cheminement d’action automatique dans l’application. | varchar(100) |
| `mobileappid` | ID de l’application mobile Stocke le nom et la version de l’application au format suivant :[AppName][BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Utilisé dans le connecteur de données Apteligent. ID d’application utilisé dans Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Utilisé dans le connecteur de données Apteligent. ID de plantage utilisé dans Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Utilisé dans le connecteur de données AppFigures. ID d’objet de boutique d’applications | varchar(255) |
| `mobilebeaconmajor` | Principale balise Mobile Services | varchar(100) |
| `mobilebeaconminor` | Balise de services mobiles mineure | varchar(100) |
| `mobilebeaconproximity` | Proximité de la balise Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UID de balise Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Le nom ou l’identifiant du contenu qui a affiché le lien. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignmedium` | Support marketing, une bannière ou un courrier électronique par exemple. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignname` | Nom de la campagne, également stocké dans la variable de campagne. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignsource` | Référent original, comme la newsletter ou les médias sociaux. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobilecampaignterm` | Mots-clés ou autres termes payés dont vous souhaitez effectuer le suivi avec cette acquisition. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| `mobiledayofweek` | Numéro du jour de la semaine où l’application a été lancée. | varchar(255) |
| `mobiledayssincefirstuse` | Nombre de jours depuis que l’application a été lancée pour la première fois. | varchar(255) |
| `mobiledayssincelastupgrade` | Collecté à partir de la variable de données contextuelles a.DaysSinceLastUpgrade. Nombre de jours écoulés depuis la session précédente. | varchar(255) |
| `mobiledayssincelastuse` | Nombre de jours depuis la dernière exécution de l’application. | varchar(255) |
| `mobiledeeplinkid` | Collecté à partir de la variable de données contextuelles a.<span>deeplink</span>.id. Utilisé dans les rapports d’acquisition en tant qu’identifiant du lien d’acquisition mobile. | varchar(255) |
| `mobiledevice` | Nom du périphérique mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparés par des virgules. Le premier chiffre représente la génération de l’appareil, le second la famille d’appareils. | varchar(255) |
| `mobilehourofday` | Définit l’heure du jour où l’application a été lancée. Suit un format numérique de 24 heures. | varchar(255) |
| `mobileinstalldate` | Date de l’installation mobile. Indique la date de la première ouverture d’une application mobile par un utilisateur. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Collecté à partir de la variable de données contextuelles a.LaunchesSinceUpgrade. Indique le nombre de lancements depuis la dernière mise à niveau. | varchar(255) |
| `mobilelaunchnumber` | Est incrémentée d’une unité chaque fois que l’application mobile est lancée. | varchar(255) |
| `mobileltv` | N’est plus utilisé. Renseignée par les méthodes trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Collecté à partir de la variable de données contextuelles a.<span>message</span>.button.id. Utilisé pour la messagerie in-app afin d’identifier le bouton qui a fermé le message. | varchar(100) |
| `mobilemessageid` | ID de message in-app | varchar(255) |
| `mobilemessageonline` | Message in-app en ligne | varchar(255) |
| `mobilemessagepushoptin` | Collecté à partir de la variable de données contextuelles a.push.optin. Définissez cette variable sur &quot;true&quot; lorsque l’utilisateur choisit de transmettre la messagerie push ; dans le cas contraire, la valeur est &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Collecté à partir de la variable de données contextuelles a.push.payloadid. Utilisé dans la messagerie push comme identifiant de charge utile. | varchar(255) |
| `mobileosenvironment` | Collectée à partir de la variable de données contextuelles a.OSEnvirMENT. Indique l’environnement du système d’exploitation, tel qu’Android ou iOS. | varchar(255) |
| `mobileosversion` | Version du système d’exploitation Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Collecté à partir de la variable de données contextuelles a.loc.ac. Indique la précision du GPS en mètres au moment de la collecte. | varchar(255) |
| `mobileplacecategory` | Collecté à partir de la variable de données contextuelles a.loc.category. Décrit la catégorie d’un endroit spécifique. | varchar(255) |
| `mobileplaceid` | Collecté à partir de la variable de données contextuelles a.<span>loc</span>.id. Identifiant d’un point d’intérêt donné. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenu de lancement de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Moyenne de lancement des services mobiles | varchar(255) |
| `mobilerelaunchcampaignsource` | Source de lancement Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Terme de lancement des services mobiles | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Collecté à partir de la variable de données contextuelles a.launch.campaign.trackingcode. Utilisé dans acquisition comme code de suivi pour la campagne de lancement. | varchar(255) |
| `mobileresolution` | Résolution de l’appareil mobile. Largeur x hauteur en pixels. | varchar(255) |
| `monthly_visitor` | Indicateur signifiant que le visiteur est unique pour le mois en cours. | tinyint sans signe |
| `mvvar1` - `mvvar3` | Valeurs des variables de liste. Contient une liste délimitée de valeurs personnalisées en fonction de l’implémentation. | text |
| `namespace` | Inutilisé. Partie d’une fonctionnalité mise au rebut il y a de nombreuses années. | varchar(50) |
| `new_visit` | Indicateur qui détermine si l’accès actif est une nouvelle visite. Valeur définie par les serveurs d’Adobe après 30 minutes d’inactivité au niveau de la visite. | tinyint sans signe |
| `os` | Identifiant numérique représentant le système d’exploitation du visiteur. Basé sur la colonne user_agent. Utilise la table de recherche de l’os. | int non signé |
| `p_plugins` | N’est plus utilisé. Liste de plugins disponibles pour le navigateur. Utilisation de la fonction JavaScript navigator.plugins(). | text |
| `page_event` | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). See [Page event lookup](datafeeds-page-event.md). | tinyint sans signe |
| `page_event_var1` | Uniquement utilisée dans les demandes d’image de suivi des liens. URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. | text |
| `page_event_var2` | Uniquement utilisée dans les demandes d’image de suivi des liens. Nom personnalisé (le cas échéant) du lien. | varchar(100) |
| `page_event_var3` | N’est plus utilisé. Contient les données des modules Survey et Media. Rapports vidéo hérités générés dans les versions précédentes d’Adobe Analytics. | text |
| `page_type` | Utilisée pour indiquer la dimension Pages introuvables, utilisée exclusivement pour les pages 404. Cette variable doit être vide ou contenir « ErrorPage ». | char(20) |
| `page_url` | URL de l’accès. N’est pas utilisée dans les demandes d’image du suivi des liens. | varchar(255) |
| `pagename` | Utilisée pour indiquer la dimension Pages. Si la variable pagename est vide, Analytics utilise la variable page_url en remplacement. | varchar(100) |
| `paid_search` | Indicateur qui est défini si l’accès correspond à la détection de recherche payante. | tinyint sans signe |
| `partner_plugins` | Inutilisé. Partie d’une fonctionnalité mise au rebut il y a de nombreuses années. | varchar(255) |
| `persistent_cookie` | Utilisée par la dimension Prise en charge des cookies persistants. Indique si le visiteur prend en charge les cookies qui ne sont pas ignorés après chaque accès. | char(1) |
| `plugins` | N’est plus utilisé. Liste des identifiants numériques qui correspondent aux plugins disponibles dans le navigateur. Utilise la recherche de plugins.tsv. | varchar(180) |
| `pointofinterest` | Nom du point ciblé Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distance des services mobiles au centre d’intérêt | varchar(255) |
| `post_ columns` | Contient la valeur finalement utilisée dans les rapports. Chaque colonne « Post » est renseignée suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. | Voir la colonne « Non post » correspondante. |
| `prev_page` | Inutilisé. Identifiant propriétaire Adobe de la page précédente. | int non signé |
| `product_list` | Liste des produits telle que transmise par l’intermédiaire de la variable « products ». Les produits sont délimités par des virgules, tandis que les propriétés des produits individuels sont délimitées par des points-virgules. | text |
| `product_merchandising` | Inutilisé. Utilisez product_list à la place. | text |
| `prop1` - `prop75` | Variables de trafic personnalisées 1 - 75. | varchar(100) |
| `purchaseid` | Identificateur unique pour un achat, tel qu’il est défini à l’aide de la variable s_purchaseID. Utilisé par la colonne duplicate_purchase. | char(20) |
| `quarterly_visitor` | Indicateur qui détermine si l’accès est un nouveau visiteur trimestriel. | tinyint sans signe |
| `ref_domain` | Basée sur la colonne Référent. Domaine référent de l’accès. | varchar(100) |
| `ref_type` | Identifiant numérique représentant le type de référence pour l’accès.<br>1 : Dans votre site<br>2 : Autres sites Web <br>3 : Moteurs de recherche <br>4 : Disque dur <br>5 : USENET <br>6 : Tapé/marqué (sans référent) <br>7 : Courriel <br>8 : Aucun code JavaScript <br>9 : Réseaux sociaux | tinyint sans signe |
| `referrer` | URL de la page précédente. Notez que, bien que `referrer` utilise un type de données de varchar(255), `post_referrer` utilise un type de données de varchar(244). | varchar(255) |
| `resolution` | Identifiant numérique représentant la résolution de l’écran. Indique la dimension Résolution de l’écran. Utilise la table de recherche de resolution.tsv. | petit entier non signé |
| `s_kwcid` | ID de mot-clé utilisé dans les intégrations d’Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valeur brute de la résolution de l’écran. Collectée à l’aide de la fonction JavaScript screen.width x screen.height. | char(20) |
| `sampled_hit` | N’est plus utilisé. Anciennement utilisée pour l’échantillonnage dans Ad Hoc Analysis. | char(1) |
| `search_engine` | Identifiant numérique représentant le moteur de recherche qui a référé le visiteur à votre site. Utilise la table de recherche de search_engines.tsv. | petit entier non signé |
| `search_page_num` | Utilisée par la dimension Classement de toutes les pages de recherche. Indique sur quelle page de résultats de recherche votre site est apparu avant que l’utilisateur ne clique sur votre site. | petit entier non signé |
| `secondary_hit` | Indicateur qui suit les accès secondaires. Normalement, il provient du balisage multisuite et des règles VISTA qui copient les accès. | tinyint sans signe |
| `service` | Inutilisé. Utilisez page_event à la place. | char(2) |
| `socialaccountandappids` | N’est plus utilisé. Identifiants de comptes sociaux et d’application | varchar(255) |
| `socialassettrackingcode` | N’est plus utilisé. Variable de campagne sociale | varchar(255) |
| `socialauthor` | N’est plus utilisé. Variable des auteurs du module Social | varchar(255) |
| `socialcontentprovider` | N’est plus utilisé. Plateformes sociales / Propriétés | varchar(255) |
| `socialinteractiontype` | N’est plus utilisé. Type d’interaction sociale | varchar(255) |
| `sociallanguage` | N’est plus utilisé. Langage social | varchar(255) |
| `sociallatlong` | N’est plus utilisé. Latitude / Longitude sociale | varchar(255) |
| `socialowneddefinitioninsighttype` | N’est plus utilisé. Type d’informations sur la définition détenue sur réseau social | varchar(255) |
| `socialowneddefinitioninsightvalue` | N’est plus utilisé. Valeur d’informations sur la définition détenue sur réseau social | varchar(255) |
| `socialowneddefinitionmetric` | N’est plus utilisé. Mesure de définition détenue sur réseau social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | N’est plus utilisé. Propriété de définition détenue sur réseau social/publication | varchar(255) |
| `socialownedpostids` | N’est plus utilisé. Identifiants de publications détenues sur réseau social | varchar(255) |
| `socialownedpropertyid` | N’est plus utilisé. Identifiant de propriété détenue sur réseau social | varchar(255) |
| `socialownedpropertyname` | N’est plus utilisé. Nom de propriété détenue sur réseau social | varchar(255) |
| `socialownedpropertypropertyvsapp` | N’est plus utilisé. Propriété détenue sur réseau social/application | varchar(255) |
| `state` | Variable d’état. | varchar(50) |
| `stats_server` | Inutilisable. Serveur interne d’Adobe qui a traité l’accès. | char(30) |
| `t_time_info` | Heure locale pour le visiteur. Le format est le suivant : M/D/AAAA HH:MM:SS Mois (0-11, 0=Janvier) Décalage du fuseau horaire (en minutes) | varchar(100) |
| `tnt` | Utilisée dans les intégrations Adobe Target. | text |
| `tnt_action` | Utilisée dans les intégrations Adobe Target. | text |
| `tnt_post_vista` | N’est plus utilisé. Utilisez post_tnt à la place. | text |
| `transactionid` | Identifiant unique vers lequel plusieurs points de données pourront être transférés plus tard au moyen de sources de données. | text |
| `truncated_hit` | Indicateur signifiant que la demande d’image a été tronquée. Indique qu’un accès partiel a été reçu. <br>Y : L’accès a été tronqué ; accès partiel reçu <br>N : L’accès n’a pas été tronqué ; accès complet reçu | char(1) |
| `ua_color` | N’est plus utilisé. Anciennement utilisée comme solution de secours pour l’intensité de couleur. | char(20) |
| `ua_os` | N’est plus utilisé. Anciennement utilisée comme solution de secours pour le système d’exploitation. | char(80) |
| `ua_pixels` | N’est plus utilisé. Anciennement utilisée comme solution de secours pour la hauteur et la largeur du navigateur. | char(20) |
| `user_agent` | Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image. | text |
| `user_hash` | Inutilisable. Hachage de l’identifiant de suite de rapports. Utilisez le nom d’utilisateur à la place. | int non signé |
| `user_server` | Variable utilisée dans la dimension Serveur. | varchar(100) |
| `userid` | Inutilisable. Identifiant numérique pour l’identifiant de suite de rapports. Utilisez le nom d’utilisateur à la place. | int non signé |
| `username` | Identifiant de la suite de rapports pour l’accès. | char(40) |
| `va_closer_detail` | Variable utilisée dans la dimension Détails de Dernière touche. | varchar(255) |
| `va_closer_id` | Identifiant numérique qui identifie la dimension Canal Dernière touche. La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| `va_finder_detail` | Variable utilisée dans la dimension Détails de Première touche. | varchar(255) |
| `va_finder_id` | Identifiant numérique qui identifie la dimension Canal Première touche. La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| `va_instance_event` | Indicateur pour identifier les instances de canal marketing. Utilisé par la mesure Instances Dernière touche des canaux marketing. | tinyint sans signe |
| `va_new_engagement` | Indicateur pour identifier les nouveaux engagements de canal marketing. Utilisé par la mesure Nouveaux engagements. | tinyint sans signe |
| `video` | Contenu vidéo | varchar(255) |
| `videoad` | Nom de la publicité vidéo | varchar(255) |
| `videoadinpod` | Publicité vidéo en position pochette | varchar(255) |
| `videoadlength` | Longueur de la publicité vidéo | varchar(255) |
| `videoadload` | Chargements de publicités vidéo | varchar(255) |
| `videoadname` | Nom de la publicité vidéo | varchar(255) |
| `videoadplayername` | Nom du lecteur vidéo | varchar(255) |
| `videoadpod` | Module Publicité vidéo | varchar(255) |
| `videoadvertiser` | Publicitaire vidéo | varchar(255) |
| `videoaudioalbum` | Album audio vidéo | varchar(255) |
| `videoaudioartist` | Artiste audio vidéo | varchar(255) |
| `videoaudioauthor` | Auteur audio vidéo | varchar(255) |
| `videoaudiolabel` | Libellé audio vidéo | varchar(255) |
| `videoaudiopublisher` | Éditeur audio vidéo | varchar(255) |
| `videoaudiostation` | Station audio vidéo | varchar(255) |
| `videocampaign` | Campagne vidéo | varchar(255) |
| `videochannel` | Canal vidéo | varchar(255) |
| `videochapter` | Nom du chapitre vidéo | varchar(255) |
| `videocontenttype` | Type de contenu vidéo. Défini automatiquement sur « Vidéo » pour toutes les consultations vidéo | varchar(255) |
| `videodaypart` | Partie du jour de la vidéo | varchar(255) |
| `videoepisode` | Épisode vidéo | varchar(255) |
| `videofeedtype` | Type de flux vidéo | varchar(255) |
| `videogenre` | Genre vidéo | text |
| `videolength` | Durée de la vidéo | varchar(255) |
| `videomvpd` | MVPD vidéo | varchar(255) |
| `videoname` | Nom de la vidéo | varchar(255) |
| `videonetwork` | Réseau vidéo | varchar(255) |
| `videopath` | Chemin de la vidéo | varchar(100) |
| `videoplayername` | Nom du lecteur vidéo | varchar(255) |
| `videoqoebitrateaverageevar` | Débit en bits moyen de la qualité vidéo | varchar(255) |
| `videoqoebitratechangecountevar` | Nombre de changements au niveau de la qualité vidéo | varchar(255) |
| `videoqoebuffercountevar` | Nombre de tampons pour la qualité vidéo | varchar(255) |
| `videoqoebuffertimeevar` | Durée du tampon de qualité vidéo | varchar(255) |
| `videoqoedroppedframecountevar` | Nombre d’images perdues au niveau de la qualité vidéo | varchar(255) |
| `videoqoeerrorcountevar` | Comptage des erreurs de la qualité vidéo | varchar(255) |
| `videoqoeextneralerrors` | Erreurs externes de qualité vidéo | text |
| `videoqoeplayersdkerrors` | Erreurs du SDK de qualité vidéo | text |
| `videoqoetimetostartevar` | Temps de démarrage de la qualité vidéo | varchar(255) |
| `videoseason` | Saison vidéo | varchar(255) |
| `videosegment` | Segment de vidéo | varchar(255) |
| `videoshow` | Vidéo | varchar(255) |
| `videoshowtype` | Type d’affichage vidéo | varchar(255) |
| `videostreamtype` | Type de flux vidéo | varchar(255) |
| `visid_high` | Utilisée en combinaison avec visid_low pour identifier de manière unique une visite. | bigent non signé |
| `visid_low` | Utilisée en combinaison avec visid_high pour identifier de manière unique une visite. | bigent non signé |
| `visid_new` | Indicateur pour identifier si l’accès contient un identifiant visiteur nouvellement généré. | char(1) |
| `visid_timestamp` | Si l’identifiant visiteur a été récemment généré, cette variable fournit l’horodatage (en heure Unix) du moment où l’identifiant visiteur a été généré. | int |
| `visid_type` | Identifiant numérique représentant la méthode utilisée pour identifier le visiteur. <br>0 : Identifiant visiteur personnalisé <br>1 : Abandon IP et agent utilisateur <br>2 : En-tête d&#39;abonné mobile HTTP <br>3 : Valeur du cookie hérité (s_vi) <br>4 : Valeur du cookie de secours (s_fid) <br>5 : Service Identity | tinyint sans signe |
| `visit_keywords` | Variable utilisée dans la dimension Mot-clé de recherche. Cette colonne utilise une limite de caractères non standard pour s’adapter à la logique dorsale utilisée par Adobe. | varchar(244) |
| `visit_num` | Variable utilisée dans la dimension Nombre de visites. Commence à 1, et est incrémentée chaque fois qu’une nouvelle visite commence par visiteur. | int non signé |
| `visit_page_num` | Variable utilisée dans la dimension Détail des accès. Augmente de 1 pour chaque accès que l’utilisateur génère. Réinitialise chaque visite. | int non signé |
| `visit_ref_domain` | Basée sur la colonne visit_referrer. Le premier domaine référent de la visite. | varchar(100) |
| `visit_ref_type` | Identifiant numérique représentant le type de référent du premier référent de la visite. Utilise la table de recherche de referrer_type.tsv. | tinyint sans signe |
| `visit_referrer` | Le premier référent de la visite. | varchar(255) |
| `visit_search_engine` | Identifiant numérique du premier moteur de recherche de la visite. Utilise la table de recherche de search_engines.tsv. | petit entier non signé |
| `visit_start_page_url` | La première URL de la visite. | varchar(255) |
| `visit_start_pagename` | Nom de la première page de la visite. | varchar(100) |
| `visit_start_time_gmt` | Horodatage (en heure Unix) du premier accès de la visite. | int |
| `weekly_visitor` | Indicateur qui détermine si l’accès est un nouveau visiteur hebdomadaire. | tinyint sans signe |
| `yearly_visitor` | Indicateur qui détermine si l’accès est un nouveau visiteur annuel. | tinyint sans signe |
| `zip` | Utilisée pour indiquer la dimension Code postal. | varchar(50) |

## Colonnes vides

Les colonnes suivantes ne sont pas utilisées et ne contiennent pas de données :

* mobileacquisitionclics
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformance anceappid<span>.</span>app-perf-app-name
* mobileappperformance anceappid<span>.</span>app-perf-platform
* mobileappperformance ancecrashes
* mobileappperformance ancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgring
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>fabricant de périphérique
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>grade-catégorie-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>révision-titre
* mobileappstoreoneoffRecettes
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstoreration
* mobileappstoreratingdivisor
* mobileavgpréventive sessionlength
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
* mobilemonthnengagement-dusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaign trackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (obsolète)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (désapprouvée)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (désapprouvée)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (désapprouvée)
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
* videouniquetimeplaying
