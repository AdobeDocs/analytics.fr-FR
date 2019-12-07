---
description: Mesure l’activité de défilement d’un visiteur afin de voir la quantité d’une page qu’il voit avant de passer à une autre page. Ce module externe vous permet de déterminer la quantité de contenu que les utilisateurs consultent en moyenne, de sorte que vous puissiez optimiser les longueurs et dispositions de page en fonction de leur comportement.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPercentPageViewed
topic: Developer and implementation
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPercentPageViewed

Le module externe getPercentPageViewed mesure l’activité de défilement d’un visiteur afin de voir la quantité d’une page qu’il voit avant de passer à une autre page.

>[!NOTE]
>Vous n’avez pas besoin d’utiliser le module externe getPercentPageViewed si la hauteur de vos pages web n’est pas importante et s’il n’est pas nécessaire de mesurer la valeur du défilement des pages par les visiteurs. En outre, si vous souhaitez mesurer l’activité de défilement uniquement sur les pages de sortie, vous ne pouvez pas utiliser ce module externe.

## Conditions préalables

Vous devez disposer d’AppMeasurement et du module d’aide handlePPVevents pour exécuter le module externe getPercentPageViewed.

## Mise en œuvre

Pour mettre en œuvre ce plug-in, copiez et collez le code n’importe où dans la section **[!UICONTROL Plugins]** du fichier [!DNL AppMeasurement].

>[!NOTE]
>L’ajout des commentaires/numéros de version en gras du code au fichier AppMeasurement permet au conseiller Adobe de résoudre les problèmes potentiels de mise en œuvre.

Vous pouvez exécuter la fonction `getPercentPageViewed` selon vos besoins dans la fonction doPlugins (voir les exemples d’appels ci-dessous).

## Arguments à transmettre

| Argument | Définition |
|---|---|
| pid (facultatif, chaîne) | Identifiant de page corrélé aux pourcentages fournis par les mesures du module externe. Sa valeur par défaut est la variable pageName d’Analytics OU l’URL si cette variable n’est pas définie. |
| ch (facultatif, booléen) | « True » est la valeur recommandée/par défaut pour cet argument. Définissez-le comme égal à « false » si vous ne voulez pas que le module externe prenne en considération toute modification de la taille d’une page après son chargement initial, en raison d’un code SPA, d’HTML dynamique, etc. |

## Retours

Le module externe getPercentPageViewed ne renvoie rien. Au lieu de cela, il définit les variables suivantes au sein de l’objet AppMeasurement :

* `s._ppvPreviousPage` : nom de la page précédente affichée (car les mesures finales ne sont pas disponibles tant qu’une nouvelle page n’est pas chargée).
* `s._ppvHighestPercentViewed` : pourcentage le plus élevé de la page précédente que le visiteur a consultée (en termes de hauteur). En d’autres termes, le point le plus éloigné jusqu’auquel le visiteur a fait défiler la page précédente.
* `s._ppvInitialPercentViewed` : pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente.
* `s._ppvHighestPixelSeen` : nombre total de pixels le plus élevé affiché (en termes de hauteur) pendant que le visiteur faisait défiler la page précédente.

## Cookies

Le module externe getPercentPageViewed crée un cookie, appelé `s_ppv`, qui est transmis d’une page à l’autre. Le contenu du cookie contient les valeurs insérées dans les quatre variables décrites ci-dessus et expire à la fin de la session.

## Exemples d’appels

**Exemple d’appel 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

L’exemple de code ci-dessus :
* détermine si s.pageName est défini et, si tel est le cas, le code exécute la fonction getPercentPageViewed.
* Lorsque la fonction `getPercentPageViewed` s’exécute, elle crée les variables décrites dans la section « Retours » ci-dessus.
* Si les variables « Retours » ont été correctement définies :

   * Le code définit s.prop1 sur la valeur de `s._ppvPreviousPag`e (c.-à-d. la valeur précédente de `s.pageName`, ou la page précédente).
   * Le code définit également s.prop2 sur le pourcentage d’affichage le plus élevé de la page précédente et le pourcentage d’affichage initial de la page précédente.

>[!NOTE]
>Si une page entière est visible au premier chargement, les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial sont égales à 100. Toutefois, si une page entière n’est pas visible au premier chargement, mais que le visiteur ne fait jamais défiler la page vers le bas avant de passer à la page suivante, les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial sont égales à la même valeur.

**Exemple d’appel 2**

Supposons que s.prop5 ait été réservé pour capturer un « type de page » cumulé plutôt que le nom complet de la page.

Le code suivant détermine si s.prop5 a été défini et, si tel est le cas, stocke sa valeur en tant que « page précédente » pour établir une corrélation avec les dimensions Pourcentage d’affichage le plus élevé et Pourcentage d’affichage initial. La valeur est toujours stockée dans la variable `s._ppvPreviousPage`, mais elle peut être traitée comme s’il s’agissait du type de page précédent au lieu du nom de la page précédent.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Remplacement d’objet s

Lors de l’instanciation de l’objet de bibliothèque AppMeasurement principal avec un autre nom que « s », modifiez la partie suivante du code du module externe à partir de :

`s.getPercentPageViewed=function(pid,ch)`

en ceci :

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
