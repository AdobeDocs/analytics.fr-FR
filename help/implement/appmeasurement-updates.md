---
title: Notes de mise à jour d’AppMeasurement pour JavaScript
description: Notes de mise à jour cumulées pour AppMeasurement pour JavaScript.
subtopic: Release notes
translation-type: tm+mt
source-git-commit: 54804b1b00730a99b7352619d04bdbd2566ba5d3

---


# Notes de mise à jour d’AppMeasurement pour JavaScript

Notes de mise à jour cumulées pour [!DNL AppMeasurement] pour JavaScript.

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

Vous pouvez télécharger la dernière version d’AppMeasurement dans le Gestionnaire de [code](/help/admin/admin/code-manager-admin.md).

## Version 2.18.0

Date de publication : **13 février 2020**

* AppMeasurement peut désormais forcer les cookies à inclure l’attribut Secure en définissant la [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) variable. Cette variable nécessite que le site Web client entier soit servi de manière sécurisée (HTTPS). (AN-204604)

## Version 2.17.0

Date de publication : **23 août 2019**

* Ajout de la prise en charge du reclassement des chaînes de requête Baidu. (AN-182483)
* Correction d’un problème en raison duquel des valeurs de visiteurs caduques dans les accès étaient placées en file d’attente en attendant une acceptation. (AN-184391)

## Version 2.16.0

Date de publication : **15 août 2019**

* Mise en œuvre de la prise en charge `sendBeacon` des liens de sortie dans [!UICONTROL AppMeasurement]. Si un accès est utilisé `sendBeacon` et que la page est déchargée, la requête est toujours terminée. Cela s’avère très utile pour les liens de sortie, car il est plus probable que l’accès atteigne les serveurs de collecte de données. (AN-175142)
* Les valeurs ECID/fid sont maintenant mises en cache au premier accès, même si les paramètres OptIn changent. (AN-175142)
* Mise à jour du module Gestion de l’audience vers DIL 9.3. (AN-182704)
* Exposed switch in `s.ActivityMap.trackScrollReach` to turn scroll reach tracking on or off. (AN-182754)
* Mise à niveau d’AppMeasurement pour utiliser le service d’identification des visiteurs 4.4.0. (AN-182912)

## Version 2.15.0

Date de publication : **15 juillet 2019**

* Ajout du suivi de la portée de défilement Activity Map à l’extension Activity Map (AN-172949)
* Ajout de DIL 9.2 à AppMeasurement (AN-182472)

## Version 2.14.0

Date de publication : **21 mai 2019**

* Correction de problèmes liés à la gestion de l’état des paramètres de suivi lorsque plusieurs accès sont en attente. (AN-176931, AN-176629, DTM-12758)
* Mise à jour d’AppMeasurement pour inclure Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Date de publication : **10 avril 2019**

* Correction de nombreux problèmes signalés avec clearVars. Le problème survient lorsque les accès sont envoyés avant que l’outil de suivi ne soit prêt. Lorsque l’outil de suivi est prêt, la bibliothèque peut définir des variables qui ont déjà été effacées ou modifiées. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Date de publication : **22 février 2019**

* Mise à jour du module Gestion de l’audience vers DIL 9.1. (AN-175255)
* La stratégie de sécurité GTM n’autorise pas le module Activity Map. (AN-174679)
* Amélioration d’AppMeasurement afin d’honorer le droit d’opposition quand le service d’identité n’est pas approuvé dans l’accord préalable. (AN-175259)

## Version 2.11.0

Date de publication : **11 février 2019**

* Ajout de la prise en charge des nouveaux services de souscription Adobe dans AppMeasurement. (AN-163546)
* Ajout de la prise en charge du stockage des données de suivi des liens pour le stockage de session. (AN-162272)
* Ajout de la prise en charge du type de flux multimédia pour Audio Analytics. (AN-173265)

## Version 2.10.0

Date de publication : **20 septembre 2018**

Cette version garantit l’envoi correct des cookies par la bibliothèque [!DNL AppMeasurement] pour tous les types de connexions.

* [!DNL AppMeasurement] bloque les transmissions de cookies durant les instructions POST. (AN-165538)
* Prise en charge de la fonction Déposer pour XDomainRequest. (AN-165733)
* Réduction de la durée de vie par défaut des cookies d’[!DNL AppMeasurement] de cinq à deux ans. (AN-158572)
* Suppression du module média du Gestionnaire de code ([!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0

Date de publication : **24 mai 2018**

> [!NOTE]L’API visiteur version 3.0 ou ultérieure est requise pour les clients utilisant le service ID [!DNL Experience Cloud]. Adobe recommande d’effectuer une mise à niveau vers la dernière version de l’API visiteur à chaque fois que des bibliothèques de code associées sont mises à jour ([!DNL at.js], [!DNL AppMeasurement.js] etc.).

* Mise à jour d’[!DNL AppMeasurement] permettant d’utiliser l’interface Visiteur mise à jour pour demander des identifiants. (AN-151483)
* Correction d’un problème en raison duquel le cookie de suivi des liens continue à s’écrire alors que le suivi des liens est désactivé. (AN-156332)
* Correction d’un problème en raison duquel `registerPreTrackCallback` et `registerPostTrackCallback` interrompent la signature de la fonction de rappel lorsqu’elles sont appelées plusieurs fois. (AN-158566)

## Version 2.8.2

Date de publication : **12 avril 2018**

* Mise à jour d’[!DNL AppMeasurement] permettant d’utiliser l’interface visiteur mise à jour pour demander des identifiants. (AN-151483)
* Le cookie de suivi des liens continue à être écrit une fois que le suivi des liens est désactivé. (AN-156332)
* Réduction de la durée de vie par défaut des cookies d’[!DNL AppMeasurement] de cinq à deux ans. (AN-158572)

## Version 2.8.1

Date de publication : **29 mars 2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

## Version 2.8.0

Date de publication : **15 mars 2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

* Compilation de VAPI v3.1 avec [!DNL AppMeasurement] v2.8. (AN-158353)
* Refactorisation de la création du point de terminaison de la collecte de données afin de faciliter le partage. (AN-156647)
* Ajout des mesures de minutage en boucle des demandes dans [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0

Date de publication : **18 janvier 2018**

* Fin de la prise en charge d’IE 6 à 9
* Inclusion de l’API visiteur version 3.0.0
* Inclusion de DIL v7.00

## Version 2.6.0

Date de publication : **9 novembre 2017**

Correction d’un problème en raison duquel la bibliothèque [!DNL AppMeasurement] ne définit pas toujours la combinaison de compte correcte lorsque s_gl est appelé. (AN-152153)

## Version 2.5.0

Date de publication : **21 septembre 2017**

* Inclusion de [!DNL dil.js 6.12] (module [!DNL Audience Manager])
* Inclusion de l’API visiteur version 2.5.0.

## Version 2.4.0

Date de publication : **17 août 2017**

* dil.js v6.11 inclus
* API Visiteur 2.4.0 inclus

## Version 2.3.0

Date de publication : **20 juillet 2017**

* Correction d’un bogue `s.Util.getQueryParam` capturé `#`
* Ajout de la version 6.10 du fichier `dil.js` (AN-145701)

## Version 2.2.0

Date de publication : **8 juin 2017**

* Prise en charge supplémentaire de plusieurs commandes d’instanciation d’[!DNL AppMeasurement]. (AN-138237)
* Inclusion de l’API visiteur version 2.2.0. (AN-144042)

## Version 2.1.0

Date de publication : **20 avril 2017**

* Comprend la dernière version de `dil.js` (AN-140396)
* Ajout de la prise en charge du paramètre `adobe_mc_ref` qui remplace le référent de la page. (AN-131920)
* API Visiteur 2.1.0. de nouveau inclus. (AN-140873)
* Ajout du paramètre `mcorgid`. (AN-139586)
* Paramètre cp (customerPerspective) ajouté. (AN-140897)

## Version 2.0.0

Date de la version : **9 mars 2017**

* Migration vers un nouveau processus de compilation qui nécessite une mise à jour vers la version 2.0.0. (AN-137878)
* Déplacement du traitement de mboxMCSDID à l’emplacement de section correct où est effectué l’appel de suivi. (AN-138483)

## Version 1.8.0

Date de publication : **19 janvier 2017**

* Inclusion de VisitorAPI 2.0.0
* Appels et vérifications de fonctions reséquencés de façon à ce que la consommation du SDID ait lieu une fois la vérification de l’abandon terminée. (AN-134364)
* Ajout `s.registerPreTrackCallback` et `s.registerPostTrackCallback` crochets. (AN-134567)

## Version 1.7.0

Mise à jour : **11 novembre 2016**

* API Visiteur 1.10.1 inclus.
* Mise à jour du module [!DNL Audience Manager] avec la bibliothèque Demdex Integration (DIL) 6.6. (AN-132065)
* Inclusion de l’API visiteur version 1.9.0. (AN-132072)
* Mise à jour du module [!DNL AppMeasurement] [!DNL Audience Manager] avec DIL 6.5 et des configurations supplémentaires (AN-129411)
* Inclusion de l’API visiteur version 1.8.0 (AN-129887)

## Version 1.6.4

Updated: **August 18, 2016**

* Mise à jour d’[!DNL AppMeasurement] afin de pouvoir lire et écrire les cookies AMCV. (AN-127098)
* Inclusion de l’API visiteur version 1.7.0.

> [!NOTE] Voir aussi les notes de mise à jour suivantes relatives à [!DNL JavaScript] version 1.6.3, qui décrivent les exigences à jour du service Experience Cloud ID.

## Version 1.6.3

Updated: **August 4, 2016**

* Correction d’un problème en raison duquel [!DNL AppMeasurement] mettait fin de manière prématurée aux connexions des requêtes. (AN-126448)

>[!IMPORTANT] La version 1.6.0 du service [!DNL Experience Cloud] ID *exige* [!DNL AppMeasurement] pour [!DNL JavaScript] version 1.6.3 ou supérieure. If you want to upgrade to version 1.6.0 of the Experience Cloud ID service, please make sure you are using [!DNL AppMeasurement] code version 1.6.3 or higher.

## Version 1.6.2

Date de publication : **21 juillet 2016**

* Inclusion de l’API visiteur version 1.6.0.
* Correction d’un problème en raison duquel [!DNL AppMeasurement] appelait la méthode d’obscurcissement incorrecte dans l’API visiteur. (AN-126006)
* Correction d’un problème provoquant l’erreur [!DNL JavaScript] : « Attribute only valid on v:image » (attribut valide seulement sur v:image). (AN-124009)

## Version 1.6.1

Date de publication : **16 juin 2016**

* Inclusion de l’API visiteur version 1.5.7.
* Correction de la prise en charge du suivi des clics sur les liens dans Firefox, qui ne couvrait pas l’événement complet.

## Version 1.6

Date de publication : **21 avril 2016**

* The [!DNL AppMeasurement] Activity Map module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. En outre, le suivi d’Activity Map est activé par défaut. (AN-112689)
* Correction d’un problème de troncation lié à l’ordre des variables de chaîne de requête dans [!DNL AppMeasurement], afin que *`pageURLRest`* soit le dernier. (AN-114647)

## Version 1.5.4

Date de publication : **17 mars 2016**

* Inclusion de l’API visiteur version 1.5.4
* Prise en charge de l’exclusion de l’API visiteur version 1.5.4+

## Version 1.5.3

Date de publication : **21 janvier 2016**

* Correction de la gestion du module [!DNL Audience Manager] lors de l’utilisation de POST pour les appels de suivi. (AN-115381)
* Déplacement du reste de l’URL de la page (&quot;-g&quot;) à la fin de la chaîne de requête de demande de suivi. (AN-114647)

## Version 1.5.2

Date de publication : **5 novembre 2015**

* Inclusion de l’API visiteur version 1.5.3.
* Correction de la détection d’IE11 pour la troncation des URL 2047 (AN-114914)

## Version 1.5.1

Date de publication : **17 septembre 2015**

* Inclusion de l’API visiteur version 1.5.2
* Mise à jour du module [!DNL Audience Manager] pour pouvoir utiliser les identifiants AAM DIL 6.2 - getCustomer de VisitorAPI.js et les transmettre dans l’appel d’événement à AAM. (AN-104978)

## Version 1.5

Date de publication : **18 juin 2015**

* Prise en charge de l’API visiteur version 1.5 qui utilise la méthode *`getCustomerIDs`* pour rassembler les ID de client et l’état authentifié et envoyer les ID avec les demandes de collecte de données.
* Correction d’un problème lié à la création d’iframe de destination en double dans le module **[!UICONTROL AudienceManagement]** (DIL 6.1).
* Correction du problème connu décrit dans la version 1.4.5.

## Version 1.4.5

Date de publication : **21 mai 2015**

* Depuis la version 4.5 du SDK iOS, une nouvelle extension iOS vous permet de collecter des données d’utilisation à partir des applications Apple Watch, des widgets d’aujourd’hui, des widgets de retouche photo et de toutes les autres applications d’extension iOS. Reportez-vous à la section Mise en oeuvre [des extensions](https://docs.adobe.com/content/help/en/mobile-services/ios/ios-ext/ios-ext.html) iOS dans le guide de l’utilisateur des services mobiles.
* Depuis la version 4.5 du SDK Android, une nouvelle extension Android vous permet de collecter des données depuis votre application Android portable. Reportez-vous à la page [Android wearables](https://docs.adobe.com/content/help/en/mobile-services/android/wearables-android/android-wearable.html) dans le guide de l’utilisateur des services mobiles.
* Inclusion de l’API visiteur version 1.4.
* Mise à jour du module AudienceManagement afin de permettre l’utilisation de DIL version 6.0.

> [!NOTE] Problème **** connu : Dans les intégrations API visiteur/ [!DNL AppMeasurement] module [!DNL Audience Manager] , deux requêtes iFrame de publication de destination sont effectuées dans IE6-9 : `//fast.<subdomain>.demdex.net/dest5.html` et `//fast.<subdomain>.demdex.net/dest4.html`. Le comportement correct, comme dans les autres navigateurs, consiste à charger uniquement `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4

Date de publication : **16 avril 2015**

* Vous pouvez maintenant inclure des variables de données contextuelles personnalisées aux mesures de cycle de vie.
* The `trackBeacon` and `clearCurrentBeacon` calls are now available in PhoneGap.
* A minor fix to clear the light server call profile ID after the `trackLight` call.

## Version 1.4.3

Date de publication : **19 février 2015**

* Homogénéisation de la gestion de tous les appels de suivi retardés, avec correction des problèmes liés aux variables sauvegardées durant le retard (par exemple l’objet sur lequel on a cliqué).
* Changement en « ne pas procéder au suivi automatique des référents » après le premier appel de suivi de sorte que le 2e, 3e, etc. appel de suivi (généralement le suivi des liens) ne comptabilise pas deux fois le référent quand *`s.referrer`* a été manuellement défini avant le premier appel de suivi.
* Le fichier compressé de distribution a été mis à jour pour inclure l’API visiteur 1.3.5.

## Version 1.4.2

Date de publication : **15 janvier 2015**

* Correction d’un problème lors de la gestion du prérendu WebKit afin d’empêcher le suivi des pages prérendues qui ne sont pas consultées.
* Le fichier compressé de distribution a été mis à jour afin d’inclure l’API visiteur 1.3.4 et un module **[!UICONTROL AudienceManagement]** mis à jour qui inclut la bibliothèque d’intégration des données (DIL) version 5.5.

## Version 1.4.1

Date de publication : **18 septembre 2014**

* Ajout d’une variable `tagContainerMarker` qui permet à la mise en œuvre de spécifier jusqu’à 4 caractères annexés à la chaîne de version avec un délimiteur de caractère (tiret) supplémentaire. Ceci est utilisé par la gestion dynamique des balises.

   ```js
   // JavaScript
   s.tagContainerMarker = "D1.0";
   
   // Data Collection request
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   Les 4 caractères se limitent aux caractères autorisés dans les URL d’accès aux fichiers, tels les caractères alphanumériques et le point.

* Sur les pages à balisage double avec du code H, correction d’une boucle pouvant survenir durant le suivi automatique des liens (téléchargement et sortie) alors que le suivi forcé des liens est activé (par défaut dans les navigateurs Webkit). En outre, ajout d’une protection générale autour du suivi automatique des liens afin d’empêcher la survenue de telles boucles. Cette protection limite à une fois toutes les 10 secondes le suivi automatique des liens pour les clics répétés vers le *même* objet. Cette protection s’applique uniquement au suivi automatique des liens, de sorte que les appels de suivi manuel des liens (s.tl) ne sont pas limités. Les clics vers d’autres objets ne sont pas non plus concernés par cette protection et feront l’objet d’un suivi.
* Correction de la gestion des objets sur lesquels l’utilisateur a cliqué lorsqu’un délai est nécessaire.
* Correction d’un problème en raison duquel le nombre de pages vues était double lorsque la variable s.t était invoquée à partir d’une fonction onclick, si l’API visiteur n’avait pas encore les valeurs requises.
* Prise en charge de HTTP POST.

   > [!IMPORTANT] Pour qu’un [!DNL Analytics] appel utilise la méthode POST au lieu de la méthode GET dans [!DNL AppMeasurement] (une méthode de résolution des URL [tronquées dans IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), vous devez utiliser la dernière mise en oeuvre du service d’identification des visiteurs pour Experience Cloud.

## Version 1.4

Date de publication : **21 août 2014**

* La suppression du suivi des modules externes de navigateur (paramètre de requête `p`) en tant que modules externes n’est plus reportée dans la version 15.
* Ajout du module **[!UICONTROL AudienceManagement]** dans le fichier compressé de téléchargement.
* Ajout de la prise en charge des eVars (76 à 250) et événements (101 à 1000) supplémentaires.

> [!NOTE] Le code H ne prend pas en charge les eVars et événements supplémentaires.

## Version 1.3.2

Date de publication : **19 juin 2014**

* Correction de la gestion des indicateurs Terminé et En attente dans les champs d’API de visiteur, par exemple l’identifiant visiteur hérité d’[!DNL Analytics], qui générait des erreurs.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.

## Version 1.3.1

Date de publication : **22 mai 2014**

* La fonction d’[!DNL AppMeasurement] pour [!DNL JavaScript] `s_gi` ne recherchait pas correctement les instances créées à l’aide du code H `s_gi`. Notez que ce problème avait uniquement une incidence sur certaines implémentations de marquage double dans lesquelles le code [!DNL AppMeasurement] pour [!DNL JavaScript] et le code H figuraient dans une même page avec des instances distinctes et que `s_gi` était utilisé pour rechercher des instances par suite de rapports.

## Version 1.3

Date de publication : **17 avril 2014**

* Prise en charge du service [d’identification des visiteurs](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud.

## Version 1.2.4

Date de publication : **13 mars 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.3

Date de publication : **20 février 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.2

Date de publication : **6 février 2014**

* Correction d’un problème de compatibilité avec le module [!DNL Audience Manager] DIL. Les utilisateurs d’[!DNL Audience Manager] doivent également effectuer la mise à jour vers la version 4.8 du module DIL.

## Version 1.2.1

Date de publication : **15 novembre 2013**

* Correction des événements de page utilisés pour la mesure vidéo Pulsation.

## Version 1.2

Date de publication : **14 novembre 2013**

* Added support for [Heartbeat video measurement](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).
* `VisitorAPI.js` a été ajouté à la prise en charge du [service d’identification des visiteurs](https://docs.adobe.com/content/help/en/id-service/using/home.html).

## Version 1.1.1

* Un appel de suivi de liens ne pouvait pas être envoyé à partir des navigateurs Opera pour les liens commençant par « opera: » (« opera: » est semblable à « about: » et « chrome: » dans d’autres navigateurs).
* Ajout de `alt=""` à tous les objets Image en vue de la conformité avec le « Communications and Video Accessibility Act ».

## Version 1.1

Date de publication : **18 septembre 2013**

* Correction de la prise en charge du positionnement du code de bibliothèque et de page dans la balise `head`.
* Ajout de la prise en charge du module `onLoad` manquante.

## Version 1.0.3

Date de publication : **15 août 2013**

* Ajout de la prise en charge du déploiement dans la gestion des balises Adobe.
* Correction d’un problème qui empêchait les variables hiérarchiques d’être définies sur l’objet [!DNL AppMeasurement].

## Version 1.0.2

Date de publication : **18 juillet 2013**

* Le hachage/fragment est désormais ignoré par le suivi automatique des liens. Auparavant, l’URL suivante était automatiquement suivie puisque l’intégralité du contenu entre les balises `href` se terminait par `.pdf` :

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Désormais, le hachage/fragment est ignoré de sorte que le lien est suivi uniquement lorsque le nom de fichier se termine par une extension qui correspond.

## Version 1.0.1

Date de publication : **23 mai 2013**

Une nouvelle bibliothèque [!DNL JavaScript] [!DNL AppMeasurement] est désormais disponible dans le Gestionnaire de code. Cette bibliothèque fournit les mêmes fonctionnalités de base que le fichier [!DNL s_code.js] ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau.

* 3 à 7 fois plus rapide que le code H.25.
* Décompressée : 21 Ko uniquement ; 8 Ko dans un fichier gzip (code H.25 : 33 Ko décompressé et 13 Ko dans un fichier gzip).
* Prise en charge native pour l’obtention des paramètres de requête, la lecture et l’écriture de cookies et le suivi avancé des liens.
* Suffisamment petite et rapide pour être utilisée sur les sites pour mobiles et suffisamment robuste pour être utilisée sur les sites pour Bureau, ce qui vous permet d’exploiter une seule et même bibliothèque dans tous les environnements web.
