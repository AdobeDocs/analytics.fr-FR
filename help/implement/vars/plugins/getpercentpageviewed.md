---
title: getPercentPageViewed
description: Récupérez le pourcentage de la page affichée par le.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getPercentPageViewed

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

The `getPercentPageViewed` plug-in measures a visitor&#39;s scroll activity to see how much of a page they view before moving on to another page. Ce plug-in n’est pas nécessaire si vos pages sont de petite taille ou si vous ne souhaitez pas mesurer le  de défilement .

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous l’extension Adobe Analytics.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

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

## Utilisation du module externe

La `getPercentPageViewed` méthode utilise les arguments suivants :

* **`pid`** (facultatif, chaîne) :  Identifiant basé sur une page que vous pouvez corréler aux pourcentages fournis par les mesures du module externe.  Valeur par défaut de la `pageName` variable.
* **`ch`** (facultatif, booléen) :  Définissez cette option sur `false` (ou `0`) si vous ne souhaitez pas que le module externe prenne en compte les modifications apportées à la taille d’une page après son chargement initial. S’il est omis, cet argument prend par défaut la valeur `true`. Adobe recommande dans la plupart des cas d’ignorer cet argument.

L’appel de cette méthode ne renvoie rien ; il définit plutôt les variables suivantes :

* `s._ppvPreviousPage`: Nom de la page précédente affichée. Les mesures de défilement finales de la page active ne sont disponibles qu’après le chargement d’une nouvelle page.
* `s._ppvHighestPercentViewed` : pourcentage le plus élevé de la page précédente que le visiteur a consultée (en termes de hauteur). Le point le plus éloigné vers lequel le a fait défiler la page précédente.
* `s._ppvInitialPercentViewed`: Pourcentage de la page précédente qui était visible lors du premier chargement de la page précédente.
* `s._ppvHighestPixelsSeen` : nombre total de pixels le plus élevé affiché (en termes de hauteur) pendant que le visiteur faisait défiler la page précédente.
* `s._ppvFoldsSeen`: Nombre le plus élevé de &quot;plis de page&quot; atteint lorsque le fait défiler la page précédente. Cette variable inclut le pliage &quot;haut de la page&quot;.
* `s._ppvFoldsAvailable`: Nombre total de &quot;plis de page&quot; disponibles pour faire défiler vers le bas sur la page précédente.

Affectez une ou plusieurs de ces variables à des eVars pour afficher les données de dimension dans les rapports.

Ce plug-in crée un cookie propriétaire appelé `s_ppv` qui contient les valeurs ci-dessus. Elle expire à la fin de la session du navigateur.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* détermine si s.pageName est défini et, si tel est le cas, le code exécute la fonction getPercentPageViewed
* Lorsque la fonction getPercentPageViewed s&#39;exécute, elle crée les variables décrites dans la section &quot;Retours&quot; ci-dessus
* Si les variables &quot;Retours&quot; ont bien été définies :
   * Le code définira s.prop1 sur la valeur de s._ppvPreviousPage (c&#39;est-à-dire la valeur précédente de s.pageName ou la page précédente).
   * Le code définit également s.prop2 sur le pourcentage le plus élevé affiché de la page précédente et le pourcentage initial affiché de la page précédente, ainsi que le nombre de plis atteint par le et le nombre de plis disponibles.

**Remarque**:  Si une page entière est visible lors du premier chargement, les dimensions Pourcentage le plus élevé affiché et Pourcentage initial affiché sont égales à 100, et les dimensions Dossiers vus et Dossiers disponibles sont égales à 1.   Lorsqu’une page entière n’est PAS visible au premier chargement, mais que le ne finit jamais par faire défiler la page avant de passer à la page suivante, les dimensions Pourcentage le plus élevé affiché et Pourcentage initial affiché sont égales à la même valeur.

### Exemple n° 2

Supposons que s.prop5 ait été réservé pour capturer un « type de page » cumulé plutôt que le nom complet de la page.

Le code suivant détermine si s.prop5 a été défini et, dans l’affirmative, stocke sa valeur en tant que &quot;page précédente&quot; pour établir une corrélation avec les dimensions Pourcentage le plus élevé affiché et Pourcentage initial affiché.  La valeur sera toujours stockée dans la variable s._ppvPreviousPage, mais elle peut être traitée comme s’il s’agissait du type de page précédent au lieu du nom de page précédent.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Historique des versions

### v4.0 (7 octobre 2019)

* Ajout `s._ppvFoldsSeen` et `s._ppvFoldsAvailable` solutions

### v3.01 (13 août 2018)

* Correction d’un problème pour les pages comportant plusieurs objets AppMeasurement sur une page.

### v3.0 (13 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite)
* Le module externe crée désormais des variables à affecter aux variables Adobe Analytics au lieu des valeurs renvoyées.
