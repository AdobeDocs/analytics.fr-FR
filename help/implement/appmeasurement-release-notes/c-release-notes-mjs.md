---
description: Notes de mise à jour cumulées pour AppMeasurement pour JavaScript.
subtopic: Release notes
title: AppMeasurement pour JavaScript
topic: Developer and implementation
uuid: 1440013d-d266-4dce-9807-8b9adac73315
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# AppMeasurement pour JavaScript{#appmeasurement-for-javascript}

Notes de mise à jour cumulées pour [!DNL AppMeasurement] pour JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

Vous pouvez télécharger la dernière version de chaque bibliothèque sous **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administration]** &gt; **[!UICONTROL Gestionnaire de code]**.

## Version 2.17.0

Date de publication : **23 août 2019**

| Fonctionnalité/correctif | Description |
| -----------| ---------- |
| Ajout de la prise en charge de Baidu | Ajout de la prise en charge du reclassement des chaînes de requête Baidu. |
| Correction de l’affichage inapproprié comme titre de la valeur | Correction d’un problème en raison duquel des valeurs de visiteurs caduques dans les accès étaient placées en file d’attente en attendant une acceptation. |

## Version 2.16.0

Date de publication : **15 août 2019**

| Fonctionnalité | Description |
| -----------| ---------- |
| Prise en charge `sendBeacon` des liens de sortie | Mise en œuvre de la prise en charge `sendBeacon` des liens de sortie dans [!UICONTROL AppMeasurement]. Cela permettra d’améliorer le suivi des liens de sortie et entraînera probablement par une augmentation du trafic. `SendBeacon` ne s’exécute pas dans le contexte d’une page, mais dans le contexte du navigateur. En d’autres termes, si une page se décharge avec `sendBeacon`, la requête sera toujours exécutée. Cela s’avère très utile pour les liens de sortie, car il est plus probable que la demande de lien de sortie soit exécutée. |
| Valeurs ECID/fid | Les valeurs ECID/fid sont maintenant mises en cache au premier accès, même si les paramètres OptIn changent. |
| DIL 9.3 | Mise à jour du module Gestion de l’audience vers DIL 9.3 |
| Suivi de la portée de défilement | Bouton exposé dans s.ActivityMap.trackScrollReach permettant d’activer ou de désactiver le suivi de la portée de défilement. |
| Service d’identification des visiteurs 4.4.0 | Mise à niveau d’AppMeasurement pour utiliser le service d’identification des visiteurs 4.4.0. |

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

Correction de nombreux problèmes signalés avec clearVars. Le problème survient lorsque les accès sont envoyés avant que l’outil de suivi ne soit prêt. Lorsque l’outil de suivi est prêt, la bibliothèque peut définir des variables qui ont déjà été effacées ou modifiées. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Date de mise à jour : **22/02/2019**

* Mise à jour du module Gestion de l’audience vers DIL 9.1. (AN-175255)
* La stratégie de sécurité GTM n’autorise pas le module Activity Map. (AN-174679)
* Amélioration d’AppMeasurement afin d’honorer le droit d’opposition quand le service d’identité n’est pas approuvé dans l’accord préalable. (AN-175259)

## Version 2.11.0

Date de mise à jour : **11/02/2019**

* Ajout de la prise en charge des nouveaux services de souscription Adobe dans AppMeasurement. (AN-163546)
* Ajout de la prise en charge du stockage des données de suivi des liens pour le stockage de session. (AN-162272)
* Ajout de la prise en charge du type de flux multimédia pour Audio Analytics. (AN-173265)

## Version 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Date de mise à jour : **20/09/2018**

Cette version garantit l’envoi correct des cookies par la bibliothèque [!DNL AppMeasurement] pour tous les types de connexions.

* [!DNL AppMeasurement] bloque les transmissions de cookies durant les instructions POST. (AN-165538)
* Prise en charge de la fonction Déposer pour XDomainRequest. (AN-165733)
* Réduction de la durée de vie par défaut des cookies d’[!DNL AppMeasurement] de cinq à deux ans. (AN-158572)
* Suppression du module média du Gestionnaire de code ([!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Date de publication : **24/05/2018**

> [!NOTE]L’API visiteur version 3.0 ou ultérieure est requise pour les clients utilisant le service ID [!DNL Experience Cloud]. Adobe recommande d’effectuer une mise à niveau vers la dernière version de l’API visiteur à chaque fois que des bibliothèques de code associées sont mises à jour ([!DNL at.js], [!DNL AppMeasurement.js] etc.).

* Mise à jour d’[!DNL AppMeasurement] permettant d’utiliser l’interface Visiteur mise à jour pour demander des identifiants. (AN-151483)
* Correction d’un problème en raison duquel le cookie de suivi des liens continue à s’écrire alors que le suivi des liens est désactivé. (AN-156332)
* Correction d’un problème en raison duquel `registerPreTrackCallback` et `registerPostTrackCallback` interrompent la signature de la fonction de rappel lorsqu’elles sont appelées plusieurs fois. (AN-158566)

## Version 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Date de publication : **12/04/2018**

* Mise à jour d’[!DNL AppMeasurement] permettant d’utiliser l’interface visiteur mise à jour pour demander des identifiants. (AN-151483)
* Le cookie de suivi des liens continue à être écrit une fois que le suivi des liens est désactivé. (AN-156332)
* Réduction de la durée de vie par défaut des cookies d’[!DNL AppMeasurement] de cinq à deux ans. (AN-158572)

## Version 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Date de publication : **29/03/2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

## Version 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Date de publication : **15/03/2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

* Compilation de VAPI v3.1 avec [!DNL AppMeasurement] v2.8. (AN-158353)
* Refactorisation de la création du point de terminaison de la collecte de données afin de faciliter le partage. (AN-156647)
* Ajout des mesures de minutage en boucle des demandes dans [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Date de publication : **18/01/2018**

* Fin de la prise en charge d’IE 6 à 9
* Inclusion de l’API visiteur version 3.0.0
* Inclusion de DIL v7.00

## Version 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Date de publication : **09/11/2017**

Correction d’un problème en raison duquel la bibliothèque [!DNL AppMeasurement] ne définit pas toujours la combinaison de compte correcte lorsque s_gl est appelé. (AN-152153)

## Version 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Date de publication : **21/09/2017**

* Inclusion de [!DNL dil.js 6.12] (module [!DNL Audience Manager])

* Inclusion de l’API visiteur version 2.5.0.

## Version 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Date de publication : **17/08/2017**

* dil.js v6.11 inclus
* API Visiteur 2.4.0 inclus

## Version 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Date de publication : **20/07/2017**

* Correction d’un problème en raison duquel [!DNL s.Util.getQueryParam] capturait #
* Ajout de la version 6.10 du fichier [!DNL dil.js] (AN-145701)

## Version 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Date de publication : **08/06/2017**

* Prise en charge supplémentaire de plusieurs commandes d’instanciation d’[!DNL AppMeasurement]. (AN-138237)
* Inclusion de l’API visiteur version 2.2.0. (AN-144042)

## Version 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Comprend la dernière version de [!DNL dil.js] (AN-140396)
* Ajout de la prise en charge du paramètre `adobe_mc_ref` qui remplace le référent de la page. (AN-131920)
* API Visiteur 2.1.0. de nouveau inclus. (AN-140873)
* Ajout du paramètre `mcorgid`. (AN-139586)
* Paramètre cp (customerPerspective) ajouté. (AN-140897)

## Version 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Date de publication : **09/03/2017**

* Migration vers un nouveau processus de compilation qui nécessite une mise à jour vers la version 2.0.0. (AN-137878)
* Déplacement du traitement de mboxMCSDID à l’emplacement de section correct où est effectué l’appel de suivi. (AN-138483)

## Version 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

Date de publication : **19/01/2017**

* Inclusion de VisitorAPI 2.0.0
* Appels et vérifications de fonctions reséquencés de façon à ce que la consommation du SDID ait lieu une fois la vérification de l’abandon terminée. (AN-134364)
* Les Hooks d’appels avant et après suivi suivants ont été ajoutés. (AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   Ces fonctions acceptent comme paramètres : rappel (fonction) et les paramètres de cette fonction. Par exemple :

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   Le rappel est appelé avec `requestUrl` et les paramètres transmis lorsque le rappel est enregistré. Cela se produit avant ou après l’appel de suivi, selon la méthode utilisée pour enregistrer le rappel. L’ordre dans lequel ces rappels sont appelés n’est pas garanti. Les rappels enregistrés dans la préfonction sont appelés après la création de l’URL de suivi finale. Les post-rappels sont appelés lors d’un appel de suivi réussi (si l’appel de suivi échoue, ces fonctions ne sont pas appelées). Les rappels enregistrés avec `registerPreTrackCallback` n’ont aucun impact sur l’appel de suivi. De plus, l’appel de ces méthodes de suivi dans un rappel enregistré n’est pas recommandé et peut entraîner une boucle sans fin.

## Version 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Mise à jour : **10/11/2016**

* API Visiteur 1.10.1 inclus.

## Version 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Mise à jour : **20/10/2016**

* Mise à jour du module [!DNL Audience Manager] avec la bibliothèque Demdex Integration (DIL) 6.6. (AN-132065)
* Inclusion de l’API visiteur version 1.9.0. (AN-132072)

## Version 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Mise à jour : **15/09/2016**

* Mise à jour du module [!DNL AppMeasurement] [!DNL Audience Manager] avec DIL 6.5 et des configurations supplémentaires (AN-129411)

* Inclusion de l’API visiteur version 1.8.0 (AN-129887)

## Version 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Mise à jour : **18/08/2016**

* Mise à jour d’[!DNL AppMeasurement] afin de pouvoir lire et écrire les cookies AMCV. (AN-127098)
* Inclusion de l’API visiteur version 1.7.0.

> [!NOTE] Voir aussi les notes de mise à jour suivantes relatives à [!DNL JavaScript] version 1.6.3, qui décrivent les exigences à jour du service Experience Cloud ID.

## Version 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Mise à jour : **04/08/2016**

* Correction d’un problème en raison duquel [!DNL AppMeasurement] mettait fin de manière prématurée aux connexions des requêtes. (AN-126448)

>[!IMPORTANT]
>
>La version 1.6.0 du service [!DNL Experience Cloud] ID *exige* [!DNL AppMeasurement] pour [!DNL JavaScript] version 1.6.3 ou supérieure. Pour effectuer la mise à niveau vers la version 1.6.0 du service Experience Cloud ID, veillez à utiliser le code [!DNL AppMeasurement] version 1.6.3 ou supérieure.

## Version 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Date de publication : **21 juillet 2016**

* Inclusion de l’API visiteur version 1.6.0.
* Correction d’un problème en raison duquel [!DNL AppMeasurement] appelait la méthode d’obscurcissement incorrecte dans l’API visiteur. (AN-126006)
* Correction d’un problème provoquant l’erreur [!DNL JavaScript] : « Attribute only valid on v:image » (attribut valide seulement sur v:image). (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa.
</note>

 -->

## Version 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Date de publication : **16 juin 2016**

Inclusion de l’API visiteur version 1.5.7.

## Version 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Date de mise à jour : **19 mai 2016**

[!DNL JavaScript] version 1.5.6

* Inclusion de l’API visiteur version 1.5.6
* Correction de la prise en charge du suivi des clics sur les liens dans Firefox, qui ne couvrait pas l’événement complet.

## Version 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Date de publication : **21 avril 2016**

* The [!DNL AppMeasurement] Activity Map module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. En outre, le suivi d’Activity Map est activé par défaut. (AN-112689)

* Correction d’un problème de troncation lié à l’ordre des variables de chaîne de requête dans [!DNL AppMeasurement], afin que *`pageURLRest`* soit le dernier. (AN-114647)

## Version 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Date de publication : **17 mars 2016**

* Inclusion de l’API visiteur version 1.5.4
* Prise en charge de l’exclusion de l’API visiteur version 1.5.4+

## Version 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Date de publication : **21 janvier 2016**

* Correction de la gestion du module [!DNL Audience Manager] lors de l’utilisation de POST pour les appels de suivi. (AN-115381)
* Déplacement du reste de l’URL de la page ("-g") à la fin de la chaîne de requête de demande de suivi. (AN-114647)

## Version 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Date de publication : **5 novembre 2015**

* Inclusion de l’API visiteur version 1.5.3.
* Correction de la détection d’IE11 pour la troncation des URL 2047 (AN-114914)

## Version 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Date de publication : **17 septembre 2015**

* Inclusion de l’API visiteur version 1.5.2

## Version 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Date de publication : **29 août 2015**

* Inclusion de l’API visiteur version 1.5.1.

## Version 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Date de publication : **16 juillet 2015**

* Mise à jour du module [!DNL Audience Manager] pour pouvoir utiliser les identifiants AAM DIL 6.2 - getCustomer de VisitorAPI.js et les transmettre dans l’appel d’événement à AAM. (AN-104978)

## Version 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Date de publication : **18 juin 2015**

* Prise en charge de l’API visiteur version 1.5 qui utilise la méthode *`getCustomerIDs`* pour rassembler les ID de client et l’état authentifié et envoyer les ID avec les demandes de collecte de données.
* Correction d’un problème lié à la création d’iframe de destination en double dans le module **[!UICONTROL AudienceManagement]** (DIL 6.1).
* Correction du problème connu décrit dans la version 1.4.5.

## Version 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Date de publication : **21 mai 2015**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extension iOS</span> </p> </td> 
   <td colname="col2"> <p> Depuis le SDK <span class="keyword"> iOS </span> version 4.5, une nouvelle extension <span class="keyword"> iOS</span> permet de collecter les données d’utilisation des applications Apple Watch Apps, Today Widgets, des widgets de retouche photo et de toutes les autres applications d’extension <span class="keyword"> iOS </span>. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/ios_ext.html">Mise en œuvre de l’extension iOS </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extension Android Wearable</span> </p> </td> 
   <td colname="col2"> <p> À compter de la version 4.5 du SDK <span class="keyword"> Android </span>, une nouvelle extension <span class="keyword"> Android </span> permet de collecter des données à partir de l’application <span class="keyword"> Android </span> Wearable. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/android_wearable.html">Extension Android Wearable </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusion de l’API visiteur version 1.4.
* Mise à jour du module AudienceManagement afin de permettre l’utilisation de DIL version 6.0.

**Problème connu**

Dans les intégrations API visiteur / module[!DNL AppMeasurement] [!DNL Audience Manager], deux demandes iFrame de publication de destination seront effectuées dans IE6-9 : `//fast.<subdomain>.demdex.net/dest5.html` et `//fast.<subdomain>.demdex.net/dest4.html`. Le comportement correct, comme dans les autres navigateurs, consiste à charger uniquement `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

Date de publication : **16 avril 2015**

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Fonctionnalité </th> 
   <th colname="2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Données personnalisées avec des mesures de cycle de vie </p> </td> 
   <td colname="2"> <p>Vous pouvez maintenant inclure des variables de données contextuelles personnalisées aux mesures de cycle de vie. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Prise en charge du suivi des balises dans <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Correction mineure afin d’effacer l’identifiant de profil d’appel au serveur léger après l’appel de `trackLight`.

## Version 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Date de publication : **19 février 2015**

* Homogénéisation de la gestion de tous les appels de suivi retardés, avec correction des problèmes liés aux variables sauvegardées durant le retard (par exemple l’objet sur lequel on a cliqué).
* Changement en « ne pas procéder au suivi automatique des référents » après le premier appel de suivi de sorte que le 2e, 3e, etc. appel de suivi (généralement le suivi des liens) ne comptabilise pas deux fois le référent quand *`s.referrer`* a été manuellement défini avant le premier appel de suivi.
* Le fichier compressé de distribution a été mis à jour pour inclure l’API visiteur 1.3.5.

## Version 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Date de publication : **15 janvier 2015**

* Correction d’un problème lors de la gestion du prérendu WebKit afin d’empêcher le suivi des pages prérendues qui ne sont pas consultées.
* Le fichier compressé de distribution a été mis à jour afin d’inclure l’API visiteur 1.3.4 et un module **[!UICONTROL AudienceManagement]** mis à jour qui inclut la bibliothèque d’intégration des données (DIL) version 5.5.

## Version 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

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

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_implement.html) implementation for Experience Cloud.

## Version 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Date de publication : **21 août 2014**

* La suppression du suivi des modules externes de navigateur (paramètre de requête `p`) en tant que modules externes n’est plus reportée dans la version 15.
* Ajout du module **[!UICONTROL AudienceManagement]** dans le fichier compressé de téléchargement.

Ajout de la prise en charge des [eVars (76 à 250) et événements (101 à 1000) supplémentaires](https://marketing.adobe.com/resources/help/en_US/sc/implement/evars_events.html).

> [!NOTE] Le code H ne prend pas en charge les eVars et événements supplémentaires.

[!DNL JavaScript]

## Version 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Date de publication : **19 juin 2014**

* Correction de la gestion des indicateurs Terminé et En attente dans les champs d’API de visiteur, par exemple l’identifiant visiteur hérité d’[!DNL Analytics], qui générait des erreurs.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.

## Version 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Date de publication : **22 mai 2014**

* La fonction d’[!DNL AppMeasurement] pour [!DNL JavaScript] `s_gi` ne recherchait pas correctement les instances créées à l’aide du code H `s_gi`. Notez que ce problème avait uniquement une incidence sur certaines implémentations de marquage double dans lesquelles le code [!DNL AppMeasurement] pour [!DNL JavaScript] et le code H figuraient dans une même page avec des instances distinctes et que `s_gi` était utilisé pour rechercher des instances par suite de rapports.

## Version 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Date de publication : **17 avril 2014**

* Prise en charge du service [d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.

## Version 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Date de publication : **13 mars 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Date de publication : **20 février 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Date de publication : **6 février 2014**

* Correction d’un problème de compatibilité avec le module [!DNL Audience Manager] DIL. Les utilisateurs d’[!DNL Audience Manager] doivent également effectuer la mise à jour vers la version 4.8 du module DIL.

## Version 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Date de publication : **15 novembre 2013**

* Correction des événements de page utilisés par la [mesure vidéo Pulsation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Version 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Date de publication : **14 novembre 2013**

* Ajout de la prise en charge de la [mesure Vidéo - Pulsation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] a été ajouté à la prise en charge du [service d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_service#.html).

## Version 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Un appel de suivi de liens ne pouvait pas être envoyé à partir des navigateurs Opera pour les liens commençant par « opera: » (« opera: » est semblable à « about: » et « chrome: » dans d’autres navigateurs).
* Ajout de `alt=""` à tous les objets Image en vue de la conformité avec le « Communications and Video Accessibility Act ».

## Version 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Date de publication : **18 septembre 2013**

* Correction de la prise en charge du positionnement du code de bibliothèque et de page dans la balise `head`.
* Ajout de la prise en charge du module `onLoad` manquante.

## Version 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Date de publication : **15 août 2013**

* Ajout de la prise en charge du déploiement dans la gestion des balises Adobe.
* Correction d’un problème qui empêchait les variables hiérarchiques d’être définies sur l’objet [!DNL AppMeasurement].

## Version 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Date de publication : **18 juillet 2013**

* Le hachage/fragment est désormais ignoré par le suivi automatique des liens. Auparavant, l’URL suivante était automatiquement suivie puisque l’intégralité du contenu entre les balises `href` se terminait par `.pdf` :

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Désormais, le hachage/fragment est ignoré de sorte que le lien est suivi uniquement lorsque le nom de fichier se termine par une extension qui correspond.

## Version 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Date de publication : **23 mai 2013**

Une nouvelle bibliothèque [!DNL JavaScript] [!DNL AppMeasurement] est désormais disponible dans le Gestionnaire de code. Cette bibliothèque fournit les mêmes fonctionnalités de base que le fichier [!DNL s_code.js] ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau.

* 3 à 7 fois plus rapide que le code H.25.
* Décompressée : 21 Ko uniquement ; 8 Ko dans un fichier gzip (code H.25 : 33 Ko décompressé et 13 Ko dans un fichier gzip).
* Prise en charge native pour l’obtention des paramètres de requête, la lecture et l’écriture de cookies et le suivi avancé des liens.
* Suffisamment petite et rapide pour être utilisée sur les sites pour mobiles et suffisamment robuste pour être utilisée sur les sites pour Bureau, ce qui vous permet d’exploiter une seule et même bibliothèque dans tous les environnements web.

Voir [AppMeasurement pour Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html) dans le Guide de mise en œuvre [!DNL Analytics]

> [!NOTE] Certains modules externes ne sont pas pris en charge par cette nouvelle version. Voir [Prise en charge des modules externes](https://marketing.adobe.com/resources/help/en_US/sc/implement/plugins_support.html) pour obtenir des informations détaillées.
