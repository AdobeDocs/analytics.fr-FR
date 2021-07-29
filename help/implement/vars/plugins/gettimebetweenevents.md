---
title: getTimeBetweenEvents
description: Permet de mesurer le temps qui s’écoule entre deux événements.
exl-id: 15887796-4fe4-4b3a-9a65-a4672c5ecb34
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 96%

---

# Plug-in Adobe : getTimeBetweenEvents

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getTimeBetweenEvents` vous permet de suivre le temps écoulé entre deux événements Analytics, y compris les événements de panier et personnalisés. Il s’avère utile pour effectuer le suivi du temps nécessaire à l’achèvement d’un processus de passage en caisse ou de tout autre processus que vous souhaitez mesurer. Ce plug-in n’est pas nécessaire si vous ne disposez pas de processus de conversion dont vous souhaitez mesurer la durée.

## Installation du module externe à l’aide de balises dans Adobe Experience Platform

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getTimeBetweenEvents
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de 

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getTimeBetweenEvents` utilise les arguments suivants :

* **`ste`** (obligatoire, chaîne) : événements de démarrage du minuteur. Chaîne d’événements Analytics délimitée par des virgules permettant de « démarrer le minuteur ».
* **`rt`** (obligatoire, booléen) : option de redémarrage du minuteur. Définissez cet argument sur `true` si vous souhaitez redémarrer le minuteur chaque fois que la variable `events` contient un événement de démarrage du minuteur. Définissez-le sur `false` si vous ne souhaitez pas que le minuteur redémarre lorsqu’il détecte un événement de démarrage du minuteur.
* **`stp`** (obligatoire, chaîne) : événements d’arrêt du minuteur. Chaîne d’événements Analytics délimitée par des virgules permettant d’« arrêter le minuteur ».
* **`res`** (obligatoire, booléen) : option de réinitialisation du minuteur. Définissez cet argument sur `true` si vous souhaitez enregistrer le temps depuis le démarrage du minuteur ET réinitialiser le minuteur après son arrêt. Définissez-le sur `false` si vous souhaitez enregistrer le temps sans arrêter le minuteur. S’il est défini sur `false`, le minuteur continue de fonctionner après que la variable events a enregistré un événement d’arrêt.

   >[!TIP]
   >
   >Si vous définissez cet argument sur `false`, il est vivement recommandé de définir l’argument `rte` ci-dessous.
* **`cn`** (facultatif, chaîne) : nom du cookie où l’heure du premier événement est enregistrée. La valeur par défaut est `"s_tbe"`.
* **`etd`** (facultatif, entier) : délai d’expiration du cookie en jours. Définissez cet argument sur `0` pour qu’il expire à la fin de la session du navigateur. La valeur par défaut est 1 jour lorsqu’elle n’est pas définie.
* **`fmt`** format du temps dans lequel le nombre de secondes est renvoyé (par défaut, aucun).
   * `"s"` pour les secondes
   * `"m"` pour les minutes
   * `"h"` pour les heures
   * `"d"` pour les jours
   * Lorsqu’il n’est pas défini, le format de la valeur renvoyée dépend des règles suivantes :
      * Tout ce qui est inférieur à une minute est arrondi à la référence de cinq secondes la plus proche. Par exemple, 10 secondes, 15 secondes.
      * Tout ce qui se situe entre une minute et une heure est arrondi à la référence d’une demi-minute la plus proche. Par exemple, 30,5 minutes, 31 minutes.
      * Tout ce qui se situe entre une heure et un jour est arrondi à la référence d’un quart d’heure la plus proche. Par exemple, 2,25 heures, 3,5 heures.
      * Tout ce qui est supérieur à un jour est arrondi à la référence de jour la plus proche. Par exemple, 1 jour, 3 jours, 9 jours.
* **`bml`** (facultatif, nombre) : durée des références de l’arrondi selon le format de l’argument `fmt`. Par exemple, si l’argument `fmt` est sur `"s"` et que cet argument est défini sur `2`, la valeur renvoyée est arrondie à la référence de deux secondes la plus proche. Si l’argument `fmt` est sur `"m"` et que cet argument est défini sur `0.5`, la valeur renvoyée est arrondie à la référence d’une demi-minute la plus proche.
* **`rte`** (facultatif, chaîne) : chaîne d’événements Analytics délimitée par des virgules qui supprime ou annule le minuteur. La valeur par défaut est nulle.

L’appel de cette méthode renvoie un entier représentant le temps écoulé entre l’événement de démarrage du minuteur et l’événement d’arrêt du minuteur au format souhaité.

## Exemples d’appels

### Exemple 1

Le code suivant…

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

…est configuré pour agir de la manière suivante :

* Le minuteur démarre lorsque s.events contient event1.
* Le minuteur redémarre chaque fois que s.events contient event1.
* Le minuteur s’arrête lorsque s.events contient event2.
* Le minuteur se réinitialise (c’est-à-dire qu’il passe à 0 seconde) chaque fois que s.events contient event2.
* Le minuteur se réinitialise également lorsque s.events contient event3 OU si le visiteur ferme son navigateur.
* Lorsqu’un temps réel entre event1 et event2 est enregistré, le plug-in définit eVar1 sur le nombre de secondes entre les deux événements configurés, arrondi à la référence de deux secondes la plus proche (par exemple 0 seconde, 2 secondes, 4 secondes, 10 secondes, 184 secondes, etc.).
* Si s.events contient event2 avant le démarrage du minuteur, eVar1 ne sera pas du tout défini.

### Exemple 2

Le code suivant…

```js
s.eVar1 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

…est configuré pour agir de la manière suivante :

* Le minuteur démarre lorsque s.events contient event1.
* Le minuteur ne redémarre PAS chaque fois que s.events contient event1, mais le minuteur d’origine continue de fonctionner.
* Le minuteur ne s’arrête PAS lorsque s.events contient event2, mais le plug-in enregistre le temps écoulé depuis l’enregistrement du paramètre event1 d’origine.
* Le minuteur est stocké dans un cookie appelé « s_20 ».
* Le minuteur ne se réinitialise que lorsque s.events contient event3 OU si 20 jours se sont écoulés depuis le démarrage du minuteur.
* Lorsqu’un temps entre event1 (paramètre d’origine) et event2 est enregistré, le plug-in définit eVar1 sur le nombre d’heures entre les deux événements configurés, arrondi à la référence d’une heure et demie la plus proche (par exemple, 0 heure, 1,5 heure, 3 heures, 7,5 heures, 478,5 heures, etc.).

### Exemple 3

Le code suivant…

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true);
```

…produit des résultats similaires à ceux du premier exemple ci-dessus. Toutefois, la valeur d’eVar1 est renvoyée en secondes, minutes, heures ou jours, selon la durée finale du minuteur.  En outre, le minuteur expirera un jour après son premier paramétrage et non au moment où le visiteur ferme son navigateur.

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.1 (26 mai 2018)

* Comprend les modifications apportées à la nouvelle version du plug-in `formatTime`.

### 2.0 (6 avril 2018)

* Réécriture/réanalyse complète du plug-in.
