---
description: Notes de mise à jour cumulées pour le code H JavaScript hérité.
seo-description: Notes de mise à jour cumulées pour le code H JavaScript hérité.
seo-title: Code H JavaScript (hérité)
solution: Analytics
subtopic: Notes de mise à jour
title: Code H JavaScript (hérité)
topic: Développeur et mise en œuvre
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Code H JavaScript (hérité){#javascript-h-code-legacy}

Notes de mise à jour cumulées pour le code H JavaScript hérité.

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_about.html).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

Date de publication : **16 juin 2016**

Inclusion de l’API visiteur version 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

Date de mise à jour : **19 mai 2016**

Inclusion de l’API visiteur version 1.5.5.

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

Date de publication : **5 novembre 2015**

* Inclusion de l’API visiteur version 1.5.3.

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

Date de publication : **17 septembre 2015**

* Inclusion de l’API visiteur version 1.5.2.

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

Date de publication : **20 août 2015**

* Inclusion de l’API visiteur version 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

Date de publication : **18 juin 2015**

* Inclusion de l’API visiteur version 1.5.

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

Date de mise à jour : **21 mai 2015**

* Inclusion de l’API visiteur version 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

Date de publication : **16 avril 2015**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Date de publication : **19 février 2015**

* Inclusion de l’API visiteur version 1.3.5.
* Changement en « ne pas procéder au suivi automatique des référents » après le premier appel de suivi de sorte que le 2e, 3e, etc. appel de suivi (généralement le suivi des liens) ne comptabilise pas deux fois le référent quand *`s.referrer`* a été manuellement défini avant le premier appel de suivi. (AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

Date de publication : **15 janvier 2015**

* Le fichier compressé de distribution a été mis à jour pour inclure l’API visiteur 1.3.4.

Date de publication : **18 septembre 2014**

* Ajout d’une variable `tagContainerMarker` qui permet à la mise en œuvre de spécifier jusqu’à 4 caractères annexés à la chaîne de version avec un délimiteur de caractère (tiret) supplémentaire. Ceci est utilisé par la gestion dynamique des balises.

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

Date de publication : **21 août 2014**

* Changements internes pour la prise en charge des fonctions à venir.

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Date de publication : **19 juin 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Prise en charge de nouvelles fonctionnalités du service d’identification des visiteurs version 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Date de publication : **11 juin 2014**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Date de publication : **22 mai 2014**

* Prise en charge du service [d’identification des visiteurs](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.
* Prise en charge de l’[intégration de Target à Analytics](https://marketing.adobe.com/resources/help/en_US/target/a4t/).

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Date de publication : **17 octobre 2013**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Date de publication : **18 juillet 2013**

* Le hachage/fragment est désormais ignoré par le suivi automatique des liens. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

Désormais, le hachage/fragment est ignoré de sorte que le lien est suivi uniquement lorsque le nom de fichier se termine par une extension qui correspond.

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Date de publication : **29 avril 2013**

* L’indicateur `useForcedLinkTracking` décrit dans la section [Suivi manuel de liens en utilisant le code de lien personnalisé](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_manuallinktrackcustomlink.html) s’applique désormais à Firefox 20+ (il ne s’appliquait auparavant qu’aux navigateurs WebKit).

* La génération d’ID d’objet image est désormais unique entre instances. Cela empêche les collisions lorsque plusieurs instances figurent dans une même page.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Date de publication : **19 avril 2013**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

* Dans le suivi automatique des vidéos sur Media Player, correction d’un problème de défilement en raison duquel la durée de lecture n’était pas correctement suivie.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Date de publication : **février 2013**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* Étendue améliorée des événements de clic affectée par `useForcedLinkTracking`. Le suivi forcé automatique des liens s’applique uniquement dans les conditions suivantes :

   * `<A>` et `<AREA>` balises

   * La balise doit avoir un attribut `HREF`.
   * The `HREF` can't start with `#`, `about:`, or `javascript:`

   * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Date de publication : **janvier 2013**

* Prise en charge de l’envoi d’URL de plus de 255 octets pour gérer l’extension du champ URL de page dans les serveurs de collecte de données Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Ceci permet d’éviter que les longues URL ne prévalent sur d’autres données en cas de troncation de navigateur, tout en permettant la saisie de longues URL.

* Correction de la gestion du décodage des URL pour les chaînes codées à la fois avec les composants `escape` et `encodeURIComponent`.

* Correction d’un problème des navigateurs WebKit, en raison duquel le suivi des liens échouait si le premier appel au serveur sur les pages expirait.
* Ajout d’une nouvelle méthode d’identification des visiteurs de secours. Voir [Identification des visiteurs uniques](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Ajout d’un nouvel indicateur `abort` qui peut être défini dans `doPlugins`. Si ce paramètre est défini sur vrai, la bibliothèque [!DNL AppMeasurement] ne poursuit pas cet appel de suivi. L’indicateur abort est réinitialisé à chaque appel de suivi, de sorte que si un appel de suivi consécutif doit également être abandonné, l’indicateur devra être redéfini dans `doPlugins`.

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

Ceci vous permet de centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Date de publication : **octobre 2012**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. Auparavant, cette version était limitée à 2 caractères (par exemple, 1.8). Un troisième caractère est désormais pris en charge (par exemple, 1.8.5).
* Correction d’un problème avec [!DNL Tag Manager], qui empêchait l’envoi des valeurs répétées dans les blocs dépendant du code.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

Date de publication : **septembre 2012**

* Codage forcé des URL pour les caractères suivants :

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* Correction d’un problème en raison duquel l’événement vidéo terminé n’était parfois pas envoyé lors de l’utilisation d’une méthode `media.monitor` personnalisée qui contrôle l’événement de fermeture multimédia :

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Date de publication : **juillet 2012**

Mise à jour permettant de garantir un suivi des liens correct dans les navigateurs WebKit (Safari et Chrome). Après cette mise à jour, le suivi automatique des liens de téléchargement et de sortie (déterminé par `s.trackDownloadLinks` et `s.trackExternalLinks`) est correct. If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

Par exemple, les liens de sortie et de téléchargement sont souvent suivis à l’aide d’un code similaire à ce qui suit :

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox et Internet Explorer exécutent l’appel de suivi des liens et ouvrent la nouvelle page. En revanche, les navigateurs WebKit peuvent annuler l’exécution de l’appel à l’ouverture de la nouvelle page. Pour cette raison, les appels de suivi des liens échouent parfois lors de l’utilisation des navigateurs WebKit.

Afin de pallier ce comportement, H.25 comprend une méthode de suivi de liens surchargée (`s.tl`) qui oblige les navigateurs WebKit à attendre que l’appel de suivi des liens soit terminé. Cette nouvelle méthode exécute l’appel de suivi des liens, puis gère l’événement de navigation, plutôt que d’utiliser l’action par défaut du navigateur. Cette méthode surchargée nécessite qu’un autre paramètre, appelé `doneAction`, précise l’action à entreprendre lors de l’appel de suivi des liens.

Pour utiliser cette nouvelle méthode, les appels doivent être modifiés en `s.tl` avec un autre paramètre `doneAction`, semblable à ce qui suit :

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Le transfert de 'navigate' comme `doneAction` reflète le comportement par défaut du navigateur et ouvre l’URL spécifiée par l’attribut `href` lors de l’exécution de l’appel de suivi des liens.

Le tableau ci-dessous répertorie les variables de configuration et les mises à jour effectuées dans la version H.25 pour la prise en charge de ces fonctionnalités.

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variable </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>Cet indicateur est utilisé pour désactiver le suivi des liens forcé pour les navigateurs WebKit. Le suivi des liens forcé est activé par défaut pour les navigateurs WebKit et est ignoré par les autres navigateurs. </p> <p> <b>Valeur par défaut</b> </p> <p> <code> true </code> </p> <p> <b>Exemple</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>Nombre maximal de millisecondes d’attente pour la fin du suivi avant d’exécuter <code>doneAction</code> transmis dans <code>s.tl </code>. Cette valeur spécifie la durée d’attente maximale. Si l’appel de suivi des liens est effectué avant ce délai d’expiration, <code>doneAction</code> est exécuté immédiatement. Si vous remarquez que les appels de suivi de liens ne sont pas effectués, vous devez augmenter ce délai d’expiration. </p> <p> <b>Valeur par défaut</b> </p> <p>250 </p> <p> <b>Exemple</b> </p> 
    <code class="syntax javascript">
      s.mandatoryLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink (<code>s.tl </code>) </td> 
   <td colname="col2"> <p>Effectue le suivi des liens personnalisés, de téléchargement et de sortie. Fournit un paramètre facultatif pour spécifier une action de navigation à exécuter une fois l’appel de suivi des liens effectué sur les navigateurs WebKit. </p> <p> <b>Syntaxe</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) </code> <p> <b>doneAction</b> : (facultatif) spécifie l’action à exécuter une fois que l’appel de suivi des liens est envoyé ou a expiré (selon la valeur spécifiée par <code>s.forcedLinkTrackingTimeout </code>). <code>doneAction</code> peut être la chaîne 'navigate', ce qui entraîne la méthode à définir <code>document.location</code> sur l’attribut <code>href</code> de <code>linkObject </code>. <code>doneAction</code> peut être également une fonction permettant une personnalisation avancée. </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>Exemples</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; </code> <code class="syntax javascript">&lt;a&amp;nbsp;href="#"&amp;nbsp;nbsp click="s.tl(this,'o','MyLink',null,function(){if(verify('Continuer?')))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Date de publication : **avril 2012**

Cette mise à jour est recommandée pour tous les utilisateurs.

* Amélioration afin de détecter si une page est prérendue à l’aide de la fonction de prérendu de Google Chrome ([https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. The [!DNL JavaScript] library now waits until the user visits your site before sending server calls for these prerendered pages.
* Ajout de la variable `timestamp`[!DNL JavaScript] à la bibliothèque pour les clients qui souhaitent personnaliser les données d’horodatage comme dans les autres bibliothèques [!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Date de publication : **février 2012**

* Correction d’un problème qui empêchait l’inclusion de données supplémentaires dans la demande d’image pour les utilisateurs utilisant les substitutions `Object.prototype` Javascript. L’utilisation d’`Object.prototype` est maintenant ignorée lors de la manipulation de variables de données contextuelles.
* Correction d’un problème en raison duquel le paramètre de requête `pe` était transmis deux fois avec la même valeur dans certaines circonstances.
* Correction du suivi [!DNL ClickMap][!DNL JavaScript] dans pour ignorer les clics sur la balise body, même si la balise a un gestionnaire d’événement `onClick`.
* Ajout d’un horodatage aux variables utilisées avec les appels de suivi légers ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Date de publication : **janvier 2012**

* Mise à jour du suivi vidéo avec une nouvelle méthode permettant le suivi des affichages complets de vidéos.
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* Correction d’un bogue en raison duquel les variables de données contextuelles n’étaient pas incluses dans les appels au serveur de liaisons, même si elles étaient référencées dans `linkTrackVars`. Les variables de données contextuelles sont utilisées avec les règles de traitement.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Date de publication : **novembre 2011**

* Mise à jour du suivi vidéo afin de combiner les accès enregistrés simultanément pour les segments et les jalons.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Date de publication : **novembre 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Date de publication : **novembre 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Date de version : **octobre 2011**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. Ces paramètres s’appliquent désormais pour les liens de sortie automatique, afin que les variables prop, eVar et event ne soient pas envoyées avec la demande d’image du lien de sortie.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Date de publication : **septembre 2011**

* Suppression des attributs de bordure des balises d’image sur les périphériques mobiles pour être conforme aux normes WML. Cette modification permet de résoudre les problèmes de rendu sur certains périphériques mobiles.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Date de publication : **août 2011**

Correction de la précision des mesures de pourcentage dans le suivi vidéo.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Date de publication : **juillet 2011**

* Ajout de la prise en charge de la [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Date de publication : **juin 2011**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* Les chaînes référentes de plus de 255 caractères sont désormais tronquées en raccourcissant le chemin au lieu de la chaîne de requête. Cela résout les problèmes liés à la troncation et à la non-collecte des paramètres de chaîne de requête.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Date de publication : **mai 2011**

* Correction d’un problème qui empêchait l’envoi de la variable de suivi vidéo (pev3).
* Résolution d’un problème qui empêchait l’appel `s_gi` de permettre au code d’être compatible avec le code G et H. Lorsque vous transmettez la valeur 1 comme second paramètre à cet appel, le code est désormais configuré pour être compatible avec les deux versions.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Date de publication : **avril 2011**

* Prise en charge des données contextuelles qui pilotent les règles de traitement côté serveur (v15 uniquement).
* Prise en charge des appels de serveur léger (v15 uniquement).
* Prise en charge de l’affectation d’une valeur autre que 1 pour un compteur d’événement dans la liste des événements.
* Prise en charge d’une nouvelle méthode de suivi vidéo utilisant les eVars et événements de conversion (bêta).
* Suppression de la prise en charge de la définition de Media.trackWhilePlaying sur la valeur false. La valeur sera toujours true.
* Ajout de l’indicateur debugTracking pour activer la journalisation des requêtes envoyées à la console Firebug tout comme dans les autres plateformes.
* Veillez à ce que "+" soit toujours codé dans l’URL, indépendamment du navigateur.
