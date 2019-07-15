---
description: Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript.
keywords: Mise en œuvre d’Analytics
seo-description: Il est possible d’effectuer le suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres définis dans le fichier AppMeasurement pour JavaScript.
seo-title: Fonction s.tl() – Suivi des liens
solution: Analytics
subtopic: Suivi des liens
title: Fonction s.tl() – Suivi des liens
topic: Développeur et mise en œuvre
uuid: f 28 f 071 a -8820-4 f 74-89 cd-fd 2333 a 21 f 22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# Fonction s.tl() – Suivi des liens

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## Fonction s.tl() – Suivi des liens {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

Si nécessaire, il est possible de suivre manuellement ces types de liens en utilisant un code de lien personnalisé comme indiqué ci-dessous. En outre, le code de lien personnalisé peut servir à suivre les liens personnalisés génériques utilisés pour divers besoins de suivi et de création de rapports.

## Référence du paramètre s.tl() {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

Le premier argument doit toujours être défini sur « this » (par défaut) ou sur « true ». L’argument fait référence à l’objet sur lequel l’utilisateur clique ; lorsqu’il est défini sur « this », il fait référence à la propriété HREF du lien.

Si vous implémentez le suivi des liens sur un objet qui n&#39;a pas de propriété HREF, vous devez toujours définir cet argument sur « this.  » »

Puisque le fait de cliquer sur un lien conduit souvent un visiteur hors de la page active, un délai de 500 ms permet de garantir que la demande d’image est envoyée à Adobe avant que ceci ne se produise. Ce délai n’est nécessaire que lors de la sortie de la page, mais il est généralement présent lors de l’appel de la fonction s.tl(). Si vous souhaitez désactiver le délai, transmettez le mot-clé « true » comme premier paramètre lors de l’appel de la fonction s.tl().

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

Trois valeurs sont possibles pour linkType, suivant le type de lien que vous souhaitez capturer. S’il ne s’agit ni d’un lien de téléchargement, ni d’un lien de sortie, vous devez choisir l’option Liens personnalisés.

| Type | Valeur de linkType |
|--- |--- |
| Téléchargements de fichiers | &#39;d&#39; |
| Liens de sortie | &#39;e&#39; |
| Liens personnalisés | &#39;o&#39; |

**linkName**

Pour cette variable, vous pouvez utiliser toute valeur personnalisée d’une taille maximale de 100 caractères. Cela a pour effet de déterminer le mode d’affichage du lien dans le rapport approprié.

**variableOverrides**

(Variable facultative, transmettez la valeur « null » si vous ne l’utilisez pas) Permet de modifier les valeurs de variable pour cet appel unique. Semblable à d’autres bibliothèques [!DNL AppMeasurement].

**useForcedLinkTracking**

Cet indicateur est utilisé pour désactiver le suivi des liens forcé pour certains navigateurs. Ce type de suivi est activé par défaut pour les navigateurs FireFox 20+ et WebKit.

Valeur par défaut = true

Exemple: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

Nombre maximal de millisecondes d’attente pour la fin du suivi avant d’exécuter doneAction transmis dans `s.tl`. Cette valeur spécifie la durée d’attente maximale. Si l’appel de suivi de liens se termine avant l’expiration de ce délai, doneAction est exécuté immédiatement. Vous devrez peut-être allonger ce délai si vous constatez que les appels de lien de suivi ne s’exécutent pas.

Valeur par défaut = 250

Exemple: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

Paramètre facultatif destiné à spécifier une action de navigation à exécuter à l’issue d’un appel de lien de suivi lorsque useForcedLinkTracking est activé.

Syntaxe :

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

 doneAction : (facultatif) indique l’action à effectuer après l’envoi ou l’expiration de l’appel de suivi de lien, en fonction de la valeur spécifiée par :

`s.forcedLinkTrackingTimeout`

La variable doneAction peut être la chaîne « navigate », auquel cas la méthode définit `document.location` sur l’attribut href de linkObject . La variable doneAction peut également être une fonction qui autorise une personnalisation avancée.

Si une valeur est fournie pour doneAction dans un événement onClick d’ancrage, vous devez renvoyer « false » après l’appel `s.tl` pour empêcher la navigation par défaut.

Pour reproduire le comportement par défaut et suivre l’URL spécifiée par l’attribut href, indiquez une chaîne « navigate » en tant que doneAction .

Vous pouvez éventuellement fournir votre propre fonction pour gérer l’événement de navigation en la transmettant en tant que doneAction .

Exemples :

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**Exemple**

Dans l’exemple ci-dessous, l’appel de fonction [!UICONTROL s.tl()] utilise un délai de 500 ms par défaut pour s’assurer que les données sont collectées avant que l’utilisateur ne quitte la page.

```js
s.tl(this,'o','link name');
```

L’exemple suivant désactive le délai de 500 ms si l’utilisateur ne quitte pas la page ou lorsque l’objet sur lequel il clique est dépourvu d’attribut HREF.

```js
s.tl(true,'o','link name');
```

Le délai de 500 ms est un délai maximum. Si l’image demandée est renvoyée en moins de 500 ms, le délai cesse immédiatement de courir. Cela permet au visiteur de passer à la page ou à l’action suivante sur la page.

Les exemples suivants concernent la gestion des liens personnalisés sur des navigateurs WebKit :

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>Les utilisations du code de lien personnalisé sont souvent très spécifiques à votre site Web et à vos besoins de création de rapports. Vous pouvez contacter votre conseiller Adobe ou le service à la clientèle avant d’implémenter un code de lien personnalisé afin de comprendre les possibilités dont vous disposez et de savoir comment exploiter au mieux cette fonctionnalité en fonction des besoins de votre entreprise.

Le code de base pour suivre un lien à l’aide du code de lien personnalisé est illustré dans l’exemple suivant :

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>The [!UICONTROL s_gi] function must contain your report suite ID as a function parameter. Veillez à remplacer [!DNL rsid] par l’ID unique de votre suite de rapports.

>[!NOTE]
>
>Si le paramètre du nom de lien n&#39;est pas défini, l&#39;URL du lien (déterminé à partir de l&#39;objet « this ») est utilisée comme nom de lien.

Les variables [!DNL Analytics] peuvent être définies comme une partie du code de lien personnalisé.

## Suivi automatique des liens de sortie et des téléchargements de fichiers {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

Il est possible de configurer le fichier JavaScript pour un suivi automatique des téléchargements de fichiers et des liens de sortie en fonction des paramètres qui définissent les types des fichiers téléchargés et les liens de sortie.

<!-- 

link_automatic.xml

 -->

Les paramètres de contrôle du suivi automatique sont les suivants :

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Les paramètres *`trackDownloadLinks`* et *`trackExternalLinks`* déterminer si le suivi automatique des téléchargements de fichiers et des liens de sortie est activé. When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

Avec les paramètres suivants, l’exemple ci-dessous sera compté comme un lien de sortie :

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## Exemple 3 {#section_2A78D05162D640169844A7D1E9799BAA}

Avec les paramètres suivants, le lien ci-dessous n’est pas comptabilisé comme un lien de sortie :

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>Un lien unique peut uniquement être suivi comme téléchargement de fichier ou lien de sortie, avec le téléchargement de fichier prioritaire. If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. Le tableau ci-après synthétise le suivi automatique des téléchargements de fichiers et des liens de sortie.

## Suivi manuel des liens en utilisant le code de lien personnalisé {#concept_7113B5D037BE4622B6934554C6D18F96}

Le code de lien personnalisé permet le suivi des téléchargements de fichiers, des liens de sortie et des liens personnalisés dans les cas où le suivi automatique n’est ni suffisant, ni applicable.

<!-- 

link_manual.xml

 -->

Le code de lien personnalisé est généralement implémenté en ajoutant un gestionnaire d’événements [!UICONTROL onClick] à un lien ou en ajoutant du code à une routine existante. Il peut être implémenté à partir de n’importe quel gestionnaire d’événements ou fonction JavaScript.

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. Cette fonction, [!UICONTROL s.tl()], est soit appelée directement dans un gestionnaire d’événements, tel que [!UICONTROL onClick] ou [!UICONTROL onChange], soit à partir d’une fonction distincte. Cette fonction [!UICONTROL s.tl()] comprend cinq arguments. Les trois premiers sont obligatoires :

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## Suivi des liens personnalisés sur des navigateurs FireFox et WebKit {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 comprend une mise à jour pour s’assurer que le suivi des liens s’effectue correctement sur des navigateurs WebKit (Safari et Chrome). JavaScript H.26 comprend une mise à jour pour s’assurer que le suivi des liens s’effectue correctement sur FireFox 20+.

Après cette mise à jour, le suivi automatique des liens de téléchargement et de sortie (déterminé par [!DNL s.trackDownloadLinks] et [!DNL s.trackExternalLinks]) est correct. Si vous effectuez un suivi des liens personnalisés à l’aide d’appels JavaScript manuels, vous devez modifier la façon dont ces appels ont lieu. Par exemple, les liens de sortie et de téléchargement sont souvent suivis à l’aide d’un code similaire à ce qui suit :

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer exécute l’appel de lien de suivi et ouvre la nouvelle page. Il se peut que d’autres navigateurs annulent l’exécution de cet appel lors de l’ouverture de la nouvelle page. Cela empêche souvent l’exécution des appels de lien de suivi.

Pour éviter cela, H.25 (publié en juillet 2012) comprend une méthode de lien de suivi en surcharge ( [!DNL s.tl])  ) qui force les navigateurs ayant ce comportement à attendre la fin de l’exécution de l’appel. Cette nouvelle méthode exécute l’appel et traite l’événement de navigation, au lieu d’utiliser l’opération par défaut du navigateur. Cette méthode surchargée nécessite qu’un autre paramètre, appelé [!UICONTROL doneAction], précise l’action à entreprendre lors de l’appel de suivi des liens.

Pour utiliser cette nouvelle méthode, les appels doivent être modifiés en [!DNL s.tl] avec un autre paramètre [!UICONTROL doneAction], semblable à ce qui suit :

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

La transmission de la chaîne « navigate » comme paramètre [!UICONTROL doneAction] reproduit le comportement par défaut du navigateur et ouvre l’URL indiquée par l’attribut href à la fin de l’appel de suivi.

Dans JavaScript H.25.4 (publié en février 2013), les limites de portée ci-après ont été ajoutées aux liens suivis lorsque `useForcedLinkTracking` est activé. Le suivi forcé automatique des liens s’applique uniquement dans les conditions suivantes :

* `<A>` et `<AREA>` des balises.
* La balise doit avoir un attribut `HREF`.
* The `HREF` can&#39;t start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## Suivi des liens à l’aide d’une demande d’image {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

Le suivi des liens peut s’effectuer sans appeler la fonction s.tl(). Pour ce faire, il convient de construire une demande d’image.

<!-- 

link_img.xml

 -->

Les demandes d’image sont codées en dur en ajoutant le paramètre « pe » au paramètre src, comme illustré ci-dessous :

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = téléchargement
* lnk_e = sortie
* lnk_o = personnalisé

En outre, une URL de lien peut être spécifiée en transmettant l’URL dans le paramètre pev1 :

```
pev1=mylink.com
```

Un nom de lien peut être spécifié en transmettant le nom dans le paramètre pev2 :

```
pev2=My%20Link
```

Par exemple :

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## Définition d’autres variables pour les téléchargements de fichiers, les liens de sortie et les liens personnalisés {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

Ils sont, par défaut, définis dans le fichier JS de la manière suivante :

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

Le paramètre *`linkTrackVars`*doit inclure chaque variable dont vous souhaitez effectuer le suivi avec chaque téléchargement de fichier, lien de sortie et lien personnalisé. The *`linkTrackEvents`* parameter should include each event you want to track with every file download, exit link, and custom link. Lorsque l’un de ces types de liens se présente, la valeur actuelle de chaque variable identifiée est suivie.

Par exemple, pour suivre « prop1 », « eVar1 » et « event1 » avec chaque téléchargement de fichier, lien de sortie et lien personnalisé, utilisez les paramètres suivants dans le fichier JS global :

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. Il est probable que cela « gonfle » par erreur le nombre d’instances de chaque variable ; un phénomène qui doit donc être évité.

## Bonnes pratiques {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. Les instances de chaque variable et de chaque événement peuvent être gonflées dans les situations où la variable (ou l’événement) s’applique à la page active, mais pas au téléchargement de fichier, lien de sortie ou lien personnalisé spécifique.

Pour garantir que les variables appropriées sont définies avec le code de lien personnalisé, Adobe conseille de définir *`linkTrackVars`* et *`linkTrackEvents`* dans le code de lien personnalisé, comme suit :

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>Dans l&#39;exemple ci-dessus, la valeur de prop 1 est définie dans le code de lien personnalisé lui-même. La valeur de prop2 provient de la valeur actuelle de la variable, telle qu’elle est définie sur la page.

## Utilisation des appels de fonction avec un code de lien personnalisé {#concept_DB662C93B3ED415DB72C80270502BE5D}

En raison de la complexité du code de lien personnalisé, vous pouvez consolider le code dans une fonction JavaScript autonome (définie sur la page ou dans un fichier JavaScript lié) et établir des appels vers la fonction dans le gestionnaire d’événements [!UICONTROL onClick].

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>Si nécessaire, vous pouvez transmettre le type de lien et le nom du lien comme paramètres supplémentaires pour la fonction JavaScript.

Pour appeler ces fonctions, vous pouvez utiliser un code semblable à celui-ci :

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## Eviter que les liens soient comptabilisés deux fois {#section_9C3F73DE758F4727943439DED110543C}

Il est possible que le lien soit comptabilisé deux fois dans les cas où il est normalement capturé par le suivi automatique du téléchargement de fichier ou du lien de sortie.

Par exemple, si vous activez le suivi automatique des téléchargements PDF, le code suivant entraîne la double comptabilisation des téléchargements :

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

Pour être sûr que les liens ne sont pas comptabilisés deux fois, utilisez la fonction JavaScript modifiée suivante :

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

Les deux dernières lignes du code ci-dessus modifient le comportement du code de lien personnalisé, de telle sorte que seul le comportement de suivi automatique survienne, éliminant ainsi l’éventualité d’un double comptage.

## Fenêtres contextuelles avec useForcedLinkTracking {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] exécute l’appel de suivi des liens et traite manuellement l’événement de navigation, au lieu d’utiliser l’opération par défaut du navigateur.

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

Cela permet le suivi du lien et le chargement de la fenêtre contextuelle, comme prévu.

## Liens provenant de réducteurs d’URL {#concept_CD792362A8E04448B452BE9A18772024}

Les services de liens provenant de réducteurs d’URL (tels que bit.ly) ne sont généralement pas suivis en tant que pages vues ou référents. Ces services renvoient des redirections 301/302 avec l’URL complète au navigateur Web qui envoie alors une nouvelle demande distincte à l’ensemble de l’URL. Le référent original est conservé puisque le réducteur ne figure plus dans la boucle, et aucune indication ne figure sur la demande indiquant qu’un service de redirection a été utilisé pour obtenir l’URL.

<!-- 

link_shortener.xml

 -->

En raison de la gamme des services disponibles, nous vous recommandons de tester les scénarios spécifiques en cours d’utilisation sur votre site afin de déterminer le mécanisme de redirection utilisé par le service.

## Variables de suivi des liens dans doPlugins {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

Pour faciliter la gestion du suivi des liens, les variables suivantes sont complétées avant l’exécution de la fonction `doPlugins`.

<!-- 

util_linkhandler.xml

 -->

Dans `doPlugins`, vous pouvez utiliser les valeurs suivantes pour modifier le comportement du suivi des liens. Vous pouvez, par exemple, annuler le suivi ou ajouter des variables supplémentaires aux demandes de suivi.

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Impact </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>Contient le type de lien déterminé automatiquement, le cas échéant. Peut être définie sur l’un des paramètres suivants : </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (téléchargement) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (sortie) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (personnalisé/autre) </li> 
    </ul> <p>Il s’agit du paramètre <code>pe</code> dans la demande d’image. </p> </td> 
   <td colname="col3"> <p>Si elle est définies avec <code>linkURL</code> ou <code>linkName</code>, un appel au serveur est envoyé en tant que lien de téléchargement, de sortie ou personnalisé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>Nom qui apparaît dans le rapport sur les liens de téléchargement, de sortie ou personnalisés. Tronquée à 100 caractères. Peut être définie sur n’importe quelle chaîne. </p> <p>Il s’agit du paramètre <code>pev2</code> dans la demande d’image. </p> </td> 
   <td colname="col3"> <p> Si elle est définie avec <code>linkType</code>, une demande d’image est envoyée en tant que lien de sortie, de téléchargement ou personnalisé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>URL du lien, qui fait office de nom en l’absence de variable linkName. Peut être définie sur n’importe quelle chaîne d’URL. </p> <p>Il s’agit du paramètre <code>pev1</code> dans la demande d’image. </p> </td> 
   <td colname="col3"> <p>Si elle est définie avec <code>linkType</code>, une demande d’image est envoyée en tant que lien de sortie, de téléchargement ou personnalisé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>L’objet qui fait l’objet d’un clic à des fins de référence. Il est en lecture seule. </p> </td> 
   <td colname="col3"> <p>Aucun impact direct sur les mesures. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## Validation des téléchargements de fichiers, des liens de sortie et des liens personnalisés {#concept_0B43AD582D3E470899FCCB58E44D3D49}

Pour valider complètement des liens de téléchargement, de sortie et personnalisés, Adobe conseille d’utiliser un analyseur de paquets afin d’examiner les liens en temps réel.

<!-- 

downloads_validate.xml

 -->

Les téléchargements de fichiers, les liens de sortie et les liens personnalisés ne sont pas des pages vues. Il est donc impossible d’utiliser le [!UICONTROL DigitalPulse Debugger] pour vérifier les paramètres et les variables. Vous devez utiliser un [Moniteur de paquets](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) pour afficher les données de lien de suivi.
