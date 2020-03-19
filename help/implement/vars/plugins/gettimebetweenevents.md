---
title: getTimeBetweenEvents
description: Mesurez la durée entre deux .
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getTimeBetweenEvents

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getTimeBetweenEvents` module externe vous permet d’effectuer le suivi de la durée entre deux  Analytics, y compris le panier d’achat et les  de personnalisés. Il s’avère utile pour effectuer le suivi du temps nécessaire à l’achèvement d’un processus de passage en caisse ou de tout autre processus que vous souhaitez mesurer. Ce module externe est inutile si vous ne souhaitez pas utiliser de processus de conversion pour mesurer le temps qu’ils prennent.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe   une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l&#39; [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Catalog] bouton
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si vous ne l’avez pas déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   *  : Core - Bibliothèque chargée (Haut de la page)
1. Ajouter une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialize getTimeBetweenEvents
1. Enregistrez et publiez les modifications apportées à la règle.

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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getTimeBetweenEvents` méthode utilise les arguments suivants :

* **`ste`** (obligatoire, chaîne) :  le du minuteur . Chaîne délimitée par des virgules du Analytics  à &quot; le minuteur&quot;.
* **`rt`** (obligatoire, booléen) : Redémarrez l’option du minuteur. Définissez cette variable sur `true` si vous souhaitez redémarrer le minuteur chaque fois que la `events` variable contient un de minuteur . Définissez sur `false` si vous ne souhaitez pas que le minuteur redémarre lorsqu’il voit un de minuteur .
* **`stp`** (obligatoire, chaîne) : Arrêtez le du minuteur. Chaîne délimitée par des virgules du Analytics qui &quot;arrête le minuteur&quot;.
* **`res`** (obligatoire, booléen) : Réinitialisez l’option du minuteur. Définissez sur `true` si vous souhaitez enregistrer l’heure depuis le démarrage du minuteur ET réinitialisez le minuteur après son arrêt. Définissez cette variable sur `false` si vous souhaitez enregistrer l’heure sans arrêter le minuteur. S’il est défini sur `false`, le minuteur continue à s’exécuter une fois que la variable  du a enregistré un  d’arrêt.
   > [!TIP] Si vous définissez cet argument sur `false`, il est vivement recommandé de définir l’ `rte` argument ci-dessous.
* **`cn`** (facultatif, chaîne) : Nom du cookie où est stockée l’heure du premier  du. Par défaut, `"s_tbe"`.
* **`etd`** (facultatif, entier) : Heure d’expiration du cookie en jours. Définissez cette option `0` pour qu’elle arrive à expiration à la fin de la session du navigateur. La valeur par défaut est 1 jour lorsqu’elle n’est pas définie.
* **`fmt`** (facultatif, chaîne) : Le format du temps de retour (par défaut, rien) du nombre de secondes
   * `"s"` pendant les secondes
   * `"m"` pendant quelques minutes
   * `"h"` pendant les heures
   * `"d"` pendant les jours
   * Lorsqu’elle n’est pas définie, le format de la valeur renvoyée est basé sur les règles suivantes :
      * Tout ce qui est inférieur à une minute est arrondi au repère de 5 secondes le plus proche. Par exemple, 10 secondes, 15 secondes
      * Tout ce qui se trouve entre une minute et une heure est arrondi au point de repère de 1/2 minute le plus proche. Par exemple, 30,5 minutes, 31 minutes
      * Tout ce qui se trouve entre une heure et une journée est arrondi au point de repère du quart d’heure le plus proche. Par exemple, 2,25 heures, 3,5 heures
      * Tout ce qui dépasse une journée est arrondi au point de référence le plus proche. Par exemple, 1 jour, 3 jours, 9 jours
* **`bml`** (facultatif, numéro) : Longueur du point de repère arrondi selon le format de l’ `fmt` argument. Par exemple, si l’ `fmt` argument est `"s"` et que cet argument est `2`, la valeur renvoyée est arrondie au repère de 2 secondes le plus proche. Si `fmt` l’argument est `"m"` et que cet argument est `0.5`, la valeur de retour est arrondie au point de repère le plus proche de la demi-minute.
* **`rte`** (facultatif, chaîne) : Chaîne délimitée par des virgules du Analytics qui supprime ou supprime le minuteur. La valeur par défaut est nulle.

L’appel de cette méthode renvoie un entier représentant la durée écoulée entre le du minuteur  et le  du minuteur d’arrêt au format souhaité.

## Exemples d’appels

### Exemple n° 1

Le code suivant...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...est configuré pour se comporter comme suit :

* Le minuteur s’lorsque s.contient la valeur1.
* Le minuteur redémarre chaque fois que s.contient 1
* Le minuteur s’arrête lorsque s.contient 2
* Le minuteur se réinitialise (c.-à-d. passe à 0 seconde) chaque fois que s. contient 2
* Le minuteur se réinitialise également lorsque s.contient 3 OU si le ferme son navigateur.
* Lorsqu’un temps réel entre 1 et 2 est enregistré, le plug-in définit eVar1 sur le nombre de secondes entre les deuxsecondes définies, arrondi au repère de 2 secondes le plus proche (par exemple 0 seconde, 2 secondes, 4 secondes, 10 secondes, 184 secondes, etc.).
* Si s.contient le 2 avant le démarrage du minuteur, l’eVar1 ne sera pas du tout définie.

### Exemple n° 2

Le code suivant...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...est configuré pour se comporter comme suit :

* Le minuteur s’lorsque s.contient la valeur1.
* Le minuteur NE redémarre PAS chaque fois que s. contient 1 ; le minuteur d’origine continue à fonctionner.
* Le minuteur ne s’arrête PAS lorsque s.contient 2, mais le plug-in enregistre l’heure depuis l’enregistrement du paramètre1 d’origine.
* Le minuteur est stocké dans un cookie appelé &quot;s_20&quot;.
* Le minuteur se réinitialise uniquement lorsque s.contient 3 OU si 20 jours se sont écoulés depuis le démarrage du minuteur.
* Lorsqu’un intervalle entre (l’original) 1 et le 2 est enregistré, le plug-in définit eVar1 sur le nombre d’heures entre les deuxheures définies, arrondi au point de référence de 1/2 heure le plus proche (par exemple, 0 heure, 1,5 heure, 3 heures, 7,5 heures, 478,5 heures, etc.).

### Exemple n° 3

Le code suivant...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...produira des résultats similaires à ceux du premier exemple ci-dessus; toutefois, la valeur d’eVar1 est renvoyée en secondes, minutes, heures ou jours, selon la durée finale du minuteur.  En outre, le minuteur expirera 1 jour après sa première définition au lieu de la fermeture du navigateur par le.

## Historique des versions

### 2.1 (26 mai 2018)

* Comprend les modifications apportées à la nouvelle version du `formatTime` module externe.

### 2.0 (6 avril 2018)

* Réécriture/réanalyse complète du module externe.
