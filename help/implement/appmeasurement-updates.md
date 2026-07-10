---
title: Notes de mise à jour d’AppMeasurement pour JavaScript
description: Notes de mise à jour cumulées pour AppMeasurement pour JavaScript.
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/iszRZIB8QN3ihEcNWcOHyO1rVGMuKpt6YTkrquuKfWs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 2880
ht-degree: 69%

---

# Notes de mise à jour d’AppMeasurement pour JavaScript

>[!IMPORTANT]
>
>À compter de mars 2025, cet article ne sera plus mis à jour. Vous pouvez afficher les notes de mise à jour d’et télécharger la dernière version d’AppMeasurement à partir de [GitHub](https://github.com/adobe/appmeasurement/releases).


## Version 2.27.0

Date de publication : **mardi 12 août 2024**

* Le cookie `s_ac` est désormais écrit avec l’indicateur `secure` si `writeSecureCookies` a été activé.
* Correction d’une erreur d’initialisation lorsque la bibliothèque était incorporée en ligne.
* Correction d’une erreur en cas de désactivation de `localStorage` ou `sessionStorage`.
* Les User-Agent Hints à entropie élevée sont désormais inclus dans les appels de suivi des liens (`tl`) si `collectHighEntropyUserAgentHints` a été activé.

## Version 2.26.0

Date de publication : **mardi 4 mars 2024**

* AppMeasurement reconnaît et utilise automatiquement le domaine racine pour les domaines de niveau supérieur de code de pays, qui nécessitaient auparavant des configurations de domaine de cookie spécifiques. La mise à jour peut avoir des implications en raison de cette reconnaissance automatique.
* La distribution comprend la bibliothèque du service d’identification des visiteurs 5.5.0 et Data Integration Library 9.6.

## Version 2.25.0

Date de publication : **mercredi 12 septembre 2023**

* Ajout de la méthode facultative [`bufferRequests()`](vars/functions/bufferrequests.md) d’améliorer la fiabilité de la capture de requêtes lorsqu’un navigateur ne prend pas en charge l’API de balise ou annule les requêtes lors du déchargement d’une page.
* Ajout de mesures de sécurité pour empêcher plusieurs rappels de post-suivi pour une seule demande de suivi.

## Version 2.24.0

Date de publication : **mercredi 18 juillet 2023**

* Ajout de la variable de configuration facultative [`decodeLinkParameters`](vars/config-vars/decodelinkparameters.md) pour décoder les URL de lien qui incluent des caractères codés sur deux octets.
* Ajout de la gestion des erreurs supplémentaires pour les navigateurs dotés d’API d’indications du client de l’agent utilisateur à entropie élevée défectueuses.
* Modification de l’en-tête Type de contenu POST pour utiliser `x-www-form-urlencoded` par défaut.

## Version 2.23.0

Date de publication : **23 septembre 2022**

* AppMeasurement prend désormais en charge la collecte d’indications du client de la chaîne Agent-utilisateur à entropie élevée que les navigateurs Chromium (Google Chrome et Microsoft Edge) utilisent pour fournir des informations sur les appareils. Vous pouvez configurer des indications du client via des balises ou utiliser la variable de configuration [`collectHighEntropyUserAgentHints`](vars/config-vars/collecthighentropyuseragenthints.md). La collecte d’indications à entropie élevée est désactivée par défaut. En savoir plus sur la chaîne Agent-utilisateur et les [indications du client](/help/technotes/client-hints.md).

## Version 2.22.4

Date de publication : **18 janvier 2022**

* L’appel de suivi des liens `s.tl()` vérifie désormais que l’objet qui lui est transmis contient un attribut `href` de type `string`. S’il ne s’agit pas d’un `string`, il ignore gracieusement l’attribut `href` au lieu d’échouer. Ce scénario peut se produire lorsque vous transmettez des objets `svg` à l’appel de suivi des liens.

## Version 2.22.3

Date de publication : **11 octobre 2021**

* Mise à jour des liens dans les fichiers pointant vers la documentation.

## Version 2.22.2

Date de publication : **7 septembre 2021**

* Cette mise à jour entraîne toujours l’inclusion de `opt.dmp` et `opt.sell` lors du suivi des liens. Pour plus d’informations, consultez la section [Compte rendu des performances sur la confidentialité](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md) dans le guide d’utilisation destiné à l’administrateur.

## Version 2.22.1

Date de publication : **17 août 2021**

* Les clients ayant choisi lʼexclusion peuvent avoir constaté que les paramètres dʼexclusion de transfert côté serveur ne sont pas respectés lors du suivi des liens. Les correctifs de cette version entraînent lʼenvoi des indicateurs dʼexclusion sʼils sont présents lors du suivi des liens.

## Version 2.22.0

Date de publication : **4 août 2020**

* Correction relative à un référent manquant lorsque le premier accès n’était pas envoyé en raison des préférences de désinscription de l’utilisateur.

## Version 2.21.0

Date de publication : **24 juin 2020**

* Correction d’un problème en raison duquel le filtre linkExclusions d’Activity Map n’était pas toujours appliqué pour Firefox.

## Version 2.20.0

Date de publication : **5 mars 2020**

* Correction d’un problème de sécurité en mettant à jour la détection d’Internet Explorer pour supprimer l’avertissement JSLint.

## Version 2.19.0

Date de publication : **21 février 2020**

* Mise à jour du module Gestion de l’audience vers DIL 9.4. (AN-209341)

## Version 2.18.0

Date de publication : **13 février 2020**

* AppMeasurement peut désormais forcer les cookies à inclure l’attribut Sécurisé en définissant la variable [`writeSecureCookies`](vars/config-vars/writesecurecookies.md). Cette variable requiert la diffusion sécurisée (HTTPS) de l’intégralité du site Web client. (AN-204604)

## Version 2.17.0

Date de publication : **23 août 2019**

* Ajout de la prise en charge du reclassement des chaînes de requête Baidu. (AN-182483)
* Correction d’un problème en raison duquel des valeurs de visiteurs caduques dans les accès étaient placées en file d’attente en attendant une acceptation. (AN-184391)

## Version 2.16.0

Date de publication : **15 août 2019**

* Mise en œuvre de la prise en charge `sendBeacon` des liens de sortie dans [!UICONTROL AppMeasurement]. Si un accès est utilisé `sendBeacon` et que la page est déchargée, la requête est toujours terminée. Cela s’avère très utile pour les liens de sortie, car il est plus probable que l’accès atteigne les serveurs de collecte de données. (AN-175142)
* Les valeurs ECID/fid sont maintenant mises en cache au premier accès, même si les paramètres OptIn changent. (AN-175142)
* Mise à jour du module Gestion de l’audience vers DIL 9.3. (AN-182704)
* Bouton exposé dans `s.ActivityMap.trackScrollReach` permettant d’activer ou de désactiver le suivi de la portée de défilement. (AN-182754)
* Mise à niveau d’AppMeasurement pour utiliser le service d’identification des visiteurs 4.4.0. (AN-182912)

## Version 2.15.0

Date de publication : **15 juillet 2019**

* Ajout du suivi de la portée de défilement ActivityMap à l’extension ActivityMap (AN-172949)
* Ajout de DIL 9.2 à AppMeasurement (AN-182472)

## Version 2.14.0

Date de publication : **21 mai 2019**

* Correction de problèmes liés à la gestion de l’état des paramètres de suivi lorsque plusieurs accès sont en attente. (AN-176931, AN-176629, DTM-12758)
* Mise à jour d’AppMeasurement pour inclure Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Date de publication : **10 avril 2019**

* Correction de nombreux problèmes signalés avec clearVars. Le problème survient lorsque les accès sont envoyés avant que l’outil de suivi ne soit prêt. Lorsque l’outil de suivi est prêt, la bibliothèque peut définir des variables qui ont déjà été effacées ou modifiées. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Date de publication : **22 février 2019**

* Mise à jour du module Gestion de l’audience vers DIL 9.1. (AN-175255)
* La politique de sécurité GTM n’autorise pas le module Activity Map. (AN-174679)
* Amélioration d’AppMeasurement pour honorer la désinscription lorsque le service d’identification des visiteurs n’est pas approuvé dans la souscription. (AN-175259)

## Version 2.11.0

Date de publication : **11 février 2019**

* Ajout de la prise en charge des nouveaux services de souscription Adobe dans AppMeasurement. (AN-163546)
* Ajout de la prise en charge du stockage des données de suivi des liens pour le stockage de session. (AN-162272)
* Ajout de la prise en charge du type de flux multimédia pour Audio Analytics. (AN-173265)

## Version 2.10.0

Date de publication : **20 septembre 2018**

Cette version garantit que la bibliothèque AppMeasurement envoie correctement les cookies pour tous les types de connexion.

* AppMeasurement bloque les transmissions de cookies lors de l’opération POST. (AN-165538)
* Prise en charge de la fonction Déposer pour XDomainRequest. (AN-165733)
* Réduisez la durée de vie des cookies par défaut d’AppMeasurement de cinq à deux ans. (AN-158572)
* Supprimer le module multimédia du Gestionnaire de code ( AppMeasurement) (AN-166590)

## Version 2.9.0

Date de publication : **24 mai 2018**

>[!NOTE]
>
>Une API visiteur version 3.0 ou ultérieure est requise pour les clients qui utilisent le service d’identification des visiteurs. Adobe recommande d’effectuer une mise à niveau vers la dernière version de l’API visiteur à chaque fois que des bibliothèques de code associées sont mises à jour (`at.js`, `AppMeasurement.js` etc.).

* Mise à jour d’AppMeasurement afin d’utiliser l’interface visiteur mise à jour pour demander des identifiants. (AN-151483)
* Correction d’un problème en raison duquel le cookie de suivi des liens continue à s’écrire alors que le suivi des liens est désactivé. (AN-156332)
* Correction d’un problème en raison duquel `registerPreTrackCallback` et `registerPostTrackCallback` interrompent la signature de la fonction de rappel lorsqu’elles sont appelées plusieurs fois. (AN-158566)

## Version 2.8.2

Date de publication : **12 avril 2018**

* Mettez à jour AppMeasurement pour utiliser l’interface visiteur mise à jour pour demander des identifiants. (AN-151483)
* Le cookie de suivi des liens continue à être écrit une fois que le suivi des liens est désactivé. (AN-156332)
* Réduisez la durée de vie des cookies par défaut d’AppMeasurement de cinq à deux ans. (AN-158572)

## Version 2.8.1

Date de publication : **29 mars 2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

## Version 2.8.0

Date de publication : **15 mars 2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 avec AppMeasurement v2.8. (AN-158353)
* Refactorisation de la création du point de terminaison de la collecte de données afin de faciliter le partage. (AN-156647)
* Ajoutez des mesures de durée d’aller-retour de demande à AppMeasurement. (AN-158343)

## Version 2.7.0

Date de publication : **18 janvier 2018**

* Fin de la prise en charge d’IE 6 à 9
* Inclusion de l’API visiteur version 3.0.0
* Inclusion de DIL v7.00

## Version 2.6.0

Date de publication : **9 novembre 2017**

Correction d’un problème en raison duquel la bibliothèque AppMeasurement ne définissait pas toujours la bonne combinaison de comptes lorsque s_gl était appelé. (AN-152153)

## Version 2.5.0

Date de publication : **21 septembre 2017**

* Inclusion d’`dil.js` 6.12 (module Audience Manager)
* Inclusion de l’API visiteur version 2.5.0.

## Version 2.4.0

Date de publication : **17 août 2017**

* dil.js v6.11 inclus
* API Visiteur 2.4.0 inclus

## Version 2.3.0

Date de publication : **20 juillet 2017**

* Bug corrigé lorsqu’il est `s.Util.getQueryParam` capturé `#`
* Ajout de la version 6.10 du fichier `dil.js` (AN-145701)

## Version 2.2.0

Date de publication : **8 juin 2017**

* Ajout de la prise en charge de plusieurs ordres d’instanciation d’AppMeasurement. (AN-138237)
* Inclusion de l’API visiteur version 2.2.0. (AN-144042)

## Version 2.1.0

Date de publication : **20 avril 2017**

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

Date de publication : **19 janvier 2017**

* Inclusion de VisitorAPI 2.0.0
* Appels et vérifications de fonctions reséquencés de façon à ce que la consommation du SDID ait lieu une fois la vérification de l’abandon terminée. (AN-134364)
* Ajout des crochets `s.registerPreTrackCallback` et `s.registerPostTrackCallback`. (AN-134567)

## Version 1.7.0

Mise à jour : **11 novembre 2016**

* API Visiteur 1.10.1 inclus.
* Mettez à jour le module Audience Manager avec Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusion de l’API visiteur version 1.9.0. (AN-132072)
* Mise à jour du module AppMeasurement Audience Manager avec DIL 6.5 et des configurations supplémentaires (AN-129411)
* Inclusion de l’API visiteur version 1.8.0 (AN-129887)

## Version 1.6.4

Mise à jour : **18 août 2016**

* Mise à jour d’AppMeasurement pour lire et écrire des cookies AMCV. (AN-127098)
* Inclusion de l’API visiteur version 1.7.0.

>[!NOTE]
>
>Consultez également les notes de mise à jour de la version 1.6.3 de JavaScript, qui comprend les exigences mises à jour pour le service d’identification des visiteurs.

## Version 1.6.3

Mise à jour : **4 août 2016**

* Correction d’un problème en raison duquel AppMeasurement interrompait prématurément les connexions aux requêtes. (AN-126448)

>[!IMPORTANT]
>
>La version 1.6.0 du service d’identification des visiteurs *nécessite* AppMeasurement pour JavaScript version 1.6.3 ou ultérieure). Si vous souhaitez effectuer une mise à niveau vers la version 1.6.0 du service d’identification des visiteurs, veillez à utiliser AppMeasurement 1.6.3 ou une version ultérieure.

## Version 1.6.2

Date de publication : **21 juillet 2016**

* Inclusion de l’API visiteur version 1.6.0.
* Correction d’un problème en raison duquel AppMeasurement appelait la mauvaise méthode obscurcie dans l’API visiteur. (AN-126006)
* Correction d’un problème qui provoquait l’erreur JavaScript : « Attribut uniquement valide sur v:image ». (AN-124009)

## Version 1.6.1

Date de publication : **16 juin 2016**

* Inclusion de l’API visiteur version 1.5.7.
* Correction de la prise en charge du suivi des clics sur les liens dans Firefox, qui ne couvrait pas l’événement complet.

## Version 1.6

Date de publication : **21 avril 2016**

* Le module AppMeasurement Activity Map a été intégré au module AppMeasurement standard, de sorte qu&#39;il vous suffit de référencer un fichier `.js`. En outre, le suivi d’Activity Map est activé par défaut. (AN-112689)
* Correction d’un problème de troncature qui se produisait avec l’ordre des variables de chaîne de requête dans AppMeasurement, de sorte que *`pageURLRest`* soit le dernier. (AN-114647)

## Version 1.5.4

Date de publication : **17 mars 2016**

* Inclusion de l’API visiteur version 1.5.4
* Prise en charge de l’exclusion de l’API visiteur version 1.5.4+

## Version 1.5.3

Date de publication : **21 janvier 2016**

* Correction de la gestion du module Audience Manager lorsque les POST sont utilisés pour le suivi des appels. (AN-115381)
* Déplacement du reste de l’URL de la page (&quot;-g&quot;) à la fin de la chaîne de requête de demande de suivi. (AN-114647)

## Version 1.5.2

Date de publication : **5 novembre 2015**

* Inclusion de l’API visiteur version 1.5.3.
* Correction de la détection d’IE11 pour la troncation des URL 2047 (AN-114914)

## Version 1.5.1

Date de publication : **17 septembre 2015**

* Inclusion de l’API visiteur version 1.5.2
* Mise à jour du module Audience Manager pour utiliser Adobe Audience Manager DIL 6.2 : obtenez les ID de client à partir de VisitorAPI.js et transmettez-les dans l’appel /event à Adobe Audience Manager. (AN-104978)

## Version 1.5

Date de publication : **18 juin 2015**

* Prise en charge de l’API visiteur version 1.5 qui utilise la méthode *`getCustomerIDs`* pour rassembler les identifiants client et l’état authentifié et envoyer les identifiants avec les demandes de collecte de données.
* Correction d’un problème lié à la création d’iframe de destination en double dans le module **[!UICONTROL AudienceManagement]** (DIL 6.1).
* Correction du problème connu décrit dans la version 1.4.5.

## Version 1.4.5

Date de publication : **21 mai 2015**

* À partir de la version 4.5 d’iOS SDK, une nouvelle extension iOS vous permet de collecter des données d’utilisation à partir de vos applications Apple Watch, des widgets Today, des widgets de retouche photo et de toutes les autres applications d’extension iOS.
* À partir de la version 4.5 d’Android SDK, une nouvelle extension Android vous permet de collecter des données à partir de votre application portable Android.
* Inclusion de l’API visiteur version 1.4.
* Mise à jour du module AudienceManagement afin de permettre l’utilisation de DIL version 6.0.

>[!NOTE]
>
>**Problème connu** : dans les intégrations de l’API visiteur/du module AppMeasurement Audience Manager, il existe deux demandes iFrame de publication de destination créées dans IE6-9 : `//fast.<subdomain>.demdex.net/dest5.html` et `//fast.<subdomain>.demdex.net/dest4.html`. Le comportement correct, comme dans les autres navigateurs, consiste à charger uniquement `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4

Date de publication : **16 avril 2015**

* Vous pouvez maintenant inclure des variables de données contextuelles personnalisées aux mesures de cycle de vie.
* Les appels `trackBeacon` et `clearCurrentBeacon` sont maintenant disponibles dans PhoneGap.
* Correction mineure afin d’effacer l’identifiant de profil d’appel au serveur léger après l’appel de `trackLight`.

## Version 1.4.3

Date de publication : **19 février 2015**

* Homogénéisation de la gestion de tous les appels de suivi retardés, avec correction des problèmes liés aux variables sauvegardées durant le retard (par exemple l’objet sur lequel on a cliqué).
* Modification de pour ne pas effectuer de suivi automatique des référents après le premier appel de suivi de sorte que le 2e, 3e, etc. appel de suivi (généralement le suivi des liens) ne comptabilise pas deux fois le référent lorsqu’*`s.referrer`* a été défini manuellement avant le premier appel de suivi.
* Le fichier compressé de distribution a été mis à jour pour inclure l’API visiteur 1.3.5.

## Version 1.4.2

Date de publication : **15 janvier 2015**

* Correction d’un problème lors de la gestion du prérendu WebKit afin d’empêcher le suivi des pages prérendues qui ne sont pas consultées.
* Le fichier compressé de distribution a été mis à jour afin d’inclure l’API visiteur 1.3.4 et un module **[!UICONTROL AudienceManagement]** mis à jour qui inclut la bibliothèque d’intégration des données (DIL) version 5.5.

## Version 1.4.1

Date de publication : **18 septembre 2014**

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

  >[!IMPORTANT]
  >
  >Pour qu’un appel Analytics utilise la méthode `POST` au lieu de la méthode `GET` dans AppMeasurement (une méthode de résolution [URL tronquées dans IE](/help/implement/js/troubleshooting.md)), vous devez utiliser la dernière mise en œuvre du service d’identification des visiteurs pour l’entreprise CX.

## Version 1.4

Date de publication : **21 août 2014**

* La suppression du suivi des plug-ins de navigateur (paramètre de requête `p`) en tant que plug-ins n’est plus reportée dans la version 15.
* Ajout du module **[!UICONTROL AudienceManagement]** dans le fichier compressé de téléchargement.
* Ajout de la prise en charge des eVars (76 à 250) et événements (101 à 1000) supplémentaires.

>[!NOTE]
>
>Le code H ne prend pas en charge les eVars et événements supplémentaires.

## Version 1.3.2

Date de publication : **19 juin 2014**

* Correction de la gestion des indicateurs Terminé et En attente pour les champs de l’API visiteur tels que l’ancien identifiant visiteur Analytics, qui provoquait des erreurs.
* Prise en charge de nouvelles fonctionnalités dans le service d’identification des visiteurs 1.3.

## Version 1.3.1

Date de publication : **22 mai 2014**

* La fonction `s_gi` d’AppMeasurement for JavaScript ne trouvait pas correctement les instances créées à l’aide du code H `s_gi`. Notez que ce problème n’affectait que certaines implémentations de balisage double où AppMeasurement pour JavaScript et le code H étaient sur la même page avec des instances distinctes et `s_gi` était utilisé pour rechercher des instances par suite de rapports.

## Version 1.3

Date de publication : **17 avril 2014**

* Prise en charge du [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home).

## Version 1.2.4

Date de publication : **13 mars 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.3

Date de publication : **20 février 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.2

Date de publication : **6 février 2014**

* Correction d’un problème de compatibilité avec le module Audience Manager DIL. Les clients Audience Manager doivent également effectuer une mise à jour vers la version 4.8 du module DIL.

## Version 1.2.1

Date de publication : **15 novembre 2013**

* Correction des événements de page utilisés par la mesure vidéo Pulsation.

## Version 1.2

Date de publication : **14 novembre 2013**

* Ajout de la prise en charge de la [mesure vidéo Pulsation](https://experienceleague.adobe.com/fr/docs/media-analytics/using/media-overview).
* `VisitorAPI.js` a été ajouté à la prise en charge du [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home).

## Version 1.1.1

* Un appel de suivi de liens ne pouvait pas être envoyé à partir des navigateurs Opera pour les liens commençant par « opera: » (« opera: » est semblable à « about: » et « chrome: » dans d’autres navigateurs).
* Ajout de `alt=""` à tous les objets Image en vue de la conformité avec le « Communications and Video Accessibility Act ».

## Version 1.1

Date de publication : **18 septembre 2013**

* Correction de la prise en charge du positionnement du code de bibliothèque et de page dans la balise `head`.
* Ajout de la prise en charge du module `onLoad` manquante.

## Version 1.0.3

Date de publication : **15 août 2013**

* Ajout de la prise en charge du déploiement dans la gestion des balises Adobe.
* Correction d’un problème qui empêchait la définition des variables de hiérarchie sur l’objet AppMeasurement.

## Version 1.0.2

Date de publication : **18 juillet 2013**

* Le hachage/fragment est désormais ignoré par le suivi automatique des liens. Auparavant, l’URL suivante était automatiquement suivie puisque l’intégralité du contenu entre les balises `href` se terminait par `.pdf` :

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  Désormais, le hachage/fragment est ignoré de sorte que le lien est suivi uniquement lorsque le nom de fichier se termine par une extension qui correspond.

## Version 1.0.1

Date de publication : **23 mai 2013**

Une nouvelle bibliothèque JavaScript AppMeasurement est désormais disponible dans le Gestionnaire de code. Cette bibliothèque fournit les mêmes fonctionnalités de base que le fichier `s_code.js` ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau.

* 3 à 7 fois plus rapide que le code H.25.
* Décompressée : 21 Ko uniquement ; 8 Ko dans un fichier gzip (code H.25 : 33 Ko décompressé et 13 Ko dans un fichier gzip).
* Prise en charge native pour l’obtention des paramètres de requête, la lecture et l’écriture de cookies et le suivi avancé des liens.
* Suffisamment petite et rapide pour être utilisée sur les sites pour mobiles et suffisamment robuste pour être utilisée sur les sites pour Bureau, ce qui vous permet d’exploiter une seule et même bibliothèque dans tous les environnements web.
