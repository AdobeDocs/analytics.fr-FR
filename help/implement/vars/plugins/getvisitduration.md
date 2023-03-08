---
title: getVisitDuration
description: Permet d’effectuer le suivi du temps passé par un visiteur sur le site jusqu’à présent.
feature: Variables
exl-id: 5299caa8-1e47-40b0-a8f4-422590f33ee4
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 100%

---

# Plug-in Adobe : getVisitDuration

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getVisitDuration` effectue le suivi en minutes du temps de consultation du site par le visiteur jusqu’à ce moment-là. Adobe recommande d’utiliser ce plug-in si vous souhaitez effectuer le suivi du temps cumulé sur le site jusqu’à ce moment-là ou pour suivre le temps nécessaire à la réalisation d’une activité. Ce plug-in ne permet pas de suivre le temps écoulé entre deux événements. Si vous recherchez cette fonctionnalité, utilisez le plug-in [`getTimeBetweenEvents`](gettimebetweenevents.md).

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getVisitDuration
1. Save and publish the changes to the rule.-->

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getVisitDuration` nʼutilise aucun argument. Elle renvoie l’une des valeurs suivantes :

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (où `[x]` est le nombre de minutes écoulées depuis que le visiteur a accédé au site)

Ce plug-in crée un cookie propriétaire appelé `"s_dur"`, qui correspond au nombre de millisecondes écoulées depuis l’arrivée du visiteur sur le site. Le cookie expire après 30 minutes d’inactivité.

## Exemples

```js
// Always sets eVar10 to the number of minutes passed since the visitor first landed on the site
s.eVar10 = getVisitDuration();

// Checks if the events variable contains the purchase event.
// If it does, sets eVar56 to the number of minutes between the start of the visit and the time of purchase
if(inList(s.events, "purchase")) s.eVar56 = getVisitDuration();
```

## Historique des versions

### 2.1 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.0 (2 mai 2018)

* Nouvelle version (réanalyse/réécriture complète du plug-in).
