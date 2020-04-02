---
title: Compatibilité des dimensions Analytics
description: Référence pour les dimensions et les rapports Analytics.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Compatibilité des dimensions Analytics

Cet article de référence répertorie les dimensions/rapports pris en charge à la fois dans Reports &amp; Analytics et dans Analysis Workspace, dans Analysis Workspace uniquement et dans Reports &amp; Analytics uniquement.

Gardez à l’esprit les éléments suivants.

* Ces listes ne sont pas exhaustives. Chaque suite de rapports peut ou non avoir un ensemble donné de variables de produit activées. En outre, toute suite de rapports donnée peut comporter un nombre quelconque de variables personnalisées activées ou désactivées ou mappées à des variables de produit. Nous avons également omis les attributs et classifications des visiteurs, car ils sont uniques pour chaque suite de rapports.

* Il existe quelques cas de chevauchement pour lesquels les outils d’Analytics utilisent des termes différents pour ce qui est essentiellement la même chose, par exemple : « `browserwidth` » et « `browserwidthbucketed` ».

## Dimensions prises en charge à la fois dans Reports &amp; Analytics et Analysis Workspace

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|---|---|
| Analytics pour Target | targetraw |
| ID Audiences | mcaudiences |
| Navigateur | browser |
| Type de navigateur | browsertype |
| Catégorie | category |
| Villes | geocity |
| Profondeur de couleur | colordepth |
| Type de connexion | connectiontype |
| Prise en charge des cookies | cookie |
| Pays | geocountry |
| Fidélité de la clientèle | customerloyalty |
| Variables de conversion personnalisées | evar1, evar2, etc. |
| Variables Aperçu personnalisé | prop1, prop2, etc. |
| Lien personnalisé | customlink |
| Jours avant le premier achat | daysbeforefirstpurchase |
| Jours depuis le dernier achat | dayssincelastpurchase |
| Domaine | filtereddomain |
| Lien de téléchargement | downloadlink |
| Page d’accès | entrypage |
| Page d’accès d’origine | entrypageoriginal |
| Lien de sortie | exitlink |
| Canal Première touche | firsttouchchannel |
| Détails du canal Première touche | firsttouchchanneldetail |
| Compatible Java | javaenabled |
| Langue | language |
| Canal Dernière touche | lasttouchchannel |
| Détails du canal Dernière touche | lasttouchchanneldetail |
| Variables de liste | listvariables |
| Canal marketing | marketingchannel |
| Prise en charge de l’audio sur le dispositif portable | mobileaudiosupport |
| Opérateur de téléphonie mobile | mobilecarrier |
| Profondeur de couleur du dispositif portable | mobilecolordepth |
| Prise en charge des cookies sur le dispositif portable | mobilecookiesupport |
| Appareil mobile | mobiledevicename |
| Type de périphérique mobile | mobiledevicetype |
| Mobile - Longueur max. d’adresse électronique | mobileemaillength |
| Prise en charge des images sur le dispositif portable | mobileimagesupport |
| Fabricant du dispositif portable | mobilemanufacturer |
| Système d’exploitation mobile (obsolète) | mobileos |
| Hauteur d’écran du dispositif portable | mobilescreenheight |
| Taille d’écran du dispositif portable | mobilescreensize |
| Largeur d’écran du dispositif portable | mobilescreenwidth |
| Mobile - Longueur max. d’URL de navigateur | mobileurllength |
| Prise en charge de la vidéo sur le dispositif portable | mobilevideosupport |
| Résolution de l’écran | monitorresolution |
| Systèmes d’exploitation | operatingsystem |
| Domaine référent initial | referringdomainoriginal |
| Page | page |
| Pages introuvables | pagesnotfound |
| Produit | product |
| Référent | referrer |
| Type de référent | referrertype |
| Domaine référent | referringdomain |
| Régions | georegion |
| Fréquence des retours | returnfrequency |
| SC-TnT | tntbase |
| Moteur de recherche | searchengine |
| Mot-clé de recherche | searchenginekeyword |
| Moteur de recherche - Naturel | searchenginenatural |
| Moteur de recherche - Payant | searchenginepaid |
| Mot-clé de recherche - Naturel | searchenginenaturalkeyword |
| Mot-clé de recherche - Payant | searchenginepaidkeyword |
| Classement de toutes les pages de recherche | searchenginepagerank |
| Serveur | server |
| Visites sur une seule page | singlepagevisits |
| Section du site | sitesections |
| Temps passé par visite - Valeur granulaire | sitetime |
| Code de suivi | campaign |
| DMA États-Unis | geodma |
| États américains | state |
| Durée avant événement | timeprior |
| Durée par visite – Regroupement | timespent |
| Profondeur de visite | pathlength |
| Nombre de visites | visitnumber |
| Code postal | zip |

## Dimensions prises en charge uniquement dans Analysis Workspace

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Matin/après-midi | timepartampm |
| Hauteur du navigateur - Regroupement | browserheightbucketed |
| Largeur du navigateur - Regroupement | browserwidthbucketed |
| Jour | daterangeday |
| Jour du mois | timepartdayofmonth |
| Jour de la semaine | dayofweek |
| Jour de la semaine | timepartdayofweek |
| Jour de l’année | timepartdayofyear |
| Jours depuis la dernière visite | dayssincelastvisit |
| Accès Aperçu personnalisé | entryprops |
| Accès aux variables de liste | entrylistvariables |
| Serveur d’accès | entryserver |
| Accès à la section de site | entrysitesections |
| Quitter Aperçu personnalisé | exitprops |
| Quitter les variables de liste | exitlistvariables |
| Quitter la page | exitpage |
| Quitter le serveur | exitserver |
| Quitter la section de site | exitsitesections |
| Détail des accès | hitdepth |
| Type d’accès | hittype |
| Heure | daterangehour |
| Heure du jour | timeparthourofday |
| Détail des canaux marketing | marketingchanneldetail |
| Minute | daterangeminute |
| Mobile - Longueur max. du signet | mobilebookmarklength |
| Numéro de l’appareil mobile | mobiledevicenumber |
| DRM mobile | mobiledrm |
| Services d’informations mobiles | mobileinformationservices |
| Java VM de mobile | mobilejavavm |
| Mobile - Décoration de courrier | mobilemaildecoration |
| Protocoles Net mobile | mobilenetprotocols |
| Mobile - Presser pour parler | mobilepushtotalk |
| Mois | daterangemonth |
| Mois de l’année | timepartmonthofyear |
| Types de systèmes d’exploitation | operatingsystemgroup |
| Recherche payante | paidsearch |
| Prise en charge des cookies persistants | persistentcookie |
| Trimestre | daterangequarter |
| Trimestre de l’année | timepartquarterofyear |
| Enquête | surveybase |
| Durée de consultation de la page – Regroupement | averagepagetime |
| Durée de consultation de la page - Granulaire | pagetimeseconds |
| Suivi du motif d’exclusion | optoutreason |
| Jour ouvrable/week-end | timepartweekdayweekend |
| Semaine | daterangeweek |
| Année | daterangeyear |

## Dimensions adaptées au contenu prises en charge uniquement dans Analysis Workspace

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Activity Map XY | clickmapxy |
| ID de session multimédia | videosessionid |
| Méthode d’accès Nielsen | nielsenaccmethod |
| ID de l’application Nielsen | nielsenappid |
| Ressource de canal Nielsen | nielsenchannelasset |
| Type de contenu Nielsen | nielsencontenttype |

## Dimensions prises en charge uniquement dans Reports &amp; Analytics

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Hauteur du navigateur | browserheight |
| Largeur du navigateur | browserwidth |
| Clients quotidiens uniques | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| Version JavaScript | javascriptversion |
| Clients mensuels uniques | monthlyuniquecustomers |
| Clients trimestriels uniques | quarterlyuniquecustomers |
| Fuseaux horaires | timezone |
| Domaines de haut niveau | topleveldomain |
| État du visiteur | legacystate |
| Clients hebdomadaires uniques | weeklyuniquecustomers |
| Clients annuels uniques | yearlyuniquecustomers |

## Rapports préconfigurés dans Reports &amp; Analytics

Reports &amp; Analytics contient plusieurs rapports préconfigurés qui ne correspondent pas à une dimension spécifique ou qui utilisent une classe de dimensions. Ces rapports sont répertoriés ci-dessous :

* Longueur de l’URL enregistrée comme signet
* Navigateurs
* Types de navigateur
* Entonnoir de conversion de campagne
* Entonnoir de conversion de panier d’achats
* Villes
* Clics jusqu’à la page
* Pays
* Vente croisée
* Entonnoir d’événements personnalisés
* Prise en charge de Decoration Mail
* Envoi du numéro de dispositif (ACTIVÉ/DÉSACTIVÉ)
* Domaines
* DRM
* Pages d’entrée
* Pages de sortie
* Abandon
* Chemins complets
* ICities
* Services d’informations
* Version Java
* Langues
* Chemins les plus longs
* Visionneuses simultanées de médias
* Tranche horaire du média
* Détails du média
* Présentation du média
* Résolutions d’écran
* Protocoles réseau
* Modules Netscape
* Page suivante
* Flux page suivante
* Systèmes d’exploitation
* Types de systèmes d’exploitation
* Profondeur de page
* Résumé de la page
* Pathfinder
* Flux Page précédente
* Page précédente
* PTT
* Entonnoir de conversion de produits
* Entonnoir de conversion d’achat
* Domaines référents
* Régions
* Actualisations
* Moteurs de recherche – Tous
* Moteurs de recherche – Naturelle
* Moteurs de recherche – Payée
* Mots-clés de recherche – Tous
* Mots-clés de recherche – Naturelle
* Mots-clés de recherche – Payée
* Détails de l’activité cible
* Durée de consultation de la page
* Fuseaux horaires
* Domaines de haut niveau
* DMA États-Unis
* États (É.-U.)
* Nombre de visites
* Page d’accueil du visiteur

## Dimensions adaptées au contenu prises en charge à la fois par Reports &amp; Analytics et par Analysis Workspace

### Vidéo (Media Analytics)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Contenu | video |
| Segment de contenu | videosegment |
| Type de contenu | videocontenttype |
| Nom du lecteur de publicités | videoadplayername |
| Position de la publicité dans la capsule | videoadinpod |
| Perte d’images | videoqoedroppedframecountevar |
| Erreurs | videoqoeerrorcountevar |
| Débit moyen | videoqoebitrateaverageevar |
| Changements de débit | videoqoebitratechangecountevar |
| Durée totale de la mémoire tampon | videoqoebuffertimeevar |
| Événements de mémoire tampon | videoqoebuffercountevar |
| Temps jusqu’au début | videoqoetimetostartevar |
| Capsule publicitaire | videoadpod |
| Chemin du média | videopath |
| Publicité | videoad |
| Nom du lecteur de contenu | videoplayername |
| Canal de contenu | videochannel |
| Chapitre | videochapter |
| Nom du contenu (variable) | videoname |
| Durée du contenu (variable) | videolength |
| Nom de la publicité (variable) | videoadname |
| Durée de la publicité (variable) | videoadlength |
| Programme | videoshow |
| Saison | videoseason |
| Épisode | videoepisode |
| Réseau | videonetwork |
| Type de programme | videoshowtype |
| Chargements de publicités | videoadload |
| MVPD | videomvpd |
| Partie de la journée | videodaypart |
| Annonceur | videoadadvertiser |
| ID de campagne | videoadcampaign |
| Genre | videogenre |
| Type de diffusion | videostreamtype |
| ID d’erreur du SDK du lecteur | videoqoeplayersdkerrors |
| ID d’erreur externes | videoqoeexternalerrors |
| Type de flux multimédia | videofeedtype |
| Accès au chemin du média | entryvideopath |
| Quitter le chemin du média | exitvideopath |
| Accès au genre | entryvideogenre |
| Quitter le genre | exitvideogenre |
| Accès à l’ID d’erreur du SDK du lecteur | entryvideoqoeplayersdkerrors |
| Quitter l’ID d’erreur du SDK du lecteur | exitvideoqoeplayersdkerrors |
| Accès aux ID d’erreur externes | entryvideoqoeexternalerrors |
| Quitter les ID d’erreur externes | exitvideoqoeexternalerrors |

### Adobe Social

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Termes | socialterm |
| Plateformes sociales / Propriétés | socialcontentprovider |
| Auteurs | socialauthor |
| Langue | sociallanguage |
| Latitude / Longitude | sociallatlong |
| Codes de suivi des ressources | socialassettrackingcode |
| Propriétés sociales détenues | socialaccountandappids |
| ID de publication détenue | socialownedpostids |
| Définitions sociales détenues | socialinteractiontype |
| ID de propriété détenue | socialownedpropertyid |
| Propriété détenue et application | socialownedpropertypropertyvsapp |
| Nom de propriété détenue | socialownedpropertyname |
| Propriété de définition détenue et publication | socialowneddefinitionpropertyvspost |
| Type d’informations sur la définition détenue | socialowneddefinitioninsighttype |
| Valeur d’informations sur la définition détenue | socialowneddefinitioninsightvalue |
| Mesure de définition détenue | socialowneddefinitionmetric |
| Ressource | socialmediaid |

### SDK Mobile

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Date du premier lancement | mobileinstalldate |
| ID application | mobileappid |
| Numéro de lancement | mobilelaunchnumber |
| Jours depuis la première utilisation | mobiledayssincefirstuse |
| Jours depuis la dernière utilisation | mobiledayssincelastuse |
| Heure du jour (SDK) | mobilehourofday |
| Jour de la semaine (SDK) | mobiledayofweek |
| Système d’exploitation (SDK) | mobileosenvironment |
| Jours depuis la dernière mise à niveau | mobiledayssincelastupgrade |
| Lancements depuis la dernière mise à niveau | mobilelaunchessincelastupgrade |
| Nom du périphérique (SDK) | mobiledevice |
| Version du système d’exploitation (SDK) | mobileosversion |
| Balise majeure | mobilebeaconmajor |
| Balise mineure | mobilebeaconminor |
| UUID de la balise | mobilebeaconuuid |
| Proximité de la balise | mobilebeaconproximity |
| Lieu (jusqu’à 10 km) | latlon1 |
| Lieu (jusqu’à 100 m) | latlon23 |
| Lieu (jusqu’à 1 m) | latlon45 |
| Nom du point ciblé | pointofinterest |
| Distance jusqu’au centre du point ciblé | pointofinterestdistance |
| Précision de la localisation | mobileplaceaccuracy |
| Catégorie d’emplacement | mobileplacecategory |
| ID de l’emplacement | mobileplaceid |
| Accès à la balise majeure | entrymobilebeaconmajor |
| Quitter la balise majeure | exitmobilebeaconmajor |
| Accès à la balise mineure | entrymobilebeaconminor |
| Quitter la balise mineure | exitmobilebeaconminor |
| Accès à la balise UUID | entrymobilebeaconuuid |
| Quitter la balise UUID | exitmobilebeaconuuid |
| Accès à la balise de proximité | entrymobilebeaconproximity |
| Quitter la balise de proximité | exitmobilebeaconproximity |

### Adobe Advertising Cloud (AMO)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| AMO EF ID | amo_ef_id |
| ID AMO | amo_cid |

### Activity Map

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Lien d’Activity Map par région | clickmaplinkbyregion |
| Région d’Activity Map | clickmapregion |
| Lien d’Activity Map | clickmaplink |
| Activity Map  Page | clickmappage |

### Intégration Nielsen

Pour plus d’informations sur la manière d’implémenter cette intégration, consultez la section [Partenariat Nielsen](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html).

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Modèle de publicité Nielsen | nielsenadmodel |
| Segment C Nielsen | nielsensegmentc |
| Segment B Nielsen | nielsensegmentb |
| Segment A Nielsen | nielsensegmenta |
| ID de contenu Nielsen | nielsencontentid |
| Ressource/Programme Nielsen | nielsenasset |
| VCID Nielsen | nielsenvcid |
| Désinscription Nielsen | nielsenoptout |
| ID + VCID client Nielsen | nielsenclientidvcid |
| ID client Nielsen | nielsenclientid |
| Accès désinscription Nielsen | entrynielsenoptout |
| Quitter désinscription Nielsen | exitnielsenoptout |
| Accès ID + VCID client Nielsen | entrynielsenclientidvcid |
| Quitter ID + VCID client Nielsen | exitnielsenclientidvcid |
| Accès ID client Nielsen | entrynielsenclientid |
| Quitter ID client Nielsen | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| ID de ressource | aemassetid |
| Source de la ressource | aemassetsource |
| ID de la ressource sélectionnée | aemclickedassetid |
| Accès ID de ressource | entryaemassetid |
| Quitter ID de ressource | exitaemassetid |

### Adobe Campaign

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Adobe Campaign Identifiant Diffusion exécutée | ac_delivery_internal_name |
