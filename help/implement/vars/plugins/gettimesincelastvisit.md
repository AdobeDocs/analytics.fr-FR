---
title: getTimeSinceLastVisit
description: Permet de mesurer le temps écoulé entre deux visites.
feature: Variables
exl-id: c5cef219-8a8a-4e57-a372-f2e063325a67
role: Admin, Developer
source-git-commit: 15a211f34e4bbe54873c44d0e1a756a5f01a0e32
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 72%

---

# Plug-in Adobe : getTimeSinceLastVisit

{{plug-in}}

Le plug-in `getTimeSinceLastVisit` vous permet de suivre le temps qu’un visiteur a mis pour revenir sur votre site après sa dernière visite.

## Installation du plug-in à l’aide de l’extension Web SDK

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** à gauche, puis sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** à gauche, puis sur l’onglet **[!UICONTROL Catalogue]**
1. Recherchez et installez l’extension **[!UICONTROL Plug-ins Web SDK courants]**.
1. Cliquez sur **[!UICONTROL Éléments de données]** à gauche, puis sur l’élément de données de votre choix.
1. Définissez le nom de l’élément de données de votre choix avec la configuration suivante :
   * Extension : plug-ins Web SDK courants
   * Élément de données : `getTimeSinceLastVisit`
1. Enregistrez et publiez les modifications apportées à l’élément de données.

## Installation du plug-in implémentant manuellement le SDK Web

Ce plug-in n’est pas encore pris en charge pour une utilisation dans le cadre d’une implémentation manuelle de Web SDK.

## Installation du plug-in à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getTimeSinceLastVisit
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in des modules externes courants Analytics, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v2.0 */
function getTimeSinceLastVisit(){if(arguments&&"-v"===arguments[0])return{plugin:"getTimeSinceLastVisit",version:"2.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.getTimeSinceLastVisit="2.0");window.formatTime=window.formatTime||function(c,b,d){function f(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var e="";"string"===typeof b&&"d"===b||("string"!==typeof b||!f("h,m,s",b))&&86400<=c?(b=86400,e="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!f("m,s",b))&&3600<=c?(b=3600,e="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!f("s",b))&&60<=c?(b=60,e="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,e="seconds",d=isNaN(d)?.2:b/d);e=Math.round(c*d/b)/d+" "+e;0===e.indexOf("1 ")&&(e=e.substring(0,e.length-1));return e}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var f=window.location.hostname,e=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){e=2<e?e:2;var k=f.lastIndexOf(".");if(0<=k){for(;0<=k&&1<e;)k=f.lastIndexOf(".",k-1),e--;k=0<k?f.substring(k):f}}g=k;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>f?b.length:f)))?c:""};h=new Date;var m=h.getTime(),n=cookieRead("s_tslv")||0,l=Math.round((m-n)/1E3);h.setTime(m+63072E6);cookieWrite("s_tslv",m,h);return n?1800<l||cookieRead("s_inv")?(cookieRead("s_inv")&&(l=cookieRead("s_inv")),cookieWrite("s_inv",l,30),"0"!==l?formatTime(l):"New Visitor"):"":(cookieWrite("s_inv","0",30),"New Visitor")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getTimeSinceLastVisit` nʼutilise aucun argument. Elle renvoie le temps écoulé depuis le dernier accès du visiteur au site, présenté sous le format suivant :

* Le temps compris entre 30 minutes et une heure depuis la dernière visite est défini selon la référence d’une demi-minute la plus proche. Par exemple, `"30.5 minutes"`, `"53 minutes"`.
* Le temps entre une heure et un jour est arrondi à la référence d’un quart d’heure la plus proche. Par exemple, `"2.25 hours"`, `"7.5 hours"`.
* Le temps écoulé depuis plus d’un jour est arrondi à la référence de jour la plus proche. Par exemple, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`.
* Si un visiteur ne s’est pas rendu sur le site avant ou si le temps écoulé est supérieur à deux ans, alors la valeur est définie sur `"New Visitor"`.

>[!NOTE]
>
>Ce plug-in renvoie uniquement une valeur au premier accès d’une visite.

Ce plug-in crée un cookie propriétaire appelé `"s_tslv"` défini sur un horodatage Unix de l’heure actuelle. Le cookie expire après deux ans d’inactivité.

## Exemples

```js
// Given a visitor's first visit to the site
// Sets prop1 to "New Visitor"
s.prop1 = getTimeSinceLastVisit();

// 35 minutes later, the same visitor returns
// Sets prop1 to "35 minutes"
s.prop1 = getTimeSinceLastVisit();

// 4 days later, the same visitor returns
// Sets prop1 to "4 days"
s.prop1 = getTimeSinceLastVisit();
```

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (16 avril 2018)

* Nouvelle version (code recompilé et taille réduite).
* Code dérivé du plug-in `getDaysSinceLastVisit` (désormais obsolète et renommé).
* Utilisation des plug-ins `formatTime` et `inList` pour la valeur renvoyée.
