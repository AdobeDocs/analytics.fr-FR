---
title: getPageLoadTime
description: Permet d’assurer le suivi du temps nécessaire au chargement d’une page.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getPageLoadTime

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPageLoadTime` utilise l’objet de performance JavaScript pour vous permettre de mesurer le temps nécessaire au chargement complet d’une page. Adobe recommande d’utiliser ce plug-in si vous souhaitez mesurer le temps de chargement des pages.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getPageLoadTime
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageLoadTime v1.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires p_fo plug-in) */
s.getPageLoadTime=function(){var a=this;if("undefined"!==typeof performance&&a.p_fo("performance")){var b=performance; b.clearResourceTimings();""!==a.c_r("s_plt")&&(0<b.timing.loadEventEnd&&clearInterval(a.pi),a._pltLoadTime=a.c_r("s_plt"),a._pltPreviousPage=a.c_r("s_pltp"),a.c_w("s_plt",""),a.c_w("s_pltp",""));0===b.timing.loadEventEnd?a.pi=setInterval(function(){a.performanceWriteFull()},250):0<b.timing.loadEventEnd&&(a.ptc?a.ptc===b.timing.loadEventEnd&&1===b.getEntries().length&&(a.pwp=setInterval(function(){a.performanceWritePart()},500)):a.performanceWriteFull())}};
s.performanceWriteFull=function(){var s=this,a=performance.timing;0<a.loadEventEnd&&(clearInterval(s.pi),""===s.c_r("s_plt")&& (s.c_w("s_plt",s.performanceCheck(a.loadEventEnd,a.navigationStart)),s.c_w("s_pltp",s.pageName)));s.ptc=a.loadEventEnd};
s.performanceWritePart=function(){var s=this,a=performance;0<a.getEntries().length&&(s.ppfe===a.getEntries().length? clearInterval(s.pwp):s.ppfe=a.getEntries().length);""===s.c_r("s_plt")&&(s.c_w("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),s.c_w("s_pltp",s.pageName))};
s.performanceCheck=function(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getPageLoadTime` n’utilise aucun argument. Lorsque vous appelez cette méthode, elle ne renvoie rien. Elle définit plutôt les variables suivantes :

* `s._pltPreviousPage` : page précédente qui vous permet d’établir une corrélation entre le temps de chargement et la page précédente.
* `s._pltLoadTime` : temps (en secondes) nécessaire au chargement de la page précédente.

Le plug-in getPageLoadTime crée deux cookies propriétaires :

* `s_plt` : temps (en secondes) nécessaire au chargement de la page précédente. Expire à la fin de la session du navigateur.
* `s_pltp` : valeur de la variable `s.pageName` telle qu’elle a été enregistrée dans la demande d’image Adobe Analytics précédente. Expire à la fin de la session du navigateur.

## Exemples d’appels

### Exemple 1

En exécutant le code suivant…

```js
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.prop11 = s._pltPreviousPage
  s.eVar10 = prop11;
  s.events = "event100=" + s._pltLoadTime;
}
```

…il vous sera possible d’effectuer les opérations suivantes :

* Exécuter le plug-in getPageLoadTime lorsque s.pageName est défini.
* Définir s.prop10 sur le temps de chargement de la page précédente.
* Définir s.prop11 et s.eVar10 sur le nom de la page précédente (tel qu’il est enregistré dans s.pageName).
* Définir event100, qui serait un événement numérique personnalisé, sur le temps de chargement de la page précédente.   Dans ce cas, l’utilisation d’un événement personnalisé vous permettrait d’obtenir le temps total pour tous les chargements de la page précédente (de tous les visiteurs/visites) et donc d’utiliser une mesure calculée pour connaître le temps moyen de chargement de chaque page.

## Historique des versions

### 1.0 (22 mai 2018)

* Version initiale.
