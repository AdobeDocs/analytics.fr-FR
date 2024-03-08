---
title: getPercentPageViewed
description: Permet de connaître le pourcentage de la page consultée par le visiteur.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: d53a2aba80455c2d807bc47e579cad4483c99c3b
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 85%

---

# Plug-in Adobe : getPercentPageViewed

{{plug-in}}

Le plug-in `getPercentPageViewed` mesure l’activité de défilement d’un visiteur pour savoir quelle partie d’une page il a vue avant de passer à une autre page. Ce plug-in n’est pas nécessaire si vos pages sont de petite taille ou si vous ne souhaitez pas mesurer l’activité de défilement.

## Installation du module externe à l’aide du SDK Web ou de l’extension SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans le SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type dʼaction : initialisation de getPercentPageViewed
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getPercentPageViewed` utilise les arguments suivants :

* **`pid`** (facultatif, chaîne) : une variable ou une valeur égale à la page active. Sa valeur par défaut est la variable Analytics AppMeasurement `pageName` OU l’URL actuelle si cette variable AppMeasurement pageName n’est pas définie.
* **`ch`** (facultatif, booléen) : définissez cet argument sur `false` (ou `0`) si vous ne souhaitez pas que le plug-in prenne en compte les modifications apportées à la taille d’une page après son chargement initial. S’il est ignoré, cet argument prend par défaut la valeur `true`. Dans la plupart des cas, Adobe recommande d’ignorer cet argument.

Lʼappel de cette fonction ne renvoie rien ; au contraire, il définit les variables suivantes :

* `window._ppvPreviousPage` : nom de la page précédente consultée. Les mesures finales de défilement de la page active ne sont disponibles qu’après le chargement d’une nouvelle page.
* `window._ppvInitialPercentViewed` : pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente. Si la page entière est visible lors du premier chargement, cette valeur est `100`.
* `window._ppvHighestPercentViewed` : pourcentage le plus élevé de la page précédente que le visiteur a consultée (en termes de hauteur). Point le plus éloigné vers lequel le visiteur a fait défiler la page précédente. Si la page entière est visible lors du premier chargement, cette valeur est `100`.
* `window._ppvFinalPercentViewed` : pourcentage de la page précédente qui était visible au moment où le visiteur a accédé à la page active. Cette valeur est égale ou supérieure au pourcentage initial affiché et également égale ou inférieure au pourcentage le plus élevé affiché.
* `window._ppvHighestPixelsSeen` : nombre total de pixels le plus élevé affiché (en termes de hauteur) pendant que le visiteur faisait défiler la page précédente.
* `window._ppvFoldsAvailable` : nombre total de « plis de page » disponibles pour faire défiler la page précédente. Si la page entière est visible lors du premier chargement, cette valeur est `1`.
* `window._ppvFoldsSeen` : nombre de « plis de page » le plus élevé atteint pendant que le visiteur faisait défiler la page précédente. Cette variable inclut le pli « haut de page ». Si la page entière est visible lors du premier chargement, cette valeur est `1`.

Affectez une ou plusieurs de ces variables à des eVars pour afficher les données sur les dimensions dans les rapports.

Ce plug-in crée trois cookies propriétaires qui expirent à la fin d’une session de navigateur :

* `s_ppv`: stocke chacune des valeurs exposées en appelant la fonction
* `s_tp`: stocke la hauteur totale en pixels de la page précédente.
* `s_ips`: stocke le pourcentage initial défilé de la page précédente.

## Exemples

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## Historique des versions

### 5.1 (8 décembre 2022)

* Ajout de la solution `_finalPercentViewed`

### 5.0.1 (22 juin 2021)

* Correction dʼun problème en raison duquel certains caractères spéciaux entraînaient le dysfonctionnement du plug-in.

### 5.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### v4.0 (7 octobre 2019)

* Ajout des solutions `s._ppvFoldsSeen` et `s._ppvFoldsAvailable`.

### v3.01 (13 août 2018)

* Correction d’un problème pour les pages comportant plusieurs objets AppMeasurement sur une page.

### v3.0 (13 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Le plug-in crée maintenant des variables à attribuer aux variables Adobe Analytics plutôt que des valeurs renvoyées.
