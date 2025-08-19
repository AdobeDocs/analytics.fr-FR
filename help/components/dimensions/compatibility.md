---
title: Compatibilité des dimensions Analytics
description: Référence pour les dimensions et les rapports Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 60%

---

# Compatibilité des dimensions Analytics

Cette page répertorie les [dimensions](overview.md) prises en charge dans leurs fonctionnalités Analytics respectives.

>[!NOTE]
>
>Les attributs de visiteur, les classifications et les noms de variable personnalisée sont omis de cette liste. Ces éléments de dimension sont spécifiques à des suites de rapports individuelles.

## Dimensions prises en charge dans Analysis Workspace

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|---|---|
| Analytics pour Target | `targetraw` |
| ID Audiences | `mcaudiences` |
| [Navigateur](browser.md) | `browser` |
| [Type de navigateur](browser-type.md) | `browsertype` |
| [Catégorie](category.md) | `category` |
| [Villes](cities.md) | `geocity` |
| [Codage des couleurs](color-depth.md) | `colordepth` |
| [Type de connexion](connection-type.md) | `connectiontype` |
| [ Prise en charge des cookies ](cookie-support.md) | `cookie` |
| [Pays](countries.md) | `geocountry` |
| [Fidélité de la clientèle](customer-loyalty.md) | `customerloyalty` |
| [Vars de conversion personnalisées](evar.md) | `evar1`, `evar2`, etc. |
| [Custom Insight Vars](prop.md) | `prop1`, `prop2`, etc. |
| [Lien personnalisé](custom-link.md) | `customlink` |
| [Jours avant le premier achat](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [Jours depuis le dernier achat](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [Domaine](domain.md) | `filtereddomain` |
| [Lien de téléchargement](download-link.md) | `downloadlink` |
| [Page d’entrée](entry-dimensions.md) | `entrypage` |
| [Page d’entrée originale](entry-dimensions.md) | `entrypageoriginal` |
| [Lien de sortie](exit-link.md) | `exitlink` |
| [Canal Première touche](first-touch-channel.md) | `firsttouchchannel` |
| [Détails du canal Première touche](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Compatible Java](java-enabled.md) | `javaenabled` |
| [Langue](language.md) | `language` |
| [ Canal Dernière touche ](last-touch-channel.md) | `lasttouchchannel` |
| [ Détails du canal Dernière touche ](last-touch-detail.md) | `lasttouchchanneldetail` |
| Variables de liste | `listvariables` |
| [ Canal marketing ](marketing-channel.md) | `marketingchannel` |
| [Prise en charge audio mobile](mobile-dimensions.md) | `mobileaudiosupport` |
| [Opérateur de téléphonie mobile](mobile-dimensions.md) | `mobilecarrier` |
| [Profondeur de couleur mobile](mobile-dimensions.md) | `mobilecolordepth` |
| [Prise en charge des cookies mobiles](mobile-dimensions.md) | `mobilecookiesupport` |
| [Appareil mobile](mobile-dimensions.md) | `mobiledevicename` |
| [Type d’appareil mobile](mobile-dimensions.md) | `mobiledevicetype` |
| [Mobile - Longueur max. d’e-mail](mobile-dimensions.md) | `mobileemaillength` |
| [ Prise en charge des images mobiles ](mobile-dimensions.md) | `mobileimagesupport` |
| [Fabricant du dispositif portable](mobile-dimensions.md) | `mobilemanufacturer` |
| [Système d’exploitation mobile (obsolète)](mobile-dimensions.md) | `mobileos` |
| [Hauteur d’écran du dispositif portable](mobile-dimensions.md) | `mobilescreenheight` |
| [Taille d’écran du dispositif portable](mobile-dimensions.md) | `mobilescreensize` |
| [Largeur d’écran du dispositif portable](mobile-dimensions.md) | `mobilescreenwidth` |
| [Longueur d’URL maximale du navigateur mobile](mobile-dimensions.md) | `mobileurllength` |
| [Prise en charge de la vidéo mobile](mobile-dimensions.md) | `mobilevideosupport` |
| [Résolution de l’écran](monitor-resolution.md) | `monitorresolution` |
| [Systèmes d’exploitation](operating-systems.md) | `operatingsystem` |
| [Domaine référent d’origine](original-referring-domain.md) | `referringdomainoriginal` |
| [Page](page.md) | `page` |
| [Pages introuvables](pages-not-found.md) | `pagesnotfound` |
| [Produit](product.md) | `product` |
| [Référent](referrer.md) | `referrer` |
| [Type de référent](referrer-type.md) | `referrertype` |
| [Domaine référent](referring-domain.md) | `referringdomain` |
| [Régions](regions.md) | `georegion` |
| [Fréquence des retours](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [Moteur de recherche](search-engine.md) | `searchengine` |
| [Mot-clé de recherche](search-keyword.md) | `searchenginekeyword` |
| [ Moteur de recherche - Naturel ](search-engine.md) | `searchenginenatural` |
| [Moteur de recherche - Payant](search-engine.md) | `searchenginepaid` |
| [Mot-clé de recherche - Naturel](search-keyword.md) | `searchenginenaturalkeyword` |
| [Mot-clé de recherche - Payant](search-keyword.md) | `searchenginepaidkeyword` |
| [Classement de toutes les pages de recherche](all-search-page-rank.md) | `searchenginepagerank` |
| [Serveur](server.md) | `server` |
| [Visites de page unique](single-page-visits.md) | `singlepagevisits` |
| [Section du site](site-section.md) | `sitesections` |
| [Temps passé par visite - Granulaire](time-spent-per-visit.md) | `sitetime` |
| [Code de suivi](tracking-code.md) | `campaign` |
| [DMA États-Unis](us-dma.md) | `geodma` |
| [ États américains ](us-states.md) | `state` |
| [Durée avant événement](time-prior-to-event.md) | `timeprior` |
| [Durée par visite - Regroupement](time-spent-per-visit.md) | `timespent` |
| [Profondeur de visite](visit-depth.md) | `pathlength` |
| [Nombre de visites](visit-number.md) | `visitnumber` |
| [Code postal](zip-code.md) | `zip` |
| [H/PM](am-pm.md) | `timepartampm` |
| [Hauteur du navigateur - Compartimenté](browser-height.md) | `browserheightbucketed` |
| [Largeur du navigateur - Compartimenté](browser-width.md) | `browserwidthbucketed` |
| [Jour](day.md) | `daterangeday` |
| [Jour du mois](day-of-month.md) | `timepartdayofmonth` |
| [Jour de la semaine](day-of-week.md) | `dayofweek` |
| [Jour de la semaine](day-of-week.md) | `timepartdayofweek` |
| [Jour de l’année](day-of-year.md) | `timepartdayofyear` |
| [Jours depuis la dernière visite](days-since-last-visit.md) | `dayssincelastvisit` |
| [Informations personnalisées d’entrée](entry-dimensions.md) | `entryprops` |
| [Variables de liste d’entrée](entry-dimensions.md) | `entrylistvariables` |
| [Serveur d’entrée](entry-dimensions.md) | `entryserver` |
| [Section Site d&#39;entrée](entry-dimensions.md) | `entrysitesections` |
| [Quitter Custom Insights](exit-dimensions.md) | `exitprops` |
| [Quitter les variables de liste](exit-dimensions.md) | `exitlistvariables` |
| [Page de sortie](exit-dimensions.md) | `exitpage` |
| [Quitter le serveur](exit-dimensions.md) | `exitserver` |
| [Quitter la section du site](exit-dimensions.md) | `exitsitesections` |
| [Profondeur d’accès](hit-depth.md) | `hitdepth` |
| [Type d’accès](hit-type.md) | `hittype` |
| [Heure](hour.md) | `daterangehour` |
| [Heure de la journée](hour-of-day.md) | `timeparthourofday` |
| [Détails du canal marketing](marketing-detail.md) | `marketingchanneldetail` |
| [Minute](minute.md) | `daterangeminute` |
| [Longueur maximale du signet mobile](mobile-dimensions.md) | `mobilebookmarklength` |
| [Numéro d’appareil mobile](mobile-dimensions.md) | `mobiledevicenumber` |
| [DRM mobile](mobile-dimensions.md) | `mobiledrm` |
| [Mobile Information Services](mobile-dimensions.md) | `mobileinformationservices` |
| [Machine virtuelle Java mobile](mobile-dimensions.md) | `mobilejavavm` |
| [Décoration d’e-mail mobile](mobile-dimensions.md) | `mobilemaildecoration` |
| [Protocoles de réseau mobile](mobile-dimensions.md) | `mobilenetprotocols` |
| [Mobile Push To Talk](mobile-dimensions.md) | `mobilepushtotalk` |
| [Mois](month.md) | `daterangemonth` |
| [Mois de l’année](month-of-year.md) | `timepartmonthofyear` |
| [Types de systèmes d’exploitation](operating-system-types.md) | `operatingsystemgroup` |
| [Recherche payante](paid-search.md) | `paidsearch` |
| [Prise en charge des cookies persistants](persistent-cookie-support.md) | `persistentcookie` |
| [Trimestre](quarter.md) | `daterangequarter` |
| [Trimestre de l’année](quarter-of-year.md) | `timepartquarterofyear` |
| Enquête | `surveybase` |
| [Durée de consultation de la page - Regroupement](time-spent-on-page.md) | `averagepagetime` |
| [Temps passé sur la page - Granulaire](time-spent-on-page.md) | `pagetimeseconds` |
| [Suivi du motif de désinscription](tracking-opt-out-reason.md) | `optoutreason` |
| [Jour de la semaine / Week-end](weekday-weekend.md) | `timepartweekdayweekend` |
| [Semaine](week.md) | `daterangeweek` |
| [Année](year.md) | `daterangeyear` |

## Dimensions adaptées au contenu prises en charge uniquement dans Analysis Workspace

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID de session multimédia | `videosessionid` |
| Méthode d’accès Nielsen | `nielsenaccmethod` |
| ID de l’application Nielsen | `nielsenappid` |
| Ressource de canal Nielsen | `nielsenchannelasset` |
| Type de contenu Nielsen | `nielsencontenttype` |

## Dimensions basées sur le contenu prises en charge par Analysis Workspace

### Vidéo (services de médias en flux continu)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| [Contenu](sm-core.md) | `video` |
| [Segment de contenu](sm-core.md) | `videosegment` |
| [Type de contenu](sm-core.md) | `videocontenttype` |
| [Nom du lecteur de publicités](sm-ads.md) | `videoadplayername` |
| [Position de la publicité dans la capsule](sm-ads.md) | `videoadinpod` |
| [Perte d’images](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Erreurs](sm-quality.md) | `videoqoeerrorcountevar` |
| [Débit moyen](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Changements de débit](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Durée totale de la mémoire tampon](sm-quality.md) | `videoqoebuffertimeevar` |
| [Événements de mémoire tampon](sm-quality.md) | `videoqoebuffercountevar` |
| [Temps jusqu’au début](sm-quality.md) | `videoqoetimetostartevar` |
| [Capsule publicitaire](sm-ads.md) | `videoadpod` |
| [Chemin d’accès au média](sm-core.md) | `videopath` |
| [Publicité](sm-ads.md) | `videoad` |
| [Nom du lecteur de contenu](sm-core.md) | `videoplayername` |
| [Canal de contenu](sm-core.md) | `videochannel` |
| [Chapitre](sm-chapters.md) | `videochapter` |
| [Nom du contenu (variable)](sm-core.md) | `videoname` |
| [Durée du contenu (variable)](sm-core.md) | `videolength` |
| [Nom de l’annonce publicitaire (variable)](sm-ads.md) | `videoadname` |
| [Longueur de l’annonce publicitaire (variable)](sm-ads.md) | `videoadlength` |
| [Programme](sm-video-metadata.md) | `videoshow` |
| [Saison](sm-video-metadata.md) | `videoseason` |
| [Épisode](sm-video-metadata.md) | `videoepisode` |
| [Réseau](sm-video-metadata.md) | `videonetwork` |
| [Type de programme](sm-video-metadata.md) | `videoshowtype` |
| [Chargements publicitaires](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [Partie de la journée](sm-video-metadata.md) | `videodaypart` |
| [Annonceur](sm-ads.md) | `videoadadvertiser` |
| [ID de campagne](sm-ads.md) | `videoadcampaign` |
| [Genre](sm-video-metadata.md) | `videogenre` |
| [Type de diffusion](sm-core.md) | `videostreamtype` |
| [ID d’erreur du SDK du lecteur](sm-quality.md) | `videoqoeplayersdkerrors` |
| [ID d’erreur externes](sm-quality.md) | `videoqoeextneralerrors` |
| [Type de flux multimédia](sm-video-metadata.md) | `videofeedtype` |
| [Chemin du média d’entrée](entry-dimensions.md) | `entryvideopath` |
| [Quitter le chemin du média](exit-dimensions.md) | `exitvideopath` |
| [Genre d’entrée](entry-dimensions.md) | `entryvideogenre` |
| [Quitter le genre](exit-dimensions.md) | `exitvideogenre` |
| [ID d’erreur SDK du lecteur d’entrée](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [ID d’erreur du SDK du lecteur de sortie](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [ID d&#39;erreur externe d&#39;entrée](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [ID des erreurs externes de sortie](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social a été mis hors service.

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Termes | `socialterm` |
| Plateformes sociales/Propriétés | `socialcontentprovider` |
| Auteurs | `socialauthor` |
| Langue | `sociallanguage` |
| Latitude / Longitude | `sociallatlong` |
| Codes de suivi des ressources | `socialassettrackingcode` |
| Propriétés sociales détenues | `socialaccountandappids` |
| ID de publication détenue | `socialownedpostids` |
| Définitions sociales détenues | `socialinteractiontype` |
| ID de propriété détenue | `socialownedpropertyid` |
| Propriété détenue et application | `socialownedpropertypropertyvsapp` |
| Nom de propriété détenue | `socialownedpropertyname` |
| Propriété de définition détenue et publication | `socialowneddefinitionpropertyvspost` |
| Type d’informations sur la définition détenue | `socialowneddefinitioninsighttype` |
| Valeur d’informations sur la définition détenue | `socialowneddefinitioninsightvalue` |
| Mesure de définition détenue | `socialowneddefinitionmetric` |
| Ressource | `socialmediaid` |

### SDK Mobile

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| [Première date de lancement](lifecycle-dimensions.md) | `mobileinstalldate` |
| [ID de l’application](lifecycle-dimensions.md) | `mobileappid` |
| [Numéro de lancement](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [Jours depuis la première utilisation](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [Jours depuis la dernière utilisation](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [Heure de la journée (SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [Jour de la semaine (SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [Système d’exploitation (SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [Jours depuis la dernière mise à niveau](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [Lancements depuis la dernière mise à niveau](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [Nom de l’appareil (SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [Version du système d’exploitation (SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [Balise principale](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [Balise mineure](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [UUID de balise](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [Proximité de la balise](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [Lieu (jusqu’à 10 km)](lifecycle-dimensions.md) | `latlon1` |
| [Lieu (jusqu’à 100 m)](lifecycle-dimensions.md) | `latlon23` |
| [Lieu (jusqu’à 1 m)](lifecycle-dimensions.md) | `latlon45` |
| [Nom du point ciblé](lifecycle-dimensions.md) | `pointofinterest` |
| [Distance jusqu’au centre du point ciblé](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [Précision de l’emplacement](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [Placer catégorie](lifecycle-dimensions.md) | `mobileplacecategory` |
| [ID de la place](lifecycle-dimensions.md) | `mobileplaceid` |
| [Balise d’entrée majeure](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [Quitter la balise principale](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [Balise d’entrée mineure](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [Quitter la balise mineure](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [UUID de balise d’entrée](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [Quitter l’UUID de la balise](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [Proximité de la balise d’entrée](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [Quitter la proximité de la balise](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| [Lien Activity Map Par Région](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Région Activity Map](activity-map-region.md) | `clickmapregion` |
| [Lien Activity Map](activity-map-link.md) | `clickmaplink` |
| [Page Activity Map](activity-map-page.md) | `clickmappage` |

### Intégration Nielsen

Pour plus d’informations sur la mise en œuvre de cette intégration, consultez la section [Extension Nielsen](https://exchange.adobe.com/apps/ec/101361) sur Adobe Exchange.

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Modèle de publicité Nielsen | `nielsenadmodel` |
| Segment C Nielsen | `nielsensegmentc` |
| Segment B Nielsen | `nielsensegmentb` |
| Segment A Nielsen | `nielsensegmenta` |
| ID de contenu Nielsen | `nielsencontentid` |
| Nielsen Asset / Programme | `nielsenasset` |
| VCID Nielsen | `nielsenvcid` |
| Désinscription Nielsen | `nielsenoptout` |
| ID + VCID client Nielsen | `nielsenclientidvcid` |
| ID client Nielsen | `nielsenclientid` |
| Accès désinscription Nielsen | `entrynielsenoptout` |
| Quitter désinscription Nielsen | `exitnielsenoptout` |
| Accès ID + VCID client Nielsen | `entrynielsenclientidvcid` |
| Quitter ID + VCID client Nielsen | `exitnielsenclientidvcid` |
| Accès ID client Nielsen | `entrynielsenclientid` |
| Quitter ID client Nielsen | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| ID de ressource | `aemassetid` |
| Source de la ressource | `aemassetsource` |
| ID de la ressource sélectionnée | `aemclickedassetid` |
| Accès ID de ressource | `entryaemassetid` |
| Quitter ID de ressource | `exitaemassetid` |

### Adobe Campaign

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| Adobe Campaign Identifiant Diffusion exécutée | `ac_delivery_internal_name` |
