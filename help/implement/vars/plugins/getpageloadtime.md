---
title: getPageLoadTime
description: Permet d’assurer le suivi du temps nécessaire au chargement d’une page.
translation-type: ht
source-git-commit: b3c5fa41194d74725f48e12a546d8ce1c08b9b7d
workflow-type: ht
source-wordcount: '566'
ht-degree: 100%

---


# Plug-in Adobe : getPageLoadTime

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPageLoadTime` utilise l’objet de performance JavaScript pour vous permettre de mesurer le temps nécessaire au chargement complet d’une page. Adobe recommande d’utiliser ce plug-in si vous souhaitez mesurer le temps de chargement des pages.

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
   * Type d’action : initialisation de getPageLoadTime
1. Enregistrez et publiez les modifications apportées à la règle.

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
/* Adobe Consulting Plugin: getPageLoadTime v2.0 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function f(){function a(a,b){if(0<=a&&0<=b)return 6E4>a-b&&0<=a-b?parseFloat((a-b)/1E3).toFixed(2):60}var b=performance.timing;0<b.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",a(b.loadEventEnd,b.navigationStart)),window.cookieWrite("s_pltp",window.pageName)));window.ptc=b.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof c&&(c.contextData.getPageLoadTime="2.0");window.pageName="undefined"!==typeof c&&c.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,e){if("string"===typeof a){var c=window.location.hostname,h=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){h=2<h?h:2;var d=c.lastIndexOf(".");if(0<=d){for(;0<=d&&1<h;)d=c.lastIndexOf(".",d-1),h--;d=0<d?c.substring(d):c}}g=d;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var k=new Date;k.setTime(k.getTime()+6E4*e)}else k=e;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),f=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((c=performance,c.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<c.timing.loadEventEnd&&clearInterval(window.pi),window._pltLoadTime=window.cookieRead("s_plt"),window._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===c.timing.loadEventEnd)?window.pi=setInterval(function(){f()},250):0<c.timing.loadEventEnd&&(window.ptc?window.ptc===c.timing.loadEventEnd&&1===c.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):f()))};
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

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (22 mai 2018)

* Version initiale.
