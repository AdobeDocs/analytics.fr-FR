---
title: ' getTimeSinceLastVisit'
description: Mesurez la durée écoulée entre deux visites.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Module externe Adobe : getTimeSinceLastVisit

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getTimeSinceLastVisit` module externe vous permet de suivre le temps qu’un visiteur a mis pour revenir sur votre site après sa dernière visite.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Pour toute règle de lancement dans laquelle vous souhaitez utiliser le module externe, ajoutez une action avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser addProductEvar
1. Enregistrer et publier les modifications apportées à la règle

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez la section [!UICONTROL Configurer le suivi à l’aide de l’accordéon de code] personnalisé, qui affiche le bouton [!UICONTROL Ouvrir l’éditeur] .
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide `s_gi`). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

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

## Utilisation du module externe

La `getTimeSinceLastVisit` méthode n’utilise aucun argument. Elle renvoie le temps écoulé depuis le dernier accès du visiteur au site, avec le format suivant :

* Durée comprise entre 30 minutes et une heure depuis la dernière visite est définie sur le point de référence demi-minute le plus proche. For example, `"30.5 minutes"`, `"53 minutes"`
* Le temps entre une heure et une journée est arrondi au point de repère du quart d’heure le plus proche. For example, `"2.25 hours"`, `"7.5 hours"`
* Le temps supérieur à un jour est arrondi au point de repère du jour le plus proche. For example, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`
* Si un visiteur n’a pas visité le site avant ou si le temps écoulé est supérieur à deux ans, la valeur est définie sur `"New Visitor"`.

> [!NOTE] Ce module externe renvoie uniquement une valeur au premier accès d’une visite.

Ce plug-in crée un cookie propriétaire appelé `"s_tslv"` défini sur un horodatage Unix de l’heure actuelle. Le cookie expire après deux ans d’inactivité.

## Exemples d’appels

### Exemple n° 1

Si un nouveau visiteur arrive sur le site et que le code suivant s’exécute sur la première page de la visite...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

...la valeur de s.prop1 sera définie sur &quot;Nouveau visiteur&quot;.

Si le même code s’exécute sur le même domaine après 35 minutes d’inactivité, la valeur de s.prop1 est définie sur &quot;35 minutes&quot;.

Si le même code s’exécute sur le même domaine après 4 jours d’inactivité ultérieure, la valeur de s.prop1 est définie sur &quot;4 jours&quot;.

## Historique des versions

### 1.0 (16 avril 2018)

* Publication ponctuelle (code recompilé et taille plus petite).
* Code dérivé du `getDaysSinceLastVisit` module externe (désormais obsolète et renommé).
* Utilise désormais `formatTime` et `inList` les plug-ins pour la valeur renvoyée.
