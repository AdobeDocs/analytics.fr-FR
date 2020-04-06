---
title: getTimeSinceLastVisit
description: Permet de mesurer le temps écoulé entre deux visites.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getTimeSinceLastVisit

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getTimeSinceLastVisit` vous permet de suivre le temps qu’un visiteur a mis pour revenir sur votre site après sa dernière visite.

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
   * Type d’action : initialisation de getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getTimeSinceLastVisit` n’utilise aucun argument. Elle renvoie le temps écoulé depuis le dernier accès du visiteur au site, présenté sous le format suivant :

* Le temps compris entre 30 minutes et une heure depuis la dernière visite est défini selon la référence d’une demi-minute la plus proche. Par exemple, `"30.5 minutes"`, `"53 minutes"`.
* Le temps entre une heure et un jour est arrondi à la référence d’un quart d’heure la plus proche. Par exemple, `"2.25 hours"`, `"7.5 hours"`.
* Le temps écoulé depuis plus d’un jour est arrondi à la référence de jour la plus proche. Par exemple, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`.
* Si un visiteur ne s’est pas rendu sur le site avant ou si le temps écoulé est supérieur à deux ans, alors la valeur est définie sur `"New Visitor"`.

>[!NOTE] Ce plug-in renvoie uniquement une valeur au premier accès d’une visite.

Ce plug-in crée un cookie propriétaire appelé `"s_tslv"` défini sur un horodatage Unix de l’heure actuelle. Le cookie expire après deux ans d’inactivité.

## Exemples d’appels

### Exemple 1

Si un nouveau visiteur arrive sur le site et que le code suivant s’exécute sur la première page de la visite…

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...alors la valeur de s.prop1 est définie sur « New Visitor ».

Si le même code s’exécute sur le même domaine après 35 minutes d’inactivité, la valeur de s.prop1 est définie sur « 35 minutes ».

Si le même code s’exécute sur le même domaine après 4 jours d’inactivité prolongée, la valeur de s.prop1 est définie sur « 4 jours ».

## Historique des versions

### 1.0 (16 avril 2018)

* Nouvelle version (code recompilé et taille réduite).
* Code dérivé du plug-in `getDaysSinceLastVisit` (désormais obsolète et renommé).
* Utilisation des plug-ins `formatTime` et `inList` pour la valeur renvoyée.
