---
title: getPercentPageViewed
description: Permet de connaître le pourcentage de la page consultée par le visiteur.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 100%

---


# Plug-in Adobe : getPercentPageViewed

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPercentPageViewed` mesure l’activité de défilement d’un visiteur pour savoir quelle partie d’une page il a vue avant de passer à une autre page. Ce plug-in n’est pas nécessaire si vos pages sont de petite taille ou si vous ne souhaitez pas mesurer l’activité de défilement.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
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

### v4.0 (7 octobre 2019)

* Ajout des solutions `s._ppvFoldsSeen` et `s._ppvFoldsAvailable`.

### v3.01 (13 août 2018)

* Correction d’un problème pour les pages comportant plusieurs objets AppMeasurement sur une page.

### v3.0 (13 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Le plug-in crée maintenant des variables à attribuer aux variables Adobe Analytics plutôt que des valeurs renvoyées.
