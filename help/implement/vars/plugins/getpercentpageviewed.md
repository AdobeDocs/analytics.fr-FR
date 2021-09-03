---
title: getPercentPageViewed
description: Permet de connaître le pourcentage de la page consultée par le visiteur.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Plug-in Adobe : getPercentPageViewed

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPercentPageViewed` mesure l’activité de défilement d’un visiteur pour savoir quelle partie d’une page il a vue avant de passer à une autre page. Ce plug-in n’est pas nécessaire si vos pages sont de petite taille ou si vous ne souhaitez pas mesurer l’activité de défilement.

## Installation du plug-in à l’aide de balises dans Adobe Experience Platform

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
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

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getPercentPageViewed` utilise les arguments suivants :

* **`pid`** (facultatif, chaîne) : identifiant basé sur une page que vous pouvez mettre en corrélation avec les pourcentages fournis par les mesures du plug-in.  Par défaut, la variable `pageName`.
* **`ch`** (facultatif, booléen) : définissez cet argument sur `false` (ou `0`) si vous ne souhaitez pas que le plug-in prenne en compte les modifications apportées à la taille d’une page après son chargement initial. S’il est ignoré, cet argument prend par défaut la valeur `true`. Dans la plupart des cas, Adobe recommande d’ignorer cet argument.

L’appel de cette fonction ne renvoie rien ; au lieu de cela, il définit les variables suivantes :

* `s._ppvPreviousPage` : nom de la page précédente consultée. Les mesures finales de défilement de la page active ne sont disponibles qu’après le chargement d’une nouvelle page.
* `s._ppvHighestPercentViewed` : pourcentage le plus élevé de la page précédente que le visiteur a consultée (en termes de hauteur). Point le plus éloigné vers lequel le visiteur a fait défiler la page précédente. Si la page entière est visible au premier chargement, cette valeur est `100`.
* `s._ppvInitialPercentViewed` : pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente. Si la page entière est visible au premier chargement, cette valeur est `100`.
* `s._ppvHighestPixelsSeen` : nombre total de pixels le plus élevé affiché (en termes de hauteur) pendant que le visiteur faisait défiler la page précédente.
* `s._ppvFoldsSeen` : nombre de « plis de page » le plus élevé atteint pendant que le visiteur faisait défiler la page précédente. Cette variable inclut le pli « haut de page ». Si la page entière est visible au premier chargement, cette valeur est `1`.
* `s._ppvFoldsAvailable` : nombre total de « plis de page » disponibles pour faire défiler la page précédente. Si la page entière est visible au premier chargement, cette valeur est `1`.

Affectez une ou plusieurs de ces variables à des eVars pour afficher les données sur les dimensions dans les rapports.

Ce plug-in crée un cookie propriétaire appelé `s_ppv` qui contient les valeurs ci-dessus. Il expire à la fin de la session du navigateur.

## Exemples

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed, the intial percent, the number of folds viewed, and total number of folds of the previous page
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed + " | foldsSeen=" + _ppvFoldsSeen + " | foldsAvailable=" + _ppvFoldsAvailable;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the highest percent viewed and the initial percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + _ppvHighestPercentViewed + " | initialPercentViewed=" + _ppvInitialPercentViewed;
}
```

## Historique des versions

### 5.0.1 (22 juin 2021)

* Correction dʼun problème en raison duquel certains caractères spéciaux entraînaient le dysfonctionnement du plug-in.

### 5.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### v4.0 (7 octobre 2019)

* Ajout des solutions `s._ppvFoldsSeen` et `s._ppvFoldsAvailable`.

### v3.01 (13 août 2018)

* Correction d’un problème pour les pages comportant plusieurs objets AppMeasurement sur une page.

### v3.0 (13 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Le plug-in crée maintenant des variables à attribuer aux variables Adobe Analytics plutôt que des valeurs renvoyées.
