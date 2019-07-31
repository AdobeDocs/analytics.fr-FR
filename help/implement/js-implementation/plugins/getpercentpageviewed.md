---
description: Mesure l’activité de défilement d’un visiteur afin de voir la quantité d’une page qu’il voit avant de passer à une autre page. Ce module externe vous permet de déterminer la quantité de contenu que les utilisateurs consultent en moyenne, de sorte que vous puissiez optimiser les longueurs et dispositions de page en fonction de leur comportement.
keywords: Mise en œuvre d’Analytics
seo-description: Mesure l’activité de défilement d’un visiteur afin de voir la quantité d’une page qu’il voit avant de passer à une autre page. Ce module externe vous permet de déterminer la quantité de contenu que les utilisateurs consultent en moyenne, de sorte que vous puissiez optimiser les longueurs et dispositions de page en fonction de leur comportement.
seo-title: getPercentPageViewed
solution: Analytics
subtopic: Modules externes
title: getPercentPageViewed
topic: Développeur et mise en œuvre
uuid: 1751 dcdb -699 f -4 bd 1-8 bcb -5 e 62 fa 24896 a
translation-type: tm+mt
source-git-commit: f9912a0da5930be965e4d249f3d2c1891cfd6ed6

---


# getPercentPageViewed

Le plug-in getpercentpageviewed mesure l'activité de défilement d'un visiteur pour déterminer la quantité de page affichée par le visiteur avant de passer à une autre page.

>[!NOTE]
>Il n'est pas nécessaire d'utiliser le plug-in getpercentpageviewed si vos pages Web sont de petite hauteur et qu'il n'est pas nécessaire de mesurer la progression des visiteurs vers le bas. De même, si vous souhaitez mesurer l'activité de défilement sur les pages de sortie uniquement, vous ne pouvez pas utiliser ce plug-in.

## Conditions préalables

Pour exécuter le plug-in getpercentpageviewed, vous devez disposer d'appmeasurement et du plug-in handleppvevents.

## Mise en œuvre

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>L'ajout des commentaires/numéros de version gras du code au fichier appmeasurement aide Adobe Consulting à résoudre tous les problèmes de mise en œuvre potentiels.

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## Arguments à transmettre

| Argument | Définition |
|---|---|
| pid (facultatif, chaîne) | Identifiant de page corrélé avec les pourcentages fournis par les mesures du module. Elle prend par défaut la variable pagename Analytics ou l'URL si la variable pagename n'est pas définie |
| ch (facultatif, booléen) | « True » est la valeur recommandée/par défaut pour cet argument. Définissez cette valeur sur « false » si vous souhaitez que ce module externe prenne en compte les modifications apportées à la taille d'une page après son chargement initial, en raison du code d'application d'une seule page, du code HTML dynamique, etc. |

## Retours

Le plug-in getpercentpageviewed ne renvoie rien. Au lieu de cela, il définit les variables suivantes au sein de l’objet AppMeasurement :

* `s._ppvPreviousPage`: Le nom de la page précédente affichée (car les mesures finales ne sont pas disponibles jusqu'à ce qu'une nouvelle page se charge).
* `s._ppvHighestPercentViewed`: Pourcentage le plus élevé de la page précédente affichée par le visiteur (à la hauteur). En d'autres termes, le point le plus éloigné du visiteur vers le bas sur la page précédente.
* `s._ppvInitialPercentViewed`: Pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente.
* `s._ppvHighestPixelSeen`: Nombre le plus élevé de pixels vus (au niveau de la hauteur) pendant que le visiteur a fait défiler la page précédente vers le bas.

## Cookies

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. Le contenu du cookie contient les valeurs insérées dans les quatre variables décrites ci-dessus et expire à la fin de la session.

## Exemples d'appels

**Exemple d'appel 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

L'exemple de code ci-dessus :
* Détermine si s. pagename est défini et si tel est le cas, le code exécutera la fonction getpercentpageviewed.
* When the `getPercentPageViewed` function runs, it creates the variables described in the "Returns" section above.
* Si les variables « Retours » ont bien été définies :

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * Le code définit également s. prop 2 correspond au pourcentage le plus élevé affiché de la page précédente et au pourcentage initial affiché de la page précédente.

>[!NOTE]
>Si une page entière est visible lors du premier chargement, le pourcentage le plus élevé affiché et le pourcentage initial affiché sont égaux à 100. Cependant, si une page entière n'est pas visible lors du premier chargement, mais que le visiteur ne parviens jamais à faire défiler la page avant de passer à la page suivante, les dimensions Pourcentage supérieur affiché et Pourcentage initial visualisé sont égales à la même valeur.

**Exemple d'appel 2**

Supposons que s. prop 5 a été configuré pour capturer un « type de page » cumulé plutôt que le nom de la page entière.

Le code suivant détermine si s. prop 5 a été défini et, le cas échéant, stocke sa valeur comme « page précédente » pour corréler avec le pourcentage le plus élevé affiché et le pourcentage initial affiché. The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Remplacement de l'objet S

Lors de l'instanciation de l'objet de bibliothèque appmeasurement principal avec un nom autre que « s », modifiez la partie suivante du code de module externe à partir de ceci :

`s.getPercentPageViewed=function(pid,ch)`

à ceci :

`[objectname].getPercentPageViewed=function(pid,ch)`

## Code à déployer

Plugins Section : ajoutez le code suivant à la section du fichier `s_code.js` intitulée PLUGINS SECTION. N’effectuez aucune modification dans cette partie du code du module externe.

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
