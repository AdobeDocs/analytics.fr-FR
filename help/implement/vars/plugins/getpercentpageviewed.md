---
title: getPercentPageViewed
description: Permet de connaître le pourcentage de la page consultée par le visiteur.
translation-type: tm+mt
source-git-commit: f11ad012756b5d42b1b53483c8688e30b4b79c83
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 98%

---


# Plug-in Adobe : getPercentPageViewed

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPercentPageViewed` mesure l’activité de défilement d’un visiteur pour savoir quelle partie d’une page il a vue avant de passer à une autre page. Ce plug-in n’est pas nécessaire si vos pages sont de petite taille ou si vous ne souhaitez pas mesurer l’activité de défilement.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d&#39;action : Initialiser getPercentPageViewed
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getPercentPageViewed` utilise les arguments suivants :

* **`pid`** (facultatif, chaîne) : identifiant basé sur une page que vous pouvez mettre en corrélation avec les pourcentages fournis par les mesures du plug-in.  Par défaut, la variable `pageName`.
* **`ch`** (facultatif, booléen) : définissez cet argument sur `false` (ou `0`) si vous ne souhaitez pas que le plug-in prenne en compte les modifications apportées à la taille d’une page après son chargement initial. S’il est ignoré, cet argument prend par défaut la valeur `true`. Dans la plupart des cas, Adobe recommande d’ignorer cet argument.

L’appel de cette méthode ne renvoie rien ; au contraire, il définit les variables suivantes :

* `s._ppvPreviousPage` : nom de la page précédente consultée. Les mesures finales de défilement de la page active ne sont disponibles qu’après le chargement d’une nouvelle page.
* `s._ppvHighestPercentViewed` : pourcentage le plus élevé de la page précédente que le visiteur a consultée (en termes de hauteur). Point le plus éloigné vers lequel le visiteur a fait défiler la page précédente.
* `s._ppvInitialPercentViewed` : pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente.
* `s._ppvHighestPixelsSeen` : nombre total de pixels le plus élevé affiché (en termes de hauteur) pendant que le visiteur faisait défiler la page précédente.
* `s._ppvFoldsSeen` : nombre de « plis de page » le plus élevé atteint pendant que le visiteur faisait défiler la page précédente. Cette variable inclut le pli « haut de page ».
* `s._ppvFoldsAvailable` : nombre total de « plis de page » disponibles pour faire défiler la page précédente.

Affectez une ou plusieurs de ces variables à des eVars pour afficher les données sur les dimensions dans les rapports.

Ce plug-in crée un cookie propriétaire appelé `s_ppv` qui contient les valeurs ci-dessus. Il expire à la fin de la session du navigateur.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Détermine si s.pageName est défini et, si tel est le cas, le code exécute la fonction getPercentPageViewed.
* Lorsque la fonction getPercentPageViewed s’exécute, elle crée les variables décrites dans la section « Retours » ci-dessus.
* Si les variables « Retours » ont été correctement définies :
   * Le code définit s.prop1 sur la valeur de s._ppvPreviousPage (c’est-à-dire la valeur précédente de s.pageName, ou la page précédente).
   * Le code définit également s.prop2 sur le pourcentage d’affichage le plus élevé de la page précédente et le pourcentage d’affichage initial de la page précédente, ainsi que sur le nombre de plis atteint par le visiteur et le nombre de plis disponibles.

**Remarque** : si une page entière est visible lors du premier chargement, les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial sont égales à 100, et les dimensions Plis vus et Plis disponibles sont égales à 1.   Lorsqu’une page entière n’est PAS visible au premier chargement, mais que le visiteur ne fait jamais défiler la page vers le bas avant de passer à la page suivante, les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial sont égales à la même valeur.

### Exemple 2

Supposons que s.prop5 ait été réservé pour capturer un « type de page » cumulé plutôt que le nom complet de la page.

Le code suivant détermine si s.prop5 a été défini et, si tel est le cas, stocke sa valeur en tant que « page précédente » pour établir une corrélation avec les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial.  La valeur est toujours stockée dans la variable s._ppvPreviousPage, mais elle peut être traitée comme s’il s’agissait du type de page précédente au lieu du nom de la page précédente.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Historique des versions

### 5.0 (19 mars 2021)

* Numéro de version Ajouté en tant que données contextuelles.

### v4.0 (7 octobre 2019)

* Ajout des solutions `s._ppvFoldsSeen` et `s._ppvFoldsAvailable`.

### v3.01 (13 août 2018)

* Correction d’un problème pour les pages comportant plusieurs objets AppMeasurement sur une page.

### v3.0 (13 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Le plug-in crée maintenant des variables à attribuer aux variables Adobe Analytics plutôt que des valeurs renvoyées.
