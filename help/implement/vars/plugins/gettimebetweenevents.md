---
title: getTimeBetweenEvents
description: Permet de mesurer le temps qui s’écoule entre deux événements.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 100%

---


# Plug-in Adobe : getTimeBetweenEvents

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getTimeBetweenEvents` vous permet de suivre le temps écoulé entre deux événements Analytics, y compris les événements de panier et personnalisés. Il s’avère utile pour effectuer le suivi du temps nécessaire à l’achèvement d’un processus de passage en caisse ou de tout autre processus que vous souhaitez mesurer. Ce plug-in n’est pas nécessaire si vous ne disposez pas de processus de conversion dont vous souhaitez mesurer la durée.

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
   * Type d’action : initialisation de getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getTimeBetweenEvents` utilise les arguments suivants :

* **`ste`** (obligatoire, chaîne) : événements de démarrage du minuteur. Chaîne d’événements Analytics délimitée par des virgules permettant de « démarrer le minuteur ».
* **`rt`** (obligatoire, booléen) : option de redémarrage du minuteur. Définissez cet argument sur `true` si vous souhaitez redémarrer le minuteur chaque fois que la variable `events` contient un événement de démarrage du minuteur. Définissez-le sur `false` si vous ne souhaitez pas que le minuteur redémarre lorsqu’il détecte un événement de démarrage du minuteur.
* **`stp`** (obligatoire, chaîne) : événements d’arrêt du minuteur. Chaîne d’événements Analytics délimitée par des virgules permettant d’« arrêter le minuteur ».
* **`res`** (obligatoire, booléen) : option de réinitialisation du minuteur. Définissez cet argument sur `true` si vous souhaitez enregistrer le temps depuis le démarrage du minuteur ET réinitialiser le minuteur après son arrêt. Définissez-le sur `false` si vous souhaitez enregistrer le temps sans arrêter le minuteur. S’il est défini sur `false`, le minuteur continue de fonctionner après que la variable events a enregistré un événement d’arrêt.
   > [!TIP] Si vous définissez cet argument sur `false`, il est vivement recommandé de définir l’argument `rte` ci-dessous.
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
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
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
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
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
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

…produit des résultats similaires à ceux du premier exemple ci-dessus. Toutefois, la valeur d’eVar1 est renvoyée en secondes, minutes, heures ou jours, selon la durée finale du minuteur.  En outre, le minuteur expirera un jour après son premier paramétrage et non au moment où le visiteur ferme son navigateur.

## Historique des versions

### 2.1 (26 mai 2018)

* Comprend les modifications apportées à la nouvelle version du plug-in `formatTime`.

### 2.0 (6 avril 2018)

* Réécriture/réanalyse complète du plug-in.
