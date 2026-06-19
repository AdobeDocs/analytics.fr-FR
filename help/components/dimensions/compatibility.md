---
title: Compatibilité des dimensions Analytics
description: Référence pour les dimensions et les rapports Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
TQID: https://experienceleague.adobe.com/WntN8KyUXgQUt8vvoHUZyQfTtEUSS3aPOF6pIDbJynk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: c9bb7ea6-c04f-4262-b69c-fbb8d91e3559
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 905
ht-degree: 55%

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
| [&#x200B; Prise en charge des cookies &#x200B;](cookie-support.md) | `cookie` |
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
| [&#x200B; Canal Dernière touche &#x200B;](last-touch-channel.md) | `lasttouchchannel` |
| [&#x200B; Détails du canal Dernière touche &#x200B;](last-touch-detail.md) | `lasttouchchanneldetail` |
| Variables de liste | `listvariables` |
| [&#x200B; Canal marketing &#x200B;](marketing-channel.md) | `marketingchannel` |
| [Prise en charge audio mobile](mobile-dimensions.md) | `mobileaudiosupport` |
| [Opérateur de téléphonie mobile](mobile-dimensions.md) | `mobilecarrier` |
| [Profondeur de couleur mobile](mobile-dimensions.md) | `mobilecolordepth` |
| [Prise en charge des cookies mobiles](mobile-dimensions.md) | `mobilecookiesupport` |
| [Appareil mobile](mobile-dimensions.md) | `mobiledevicename` |
| [Type d’appareil mobile](mobile-dimensions.md) | `mobiledevicetype` |
| [Mobile - Longueur max. d’e-mail](mobile-dimensions.md) | `mobileemaillength` |
| [&#x200B; Prise en charge des images mobiles &#x200B;](mobile-dimensions.md) | `mobileimagesupport` |
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
| [&#x200B; Moteur de recherche - Naturel &#x200B;](search-engine.md) | `searchenginenatural` |
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
| [&#x200B; États américains &#x200B;](us-states.md) | `state` |
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
| [Type d’accès](hit-type.md) | `customerperspective` |
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
| [&#x200B; Type de contenu &#x200B;](sm-core.md) | `videocontenttype` |
| [Nom du lecteur de publicités](sm-ads.md) | `videoadplayername` |
| [Position de la publicité dans la capsule](sm-ads.md) | `videoadinpod` |
| [Images perdues](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Erreurs](sm-quality.md) | `videoqoeerrorcountevar` |
| [Débit moyen](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Changements de débit](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Durée totale de la mémoire tampon](sm-quality.md) | `videoqoebuffertimeevar` |
| [Événements de mémoire tampon](sm-quality.md) | `videoqoebuffercountevar` |
| [Heure de commencer](sm-quality.md) | `videoqoetimetostartevar` |
| [capsule publicitaire](sm-ads.md) | `videoadpod` |
| [Chemin d’accès au média](sm-core.md) | `videopath` |
| [Annonce](sm-ads.md) | `videoad` |
| [Nom du lecteur de contenu](sm-core.md) | `videoplayername` |
| [&#x200B; Canal de contenu &#x200B;](sm-core.md) | `videochannel` |
| [Chapitre](sm-chapters.md) | `videochapter` |
| [Nom du contenu (variable)](sm-core.md) | `videoname` |
| [Longueur du contenu (variable)](sm-core.md) | `videolength` |
| [Nom de l’annonce publicitaire (variable)](sm-ads.md) | `videoadname` |
| [Longueur de l’annonce publicitaire (variable)](sm-ads.md) | `videoadlength` |
| [Afficher](sm-video-metadata.md) | `videoshow` |
| [&#x200B; Saison &#x200B;](sm-video-metadata.md) | `videoseason` |
| [Épisode](sm-video-metadata.md) | `videoepisode` |
| [Réseau](sm-video-metadata.md) | `videonetwork` |
| [Afficher le type](sm-video-metadata.md) | `videoshowtype` |
| [Chargements publicitaires](sm-ads.md) | `videoadload` |
| [&#128279;](sm-video-metadata.md) | `videomvpd` |
| [Jour](sm-video-metadata.md) | `videodaypart` |
| [Publicitaire](sm-ads.md) | `videoadadvertiser` |
| [ID de campagne](sm-ads.md) | `videoadcampaign` |
| [Genre](sm-video-metadata.md) | `videogenre` |
| [Type de flux](sm-core.md) | `videostreamtype` |
| [ID d’erreur du lecteur SDK](sm-quality.md) | `videoqoeplayersdkerrors` |
| [ID d’erreur externe](sm-quality.md) | `videoqoeextneralerrors` |
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

### Adobe Advertising

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nom de la dimension (visible dans l’interface utilisateur d’Analytics) | ID de dimension (utilisé dans les requêtes API) |
|--- |--- |
| [Lien d’Activity Map par région](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Région d’Activity Map](activity-map-region.md) | `clickmapregion` |
| [Lien d’Activity Map](activity-map-link.md) | `clickmaplink` |
| [Page d’Activity Map](activity-map-page.md) | `clickmappage` |

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
