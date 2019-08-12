---
description: Tableau décrivant les colonnes du flux de données.
keywords: Flux de données ; colonnes
seo-description: Tableau décrivant les colonnes du flux de données.
seo-title: Référence des colonnes de données
solution: Analytics
subtopic: flux de données
title: Référence des colonnes de données
topic: Reports and Analytics
uuid: 9042 a 274-7124-4323-8 cd 6-5 c 84 ab 3 eef 6 d
translation-type: tm+mt
source-git-commit: 6bae6861586fc2aba33888cadfec3b1399898b90

---


# Référence des colonnes de données

Utilisez cette page pour connaître les données contenues dans chaque colonne. La plupart des implémentations n'utilisent pas toutes les colonnes. Par conséquent, cette page peut être référencée lors de la détermination des colonnes à inclure dans une exportation de flux de données.

> [!IMPORTANT] Pour une colonne donnée (par exemple, une valeur définie comme 255 caractères), un flux de données peut envoyer des caractères supplémentaires en raison de l'ajout de caractères d'échappement des valeurs dans une chaîne. Gardez à l'esprit cette rubrique si votre implémentation envoie régulièrement des valeurs qui dépassent les limites de caractères.

## Colonnes, descriptions et types de données

> [!NOTE] La plupart des colonnes contiennent une colonne similaire avec un préfixe de `post_`. Les colonnes « Post » contiennent les valeurs suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas.

| Nom de la colonne | Description de la colonne | Type de données |
| --- | --- | --- |
| accept_language | Liste toutes les langues acceptées, comme indiqué dans l’en-tête HTTP Accept-Language lors d’une demande d’image. | char(20) |
| aemassetid | Variable à plusieurs valeurs correspondant aux ID de ressource (identificateurs globaux uniques) d’un ensemble de ressources d’Adobe Experience Manager. Incrémente l’événement Impression. | text |
| aemassetsource | Identifie la source de l’événement de ressources. Utilisée dans Adobe Experience Manager. | varchar(255) |
| aemclickedassetid | ID de ressource d’une ressource Adobe Experience Manager. Incrémente l’événement Click. | varchar(255) |
| browser | Identifiant numérique du navigateur. Fait référence à la table de recherche de browser.tsv. | int unsigned |
| browser_height | Hauteur en pixels de la fenêtre du navigateur. | smallint unsigned |
| browser_width | Largeur en pixels de la fenêtre du navigateur. | smallint unsigned |
| c_color | Codage en bits de la palette de couleurs. Utilisée dans le cadre du calcul de la dimension Intensité de couleur. Utilise la fonction JavaScript screen.colorDepth(). | char(20) |
| Campaign | Variable utilisée dans la dimension Code de suivi. | varchar(255) |
| carrier | Variable d’intégration Adobe Advertising Cloud. Définit l’opérateur de téléphonie mobile. Fait référence à la table de recherche des opérateurs. | varchar(100) |
| channel | Variable utilisée dans la dimension Sections du site. | varchar(100) |
| click_action | N’est plus utilisée. Adresse du lien cliqué dans l’outil hérité Clickmap. | varchar(100) |
| click_action_type | N’est plus utilisée. Type de lien de l’outil hérité Clickmap.<br>0 : URL HREF<br>1 : ID personnalisé<br>2 : JavaScript onclick event<br>3 : Elément Form | tinyint sans signe |
| click_context | N’est plus utilisée. Nom de la page où un clic a été fait sur les liens. Partie de l’outil hérité Clickmap. | varchar(255) |
| click_context_type | N’est plus utilisée. Indique si click_context avait un nom de page ou une URL de page par défaut.<br>0 : URL de la page<br>1 : Nom de page | tinyint sans signe |
| click_sourceid | N’est plus utilisée. Identifiant numérique pour l’emplacement sur la page du lien cliqué. Partie de l’outil hérité Clickmap. | int unsigned |
| click_tag | N’est plus utilisée. Type d’élément HTML sur lequel on a cliqué. | char(10) |
| clickmaplink | Page link | varchar(255) |
| clickmaplinkbyregion | Lien Carte d'activités par région | varchar(255) |
| clickmappage | Page Carte d'activités | varchar(255) |
| clickmapregion | Région de Carte d'activités | varchar(255) |
| code_ver | Version de la bibliothèque AppMeasurement utilisée pour compiler et envoyer la demande d’image. | char(16) |
| color | Identifiant de l’intensité des couleurs basé sur la valeur de la colonne c_color. Fait référence à la table de recherche de color_depth.tsv. | smallint unsigned |
| connection_type | Identifiant numérique représentant le type de connexion. Variable utilisée dans la dimension Type de connexion. Fait référence à la table de recherche de connection_type.tsv. | tinyint sans signe |
| cookies | Variable utilisée dans la dimension Prise en charge des cookies.<br>Y : Enabledn<br>: Disabledu<br>: Inconnu | char(1) |
| country | Identifiant numérique représentant le pays d’où provient l’accès. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. Utilise la recherche de country.tsv. | smallint unsigned |
| ct_connect_type | Liée à la colonne connection_type. Les valeurs les plus courantes sont LAN/Wi-Fi, Opérateur de téléphonie mobile et Modem. | char(20) |
| curr_factor | Détermine la décimale de la devise et est utilisée pour la conversion de devise. Par exemple, le dollar américain (USD) utilise deux décimales, donc cette valeur de colonne serait de 2. | tinyint |
| curr_rate | Taux de change au moment de la transaction. Adobe travaille en partenariat avec XE pour déterminer le taux de change du jour. | decimal(24,12) |
| currency | Le code de devise qui a été utilisé pendant la transaction. | char(8) |
| cust_hit_time_gmt | Suites de rapports avec horodatage uniquement. Horodatage envoyé avec l’accès, basé sur l’heure Unix. | int |
| cust_visid | Si un identifiant visiteur personnalisé est défini, il est indiqué dans cette colonne. | varchar(255) |
| daily_visitor | Indicateur qui détermine si l’accès est un nouveau visiteur quotidien. | tinyint sans signe |
| date_time | Heure de l’accès dans un format lisible, basée sur le fuseau horaire de la suite de rapports. | Heure du jour |
| domain | Variable utilisée dans la dimension Domaine. Basée sur le fournisseur d’accès Internet (FAI) de l’utilisateur. | varchar(100) |
| duplicate_events | Répertorie chaque événement compté comme double. | varchar(255) |
| duplicate_purchase | Indicateur signifiant que l’événement d’achat pour cet accès doit être ignoré, car il s’agit d’un double. | tinyint sans signe |
| duplicated_from | Utilisée uniquement dans les suites de rapports contenant les règles VISTA de la copie de l’accès. Indique la suite de rapports à partir de laquelle l’accès a été copié. | varchar(40) |
| ef_id | ef_id utilisée dans les intégrations Adobe Advertising Cloud. | varchar(255) |
| evar1-evar250 | Variables personnalisées 1-250. Chaque organisation utilise les eVars différemment. Le meilleur outil pour obtenir plus d’informations sur la façon dont votre organisation renseigne les eVars respectifs serait un document de conception de solution spécifique à votre organisation. | varchar(255) |
| event_list | Liste séparée par des virgules d’identifiants numériques représentant les événements déclenchés lors de l’accès. Comprend à la fois les événements par défaut et les événements personnalisés 1-1000. Utilise la recherche d’event.tsv. | text |
| exclude_hit | Indicateur signifiant que l’accès est exclu de la création de rapports. La colonne visit_ num n'est pas incrémentée pour les accès exclus.<br>1 : Inutilisée. Partie d'une fonction désélectionnée.<br>2 : Inutilisée. Partie d'une fonction désélectionnée.<br>3 : Plus utilisé. Exclusion de l'agent utilisateur<br>4 : Exclusion basée sur l'adresse IP<br>5 : Informations d'accès vitales manquantes, telles que page_ url, pagename, page_ event ou event_ list<br>6 : JavaScript n'a pas correctement traité l'accès<br>7 : Exclusion spécifique au compte, par exemple dans les règles VISTA<br>8 : Non utilisé. Autre exclusion spécifique au compte.<br>9 : Inutilisée. Partie d'une fonction désélectionnée.<br>10 : Code de devise non valide<br>11 : L'accès a manqué un horodatage sur une suite de rapports horodatée uniquement, ou un accès contenait un horodatage sur une suite de rapports non horodatée<br>12 : Non utilisé. Partie d'une fonction désélectionnée.<br>13 : Inutilisée. Partie d'une fonction désélectionnée.<br>14 : Accès Target qui ne correspondait pas à un accès Analytics<br>15 : Actuellement utilisé.<br>16 : Correspondance de publicité qui ne correspondait pas à un accès Analytics | tinyint sans signe |
| first_hit_page_url | La toute première URL du visiteur. | varchar(255) |
| first_hit_pagename | Variable utilisée dans la dimension Page d’accès d’origine. Le nom de la page d’entrée d’origine du visiteur. | varchar(100) |
| first_hit_ref_domain | Variable utilisée dans la dimension Domaine référent initial. Basée sur first_hit_referrer. Le tout premier domaine référent du visiteur. | varchar(100) |
| first_hit_ref_type | Identifiant numérique représentant le type de référent du tout premier référent du visiteur. Utilise la recherche de referrer_type.tsv. | tinyint sans signe |
| first_hit_referrer | La toute première URL de référence du visiteur. | varchar(255) |
| first_hit_time_gmt | Horodatage du tout premier accès du visiteur en heure Unix. | int |
| geo_city | Nom de la ville d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et la ville. | char(32) |
| geo_country | Abréviation du pays d’origine de l’accès, basée sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le pays. | char(4) |
| geo_dma | Identifiant numérique de la zone démographique d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et la zone démographique. | int unsigned |
| geo_region | Nom de l’état ou de la région d’où provient l’accès, basé sur l’IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et l’état/la région. | char(32) |
| geo_zip | Le code postal de l'accès est issu de l'adresse IP. Adobe travaille en partenariat avec Digital Envoy pour établir une correspondance entre l’adresse IP et le code postal. | varchar(16) |
| hier1 - hier5 | Utilisée par les variables hiérarchiques. Contient une liste délimitée de valeurs. Le délimiteur est sélectionné dans les paramètres de la suite de rapports. | varchar(255) |
| hit_source | Indique la source de l’accès. <br>1 : Demande d'image standard sans horodatage <br>2 : Demande d'image standard avec horodatage <br>3 : Transfert de source de données en direct avec horodatage <br>4 : Non utilisé <br>5 : Transfert générique de source de données <br>6 : Transfert complet de la source de données de traitement <br>7 : Transfert de source de données transactionid <br>8 : Plus utilisé ; Versions précédentes d'Adobe Publish Sources de données Cloud <br>9 : Plus utilisé ; Mesures récapitulatives Adobe Social | tinyint sans signe |
| hit_time_gmt | L'horodatage des serveurs de collecte de données Adobe a reçu l'accès, selon l'heure Unix. | int |
| hitid_high | Utilisée en combinaison avec hitid_low pour identifier de manière unique un accès. | bigint unsigned |
| hitid_low | Utilisée en combinaison avec hitid_high pour identifier de manière unique un accès. | bigint unsigned |
| homepage | N’est plus utilisée. Indique si l’URL active est la page d’accueil du navigateur. | char(1) |
| hourly_visitor | Indicateur qui détermine si l’accès est un nouveau visiteur horaire. | tinyint sans signe |
| ip | Adresse IP, basée sur l’en-tête HTTP de la demande d’image. | char(20) |
| ip2 | Inutilisée. Variable de référence du serveur principal pour les suites de rapports contenant des règles VISTA basées sur l’adresse IP. | char(20) |
| j_jscript | Version de JavaScript prise en charge par le navigateur. | char(5) |
| java_enabled | Indicateur précisant si Java est activé. <br>Y : Activé <br>N : Désactivé <br>U : Inconnu | char(1) |
| javascript | Identifiant de recherche de la version JavaScript, basé sur j_jscript. Utilise une table de recherche. | tinyint sans signe |
| language | Identifiant numérique de la langue. Utilise la table de recherche de languages.tsv. | smallint unsigned |
| last_hit_time_gmt | Horodatage (en heure Unix) de l’accès précédent. Utilisé pour calculer la dimension Jours depuis la dernière visite. | int |
| last_purchase_num | Variable utilisée dans la dimension Fidélisation des clients. Indique le nombre d’achats précédents effectués par le visiteur. <br>0 : Aucun achat précédent (pas un client) <br>1 : 1 achat précédent (nouveau client) <br>2 : 2 achats précédents (client régulier) <br>3 : 3 achats précédents (client fidèle) | int unsigned |
| last_purchase_time_gmt | Utilisée dans la dimension Jours depuis le dernier achat. Horodatage (en heure Unix) du dernier achat effectué. Pour les premiers achats et les visiteurs qui n’avaient jamais effectué d’achat auparavant, cette valeur est de 0. | int |
| latlon1 | Lieu (jusqu’à 10 km) | varchar(255) |
| latlon23 | Lieu (jusqu’à 100 m) | varchar(255) |
| latlon45 | Lieu (jusqu’à 1 m) | varchar(255) |
| Des colonnes | Liste des identifiants de segment Audience Manager auxquels le visiteur appartient. | text |
| mcvisid | Identifiant visiteur Experience Cloud. Nombre 128 bits constitué de deux nombres 64 bits concaténés complétés par 19 chiffres. | varchar(255) |
| mobile_id | Si l'utilisateur utilise un périphérique mobile, l'ID numérique du périphérique. | int |
| mobileaction | Action mobile. Automatiquement collecté lorsque trackaction est appelé dans Mobile Services. Permet le cheminement d’action automatique dans l’application. | varchar(100) |
| mobileappid | ID de l’application mobile Stocke le nom et la version de l’application au format suivant :[Appname] [bundleversion] | varchar(255) |
| mobileappperformanceappid | Utilisé dans le connecteur de données Apteligent. ID d'application utilisé dans Apteligent. | varchar(255) |
| mobileappperformancecrashid | Utilisé dans le connecteur de données Apteligent. ID de plantage utilisé dans Apteligent. | varchar(255) |
| mobileappstoreobjectid | Utilisé dans le connecteur de données Appfigures. ID d'objet de boutique d'applications | varchar(255) |
| mobilebeaconmajor | Balise de balise Mobile Services | varchar(100) |
| mobilebeaconminor | Balise Mobile Services mineure | varchar(100) |
| mobilebeaconproximity | Proximité de la balise Mobile Services | varchar(255) |
| mobilebeaconuuid | UUID de balise Mobile Services | varchar(100) |
| mobilecampaigncontent | Le nom ou l’identifiant du contenu qui a affiché le lien. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| mobilecampaignmedium | Support marketing, une bannière ou un courrier électronique par exemple. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| mobilecampaignname | Nom de la campagne, également stocké dans la variable de campagne. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| mobilecampaignsource | Référent original, comme la newsletter ou les médias sociaux. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| mobilecampaignterm | Mots-clés ou autres termes payés dont vous souhaitez effectuer le suivi avec cette acquisition. Renseigné par l’acquisition des applications mobiles. | varchar(255) |
| mobiledayofweek | Numéro du jour de la semaine où l’application a été lancée. | varchar(255) |
| mobiledayssincefirstuse | Nombre de jours depuis que l’application a été lancée pour la première fois. | varchar(255) |
| mobiledayssincelastupgrade | Collecté à partir de la variable de données contextuelles a. dayssincelastupgrade. Nombre de jours écoulés depuis la session précédente. | varchar(255) |
| mobiledayssincelastuse | Nombre de jours depuis la dernière exécution de l’application. | varchar(255) |
| mobiledeeplinkid | Collecté à partir de la variable de données contextuelles a.<span>deeplink</span>. id. Utilisé dans les rapports d'acquisition comme identificateur pour le lien d'acquisition mobile. | varchar(255) |
| mobiledevice | Nom du périphérique mobile. Sous iOS, il est stocké sous la forme d’une chaîne de 2 chiffres séparés par des virgules. Le premier chiffre représente la génération de l’appareil, le second la famille d’appareils. | varchar(255) |
| mobilehourofday | Définit l’heure du jour où l’application a été lancée. Suit un format numérique de 24 heures. | varchar(255) |
| mobileinstalldate | Date de l’installation mobile. Indique la date de la première ouverture d’une application mobile par un utilisateur. | varchar(255) |
| mobilelaunchessincelastupgrade | Collecté à partir de la variable de données contextuelles a. launchessinceupgrade. Indique le nombre de lancements depuis la dernière mise à niveau. | varchar(255) |
| mobilelaunchnumber | Est incrémentée d’une unité chaque fois que l’application mobile est lancée. | varchar(255) |
| mobileltv | N’est plus utilisée. Renseignée par les méthodes trackLifetimeValue. | varchar(255) |
| mobilemessagebuttonname | Collecté à partir de la variable de données contextuelles a.<span>message</span>. button. id. Utilisé pour la messagerie in-app pour identifier le bouton qui a fermé le message. | varchar(100) |
| mobilemessageid | ID de message in-app | varchar(255) |
| mobilemessageonline | Message in-app en ligne | varchar(255) |
| mobilemessagepushoptin | Collecté à partir de la variable de données contextuelles a. push. optin. Définissez cette valeur sur true lorsque l'utilisateur choisit de transmettre la messagerie push ; sinon, la valeur est « false ». | varchar(255) |
| mobilemessagepushpayloadid | Collecté à partir de la variable de données contextuelles a. push. payloadid. Utilisé dans la messagerie Push comme identifiant de charge utile. | varchar(255) |
| mobileosenvironment | Collecté à partir de la variable de données contextuelles a. osenvironment. Environnement d'exploitation des états, tel qu'Android ou ios. | varchar(255) |
| mobileosversion | Version du système d'exploitation Mobile Services | varchar(255) |
| mobileplaceaccuracy | Collecté à partir de la variable de données contextuelles a. loc. acc. Indique la précision du GPS en mètres au moment de la collecte. | varchar(255) |
| mobileplacecategory | Collecté à partir de la variable de données contextuelles a. loc. category. Décrit la catégorie d'un endroit spécifique. | varchar(255) |
| mobileplaceid | Collecté à partir de la variable de données contextuelles a.<span>loc</span>. id. Identifiant d'un point ciblé donné. | varchar(255) |
| mobilerelaunchcampaigncontent | Mobile Services lance le contenu | varchar(255) |
| mobilerelaunchcampaignmedium | Mobile Services lancement medium | varchar(255) |
| mobilerelaunchcampaignsource | Source de lancement de Mobile Services | varchar(255) |
| mobilerelaunchcampaignterm | Terme de lancement des services mobiles | varchar(255) |
| mobilerelaunchcampaigntrackingcode | Collecté à partir de la variable de données contextuelles a. launch. campaign. trackingcode. Utilisé dans l'acquisition comme code de suivi pour la campagne de lancement. | varchar(255) |
| mobileresolution | Résolution de l’appareil mobile. Largeur x hauteur en pixels. | varchar(255) |
| monthly_visitor | Indicateur signifiant que le visiteur est unique pour le mois en cours. | tinyint sans signe |
| mvvar 1 - mvvar 3 | Valeurs des variables de liste. Contient une liste délimitée de valeurs personnalisées en fonction de l’implémentation. | texte |
| namespace | Inutilisée. Partie d’une fonctionnalité mise au rebut il y a de nombreuses années. | varchar(50) |
| new_visit | Indicateur qui détermine si l’accès actif est une nouvelle visite. Valeur définie par les serveurs d’Adobe après 30 minutes d’inactivité au niveau de la visite. | tinyint sans signe |
| os | Identifiant numérique représentant le système d’exploitation du visiteur. Basé sur la colonne user_agent. Utilise la table de recherche de l’os. | int unsigned |
| p_plugins | N’est plus utilisée. Liste de plugins disponibles pour le navigateur. Utilisation de la fonction JavaScript navigator.plugins(). | texte |
| page_event | Le type d’accès qui est envoyé dans la demande d’image (accès standard, lien de téléchargement, lien personnalisé, lien de sortie). | tinyint sans signe |
| page_event_var1 | Uniquement utilisée dans les demandes d’image de suivi des liens. URL du lien de téléchargement, de sortie ou personnalisé sur lequel a cliqué l’utilisateur. | text |
| page_event_var2 | Uniquement utilisée dans les demandes d’image de suivi des liens. Nom personnalisé (le cas échéant) du lien. | varchar(100) |
| page_event_var3 | N’est plus utilisée. Contient les données des modules Survey et Media. Rapports vidéo hérités générés dans les versions précédentes d’Adobe Analytics. | texte |
| page_type | Utilisée pour indiquer la dimension Pages introuvables, utilisée exclusivement pour les pages 404. Cette variable doit être vide ou contenir « ErrorPage ». | char(20) |
| page_url | URL de l’accès. N’est pas utilisée dans les demandes d’image du suivi des liens. | varchar(255) |
| pagename | Utilisée pour indiquer la dimension Pages. Si la variable pagename est vide, Analytics utilise la variable page_url en remplacement. | varchar(100) |
| paid_search | Indicateur qui est défini si l’accès correspond à la détection de recherche payante. | tinyint sans signe |
| partner_plugins | Inutilisée. Partie d’une fonctionnalité mise au rebut il y a de nombreuses années. | varchar(255) |
| persistent_cookie | Utilisée par la dimension Prise en charge des cookies persistants. Indique si le visiteur prend en charge les cookies qui ne sont pas ignorés après chaque accès. | char(1) |
| plugins | N’est plus utilisée. Liste des identifiants numériques qui correspondent aux plugins disponibles dans le navigateur. Utilise la recherche de plugins.tsv. | varchar(180) |
| pointofinterest | Nom d'intérêt de Mobile Services | varchar(255) |
| pointofinterestdistance | Distance des services mobiles jusqu'au centre ciblé | varchar(255) |
| post_ columns | Contient la valeur finalement utilisée dans les rapports. Chaque colonne « Post » est renseignée suivant la logique côté serveur, les règles de traitement et les règles VISTA. Adobe recommande d’utiliser des colonnes « Post » dans la plupart des cas. | Voir la colonne « Non post » correspondante. |
| prev_page | Inutilisée. Identifiant propriétaire Adobe de la page précédente. | int unsigned |
| product_list | Liste des produits telle que transmise par l’intermédiaire de la variable « products ». Les produits sont délimités par des virgules, tandis que les propriétés des produits individuels sont délimitées par des points-virgules. | text |
| product_merchandising | Inutilisée. Utilisez product_list à la place. | text |
| prop1 - prop75 | Variables de trafic personnalisées 1 - 75. | varchar(100) |
| purchaseid | Identificateur unique pour un achat, tel qu’il est défini à l’aide de la variable s_purchaseID. Utilisé par la colonne duplicate_purchase. | char(20) |
| quarterly_visitor | Indicateur qui détermine si l’accès est un nouveau visiteur trimestriel. | tinyint sans signe |
| ref_domain | Basée sur la colonne Référent. Domaine référent de l’accès. | varchar(100) |
| ref_type | Identifiant numérique représentant le type de référence pour l’accès.<br>1 : Dans votre site<br>2 : Autres sites Web <br>3 : Moteurs de recherche <br>4 : Disque dur <br>5 : USENET <br>6 : Tapé/marqué (aucun référent) <br>7 : Email <br>8 : Pas de code JavaScript <br>9 : Réseaux sociaux | tinyint sans signe |
| referrer | URL de la page précédente. | varchar(255) |
| resolution | Identifiant numérique représentant la résolution de l’écran. Indique la dimension Résolution de l’écran. Utilise la table de recherche de resolution.tsv. | smallint unsigned |
| s_kwcid | ID de mot-clé utilisé dans les intégrations d'Adobe Advertizing Cloud. | varchar(255) |
| s_resolution | Valeur brute de la résolution de l’écran. Collectée à l’aide de la fonction JavaScript screen.width x screen.height. | char(20) |
| sampled_hit | N’est plus utilisée. Anciennement utilisée pour l’échantillonnage dans Ad Hoc Analysis. | char(1) |
| search_engine | Identifiant numérique représentant le moteur de recherche qui a référé le visiteur à votre site. Utilise la table de recherche de search_engines.tsv. | smallint unsigned |
| search_page_num | Utilisée par la dimension Classement de toutes les pages de recherche. Indique sur quelle page de résultats de recherche votre site est apparu avant que l’utilisateur ne clique sur votre site. | smallint unsigned |
| secondary_hit | Indicateur qui suit les accès secondaires. Normalement, il provient du balisage multisuite et des règles VISTA qui copient les accès. | tinyint sans signe |
| service | Inutilisée Utilisez page_event à la place. | char(2) |
| socialaccountandappids | N’est plus utilisée. Identifiants de comptes sociaux et d’application | varchar(255) |
| socialassettrackingcode | N’est plus utilisée. Variable de campagne sociale | varchar(255) |
| socialauthor | N’est plus utilisée. Variable des auteurs du module Social | varchar(255) |
| socialcontentprovider | N’est plus utilisée. Plateformes sociales / Propriétés | varchar(255) |
| socialinteractiontype | N’est plus utilisée. Type d’interaction sociale | varchar(255) |
| sociallanguage | N’est plus utilisée. Langage social | varchar(255) |
| sociallatlong | N’est plus utilisée. Latitude / Longitude sociale | varchar(255) |
| socialowneddefinitioninsighttype | N’est plus utilisée. Type d’informations sur la définition détenue sur réseau social | varchar(255) |
| socialowneddefinitioninsightvalue | N’est plus utilisée. Valeur d’informations sur la définition détenue sur réseau social | varchar(255) |
| socialowneddefinitionmetric | N’est plus utilisée. Mesure de définition détenue sur réseau social | varchar(255) |
| socialowneddefinitionpropertyvspost | N’est plus utilisée. Propriété de définition détenue sur réseau social/publication | varchar(255) |
| socialownedpostids | N’est plus utilisée. Identifiants de publications détenues sur réseau social | varchar(255) |
| socialownedpropertyid | N’est plus utilisée. Identifiant de propriété détenue sur réseau social | varchar(255) |
| socialownedpropertyname | N’est plus utilisée. Nom de propriété détenue sur réseau social | varchar(255) |
| socialownedpropertypropertyvsapp | N’est plus utilisée. Propriété détenue sur réseau social/application | varchar(255) |
| état | Variable d’état. | varchar(50) |
| stats_server | Inutilisable. Serveur interne d’Adobe qui a traité l’accès. | char(30) |
| t_time_info | Heure locale pour le visiteur. Le format est le suivant : M/J/AAAA HH : MM : Décalage du fuseau horaire SS (0-11, 0 = janvier) Décalage fuseau horaire (en minutes) | varchar(100) |
| tnt | Utilisée dans les intégrations Adobe Target. | texte |
| tnt_action | Utilisée dans les intégrations Adobe Target. | texte |
| tnt_post_vista | N’est plus utilisée. Utilisez post_tnt à la place. | texte |
| transactionid | Identifiant unique vers lequel plusieurs points de données pourront être transférés plus tard au moyen de sources de données. | text |
| truncated_hit | Indicateur signifiant que la demande d’image a été tronquée. Indique qu’un accès partiel a été reçu. <br>Y : Accès tronqué ; accès partiel reçu <br>N : Accès n'était pas tronqué ; accès complet reçu | char(1) |
| ua_color | N’est plus utilisée. Anciennement utilisée comme solution de secours pour l’intensité de couleur. | char(20) |
| ua_os | N’est plus utilisée. Anciennement utilisée comme solution de secours pour le système d’exploitation. | char(80) |
| ua_pixels | N’est plus utilisée. Anciennement utilisée comme solution de secours pour la hauteur et la largeur du navigateur. | char(20) |
| user_agent | Chaîne de l’agent utilisateur envoyée dans l’en-tête HTTP de la demande d’image. | texte |
| user_hash | Inutilisable. Hachage de l’identifiant de suite de rapports. Utilisez le nom d’utilisateur à la place. | int unsigned |
| user_server | Variable utilisée dans la dimension Serveur. | varchar(100) |
| userid | Inutilisable. Identifiant numérique pour l’identifiant de suite de rapports. Utilisez le nom d’utilisateur à la place. | int unsigned |
| username | Identifiant de la suite de rapports pour l’accès. | char(40) |
| va_closer_detail | Variable utilisée dans la dimension Détails de Dernière touche. | varchar(255) |
| va_closer_id | Identifiant numérique qui identifie la dimension Canal Dernière touche. La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| va_finder_detail | Variable utilisée dans la dimension Détails de Première touche. | varchar(255) |
| va_finder_id | Identifiant numérique qui identifie la dimension Canal Première touche. La recherche de cet identifiant se trouve dans le gestionnaire des canaux marketing. | tinyint sans signe |
| va_instance_event | Indicateur pour identifier les instances de canal marketing. Utilisé par la mesure Instances Dernière touche des canaux marketing. | tinyint sans signe |
| va_new_engagement | Indicateur pour identifier les nouveaux engagements de canal marketing. Utilisé par la mesure Nouveaux engagements. | tinyint sans signe |
| video | Contenu vidéo | varchar(255) |
| videoad | Nom de publicité vidéo | varchar(255) |
| videoadinpod | Publicité vidéo dans la position de la capsule | varchar(255) |
| videoadlength | Longueur de publicité vidéo | varchar(255) |
| videoadload | Chargement de publicités vidéo | varchar(255) |
| videoadname | Nom de publicité vidéo | varchar(255) |
| videoadplayername | Nom du lecteur de publicités vidéo | varchar(255) |
| videoadpod | Capsule vidéo | varchar(255) |
| videoadvertiser | Annonceur vidéo | varchar(255) |
| videoaudioalbum | Album audio vidéo | varchar(255) |
| videoaudioartist | Artiste audio vidéo | varchar(255) |
| videoaudioauthor | Auteur audio vidéo | varchar(255) |
| videoaudiolabel | Libellé audio vidéo | varchar(255) |
| videoaudiopublisher | Editeur audio vidéo | varchar(255) |
| videoaudiostation | Station audio vidéo | varchar(255) |
| videocampaign | Campagne vidéo | varchar(255) |
| videochannel | Canal vidéo | varchar(255) |
| videochapter | Nom du chapitre vidéo | varchar(255) |
| videocontenttype | Type de contenu vidéo. Défini automatiquement sur « Vidéo » pour toutes les consultations vidéo | varchar(255) |
| videodaypart | Partie de la vidéo | varchar(255) |
| videoepisode | Épisode vidéo | varchar(255) |
| videofeedtype | Type de flux vidéo | varchar(255) |
| videogenre | Genre vidéo | text |
| videolength | Durée de la vidéo. | varchar(255) |
| videomvpd | MVPD vidéo | varchar(255) |
| videoname | Nom de la vidéo | varchar(255) |
| videonetwork | Réseau vidéo | varchar(255) |
| videopath | Chemin de la vidéo | varchar(100) |
| videoplayername | Nom du lecteur vidéo | varchar(255) |
| videoqoebitrateaverageevar | Débit en bits moyen de la qualité vidéo | varchar(255) |
| videoqoebitratechangecountevar | Nombre de changements au niveau de la qualité vidéo | varchar(255) |
| videoqoebuffercountevar | Nombre de tampons pour la qualité vidéo | varchar(255) |
| videoqoebuffertimeevar | Temps de mise en mémoire tampon de la qualité vidéo | varchar(255) |
| videoqoedroppedframecountevar | Nombre d’images perdues au niveau de la qualité vidéo | varchar(255) |
| videoqoeerrorcountevar | Comptage des erreurs de la qualité vidéo | varchar(255) |
| videoqoeexternalerrors | Erreurs externes de qualité vidéo | text |
| videoqoeplayersdkerrors | Erreurs de SDK qualité vidéo | text |
| videoqoetimetostartevar | Temps de démarrage de la qualité vidéo | varchar(255) |
| videoseason | Saison vidéo | varchar(255) |
| videosegment | Segment de vidéo | varchar(255) |
| videoshow | Vidéo affichée | varchar(255) |
| videoshowtype | Type d'affichage vidéo | varchar(255) |
| videostreamtype | Type de flux vidéo | varchar(255) |
| visid_high | Utilisée en combinaison avec visid_low pour identifier de manière unique une visite. | bigint unsigned |
| visid_low | Utilisée en combinaison avec visid_high pour identifier de manière unique une visite. | bigint unsigned |
| visid_new | Indicateur pour identifier si l’accès contient un identifiant visiteur nouvellement généré. | char(1) |
| visid_timestamp | Si l’identifiant visiteur a été récemment généré, cette variable fournit l’horodatage (en heure Unix) du moment où l’identifiant visiteur a été généré. | int |
| visid_type | Identifiant numérique représentant la méthode utilisée pour identifier le visiteur. <br>0 : Visitorid <br>1 personnalisé : Secours de l'agent utilisateur et IP <br>2 : En-tête d'abonné mobile HTTP <br>3 : Valeur du cookie hérité (s_ vi) <br>4 : Valeur du cookie de secours (s_ fid) <br>5 : Service d'identité | tinyint sans signe |
| visit_keywords | Variable utilisée dans la dimension Mot-clé de recherche. Cette colonne utilise une limite de caractères non standard pour accommoder la logique d'arrière-plan utilisée par Adobe. | varchar(244) |
| visit_num | Variable utilisée dans la dimension Nombre de visites. Commence à 1, et est incrémentée chaque fois qu’une nouvelle visite commence par visiteur. | int unsigned |
| visit_page_num | Variable utilisée dans la dimension Détail des accès. Augmente de 1 pour chaque accès que l’utilisateur génère. Réinitialise chaque visite. | int unsigned |
| visit_ref_domain | Basée sur la colonne visit_referrer. Le premier domaine référent de la visite. | varchar(100) |
| visit_ref_type | Identifiant numérique représentant le type de référent du premier référent de la visite. Utilise la table de recherche de referrer_type.tsv. | tinyint sans signe |
| visit_referrer | Le premier référent de la visite. | varchar(255) |
| visit_search_engine | Identifiant numérique du premier moteur de recherche de la visite. Utilise la table de recherche de search_engines.tsv. | smallint unsigned |
| visit_start_page_url | La première URL de la visite. | varchar(255) |
| visit_start_pagename | Le premier Nom de page de la visite. | varchar(100) |
| visit_start_time_gmt | Horodatage (en heure Unix) du premier accès de la visite. | int |
| weekly_visitor | Indicateur qui détermine si l’accès est un nouveau visiteur hebdomadaire. | tinyint sans signe |
| yearly_visitor | Indicateur qui détermine si l’accès est un nouveau visiteur annuel. | tinyint sans signe |
| zip | Utilisée pour indiquer la dimension Code postal. | varchar(50) |

## Colonnes vides

La liste de colonnes suivante est inutilisée et ne contient aucune donnée :

* mobileider itionclicks
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
* mobileappstoreinexyscenes
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
* mobileappstoreobjectid<span>.</span>révision-commentaire
* mobileappstoreobjectid<span>.</span>révision-titre
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdior
* mobileappstorerating
* mobileappstoreratingdior
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
* mobilemonthlyengagement
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (désapprouvée)
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
* videouniquetimeplayed
