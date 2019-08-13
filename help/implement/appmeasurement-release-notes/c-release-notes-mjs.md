---
description: Notes de mise à jour cumulées pour AppMeasurement pour JavaScript.
seo-description: Notes de mise à jour cumulées pour AppMeasurement pour JavaScript.
seo-title: AppMeasurement pour JavaScript
solution: Analytics
subtopic: Notes de mise à jour
title: AppMeasurement pour JavaScript
topic: Développeur et mise en œuvre
uuid: 1440013 d-d 266-4 dce -9807-8 b 9 adac 73315
translation-type: tm+mt
source-git-commit: 0143edbcbab3450f6932367f51e9e4c79bc1ae63

---


# AppMeasurement pour JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## Version 2.16.0

Date de publication : **15 août 2019**

| Fonctionnalité | Description |
| -----------| ---------- |
| Prise en charge `sendBeacon` des liens de sortie | Mise en œuvre de la prise en charge `sendBeacon` des liens de sortie dans [!UICONTROL AppMeasurement]. Cela permettra d’améliorer le suivi des liens de sortie et entraînera probablement par une augmentation du trafic. `SendBeacon` ne s'exécute pas dans le contexte d'une page, mais dans le contexte du navigateur. En d'autres termes, si une page est chargée, `sendBeacon`la demande est toujours terminée. Cela s'avère très utile pour les liens de sortie, car il sera beaucoup plus probable que la demande de lien de sortie soit terminée. |
| Valeurs ECID/fid | Les valeurs ECID/fid sont maintenant mises en cache au premier accès, même si les paramètres OptIn changent. |
| DIL 9.3 | Mise à jour du module Gestion de l’audience vers DIL 9.3 |
| Suivi de la portée de défilement | Bouton exposé dans s.ActivityMap.trackScrollReach permettant d’activer ou de désactiver le suivi de la portée de défilement. |
| Service d’identification des visiteurs 4.4.0 | Mise à niveau d’AppMeasurement pour utiliser le service d’identification des visiteurs 4.4.0. |

## Version 2.15.0

Date de publication : **15 juillet 2019**

* Suivi d'une portée de défilement activitymap ajouté à l'extension de Carte d'activités (AN -172949)
* Ajout de DIL 9.2 à appmeasurement (AN -182472)

## Version 2.14.0

Date de publication : **21 mai 2019**

* Correction de problèmes liés à la gestion de l’état des paramètres de suivi lorsque plusieurs accès sont en attente. (AN-176931, AN-176629, DTM-12758)
* Mise à jour d’AppMeasurement pour inclure Visitor.js 4.3.0 (AN-180049)

## Version 2.13.0

Date de publication : **10 avril 2019**

Correction de nombreux problèmes signalés avec clearvars. Le problème survient lorsque des accès sont envoyés avant que le suivi ne soit prêt. Lorsque le suivi est prêt, la bibliothèque peut définir des variables qui ont déjà été effacées ou modifiées. (AN-176931, AN-176629, DTM-12758).

## Version 2.12.0

Release Date: **02/22/2019**

* Mise à jour du module Gestion de l’audience vers DIL 9.1. (AN-175255)
* La stratégie de sécurité GTM n’autorise pas le module Activity Map. (AN-174679)
* Amélioration de appmeasurement pour qu'il respecte l'exclusion lorsque le service d'identité n'est pas approuvé dans la souscription. (AN-175259)

## Version 2.11.0

Release Date: **02/11/2019**

* Ajout de la prise en charge des nouveaux services de souscription Adobe dans AppMeasurement. (AN-163546)
* Ajout de la prise en charge du stockage des données de suivi des liens pour le stockage de session. (AN-162272)
* Ajout de la prise en charge du type de flux multimédia pour Audio Analytics. (AN-173265)

## Version 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] bloque les transmissions de cookies durant les instructions POST. (AN-165538)
* Prise en charge de la fonction Déposer pour XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Date de publication : **24/05/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe recommande d’effectuer une mise à niveau vers la dernière version de l’API visiteur à chaque fois que des bibliothèques de code associées sont mises à jour ([!DNL at.js], etc.).[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* Correction d’un problème en raison duquel le cookie de suivi des liens continue à s’écrire alors que le suivi des liens est désactivé. (AN-156332)
* Correction d’un problème en raison duquel `registerPreTrackCallback` et `registerPostTrackCallback` interrompent la signature de la fonction de rappel lorsqu’elles sont appelées plusieurs fois. (AN-158566)

## Version 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Date de publication : **12/04/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* Le cookie de suivi des liens continue à être écrit une fois que le suivi des liens est désactivé. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Version 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Date de publication : **29/03/2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

## Version 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Date de publication : **15/03/2018**

Recompilation de l’API visiteur 3.1.0 (AN-159524) avec les correctifs suivants : (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* Refactorisation de la création du point de terminaison de la collecte de données afin de faciliter le partage. (AN-156647)
* Ajout des mesures de minutage en boucle des demandes dans [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Date de publication : **18/01/2018**

* Fin de la prise en charge d’IE 6 à 9
* Inclusion de l’API visiteur version 3.0.0
* Inclusion de DIL v7.00

## Version 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Date de publication : **09/11/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Version 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Date de publication : **21/09/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* Inclusion de l’API visiteur version 2.5.0.

## Version 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Date de publication : **17/08/2017**

* dil.js v6.11 inclus
* API Visiteur 2.4.0 inclus

## Version 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Date de publication : **20/07/2017**

* Correction d’un problème en raison duquel [!DNL s.Util.getQueryParam] capturait #
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Version 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Date de publication : **08/06/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusion de l’API visiteur version 2.2.0. (AN-144042)

## Version 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Comprend la dernière version de [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* API Visiteur 2.1.0. de nouveau inclus. (AN-140873)
* Ajout `mcorgid` du paramètre. (AN-139586)
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

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusion de l’API visiteur version 1.9.0. (AN-132072)

## Version 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Mise à jour : **15/09/2016**

* Mise à jour [!DNL AppMeasurement][!DNL Audience Manager] du module avec DIL 6.5 et des configurations supplémentaires (AN -129411)

* Inclusion de l’API visiteur version 1.8.0 (AN-129887)

## Version 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Mise à jour : **18/08/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusion de l’API visiteur version 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Version 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Mise à jour : **04/08/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Version 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Date de publication : **21 juillet 2016**

* Inclusion de l’API visiteur version 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

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

[!DNL JavaScript] version 1.5.6

* Inclusion de l’API visiteur version 1.5.6
* Correction de la prise en charge du suivi des clics publicitaires dans Firefox, qui ne couvrait pas l’événement complet.

## Version 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Date de publication : **21 avril 2016**

* The [!DNL AppMeasurement] [!DNL Activity Map] module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. De plus [!DNL Activity Map] , le suivi est activé par défaut. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Version 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Date de publication : **17 mars 2016**

* Inclusion de l’API visiteur version 1.5.4
* Prise en charge de l’exclusion de l’API visiteur version 1.5.4+

## Version 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Date de publication : **21 janvier 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* Déplacement du reste de l’URL de la page ("-g") à la fin de la chaîne de requête de demande de suivi. (AN-114647)

## Version 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Date de publication : **5 novembre 2015**

* Inclusion de l’API visiteur version 1.5.3.
* Correction de la détection d’IE11 pour la troncation des URL 2047 (AN-114914)

## Version 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Date de publication : **17 septembre 2015**

* Inclusion de l’API visiteur version 1.5.2.

## Version 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Date de publication : **29 août 2015**

* Inclusion de l’API visiteur version 1.5.1.

## Version 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Date de publication : **16 juillet 2015**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## Version 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Date de publication : **18 juin 2015**

* Prise en charge de l’API visiteur version 1.5 qui utilise la méthode *`getCustomerIDs`* pour rassembler les ID de client et l’état authentifié et envoyer les ID avec les demandes de collecte de données.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Correction du problème connu décrit dans la version 1.4.5.

## Version 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Date de mise à jour : **21 mai 2015**

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
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external">Mise en œuvre de l’extension iOS </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Extension Android Wearable</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external">Extension Android Wearable </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusion de l’API visiteur version 1.4.
* Mise à jour du module AudienceManagement afin de permettre l’utilisation de DIL version 6.0.

**Problème connu**

Dans les intégrations API/ [!DNL AppMeasurement][!DNL Audience Manager] module visiteur, il existe deux demandes d'iframe de publication de destination effectuées dans IE 6-9 : `//fast.<subdomain>.demdex.net/dest5.html` et `//fast.<subdomain>.demdex.net/dest4.html`. Le comportement correct, comme dans les autres navigateurs, consiste à charger uniquement `//fast.<subdomain>.demdex.net/dest5.html`.

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
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>Les appels <code>trackBeacon</code> et <code>clearCurrentBeacon</code><span class="keyword"> sont maintenant disponibles dans PhoneGap </span>. </p> </td> 
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
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

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
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## Version 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Date de publication : **21 août 2014**

* La suppression du suivi des modules externes de navigateur (paramètre de requête `p`) en tant que modules externes n’est plus reportée dans la version 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Ajout de la prise en charge des [eVars (76 à 250) et événements (101 à 1000) supplémentaires](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events).

>[!NOTE]
>
>Le code H ne prend pas en charge les evars et événements supplémentaires.

[!DNL JavaScript]

## Version 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Date de publication : **19 juin 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.

## Version 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Date de publication : **22 mai 2014**

* [!DNL AppMeasurement] pour [!DNL JavaScript]`s_gi` la fonction ne recherchait pas correctement les instances créées à l'aide du code `s_gi`H. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Version 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Date de publication : **17 avril 2014**

* Prise en charge du [service d’identification des visiteurs de Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Version 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Date de publication : **13 mars 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Date de publication : **20 février 2014**

* Correctifs de bogues pour la vidéo Pulsation.

## Version 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Date de publication : **6 février 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] Les clients doivent également effectuer la mise à jour vers la version 4.8 du module DIL.

## Version 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Date de publication : **15 novembre 2013**

* Correction des événements de page utilisés par la [mesure vidéo Pulsation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Version 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Date de publication : **14 novembre 2013**

* Ajout de la prise en charge de la [mesure Vidéo - Pulsation](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] a été ajouté à la prise en charge du [service d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Version 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Un appel de suivi de liens ne pouvait pas être envoyé à partir des navigateurs Opera pour les liens commençant par « opera: » (« opera: » est semblable à « about: » et « chrome: » dans d’autres navigateurs).
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Version 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Date de publication : **18 septembre 2013**

* Correction de la prise en charge du positionnement du code de bibliothèque et de page dans la balise `head`.
* Added missing module `onLoad` support.

## Version 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Date de publication : **15 août 2013**

* Ajout de la prise en charge du déploiement dans la gestion des balises Adobe.
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Version 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Date de publication : **18 juillet 2013**

* Le hachage/fragment est désormais ignoré par le suivi automatique des liens. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Désormais, le hachage/fragment est ignoré de sorte que le lien est suivi uniquement lorsque le nom de fichier se termine par une extension qui correspond.

## Version 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Date de publication : **23 mai 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. Cette bibliothèque fournit les mêmes fonctionnalités de base que le fichier [!DNL s_code.js] ; elle est toutefois plus légère et plus rapide sur les sites pour mobiles comme sur les sites pour Bureau.

* 3 à 7 fois plus rapide que le code H.25.
* Décompressée : 21 K uniquement ; 8 K dans un fichier gzip (code H.25 : 33 K décompressé et 13 K dans un fichier gzip).
* Prise en charge native pour l’obtention des paramètres de requête, la lecture et l’écriture de cookies et le suivi avancé des liens.
* Suffisamment petite et rapide pour être utilisée sur les sites pour mobiles et suffisamment robuste pour être utilisée sur les sites pour Bureau, ce qui vous permet d’exploiter une seule et même bibliothèque dans tous les environnements web.

Voir [AppMeasurement pour Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) dans le Guide de mise en œuvre [!DNL Analytics]

>[!NOTE]
>
>Certains plug-ins ne sont pas pris en charge dans cette nouvelle version. Voir [Prise en charge des modules externes](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) pour obtenir des informations détaillées.
