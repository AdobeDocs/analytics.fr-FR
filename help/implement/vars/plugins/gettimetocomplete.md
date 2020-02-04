---
title: getTimeToComplete
description: Mesurez le temps nécessaire pour terminer une tâche.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Module externe Adobe : getTimeToComplete

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getTimeToComplete` module externe effectue le suivi du temps nécessaire à un utilisateur pour terminer un processus sur un site. L’horloge commence lorsque l’ `start` action est appelée et se termine lorsque l’ `stop` action est appelée. Adobe conseille d’utiliser ce module externe s’il existe un flux de travail sur le site qui prend du temps et que vous souhaitez savoir combien de temps les visiteurs passent pour le terminer. Il n’est pas nécessaire d’utiliser ce plug-in si le processus sur votre site prend un court laps de temps (moins de 3 secondes), car la granularité est réduite à la seconde complète.

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getTimeToComplete` méthode utilise les arguments suivants :

* **`sos`**(facultatif, chaîne) : Définissez sur`"start"`le moment où vous souhaitez démarrer le minuteur. Définissez sur`"stop"`quand arrêter le minuteur. Par défaut,`"start"`.
* **`cn`**(facultatif, chaîne) : Nom du cookie pour stocker l’heure de début. Par défaut,`"s_gttc"`.
* **`exp`**(facultatif, entier) : Nombre de jours d’expiration du cookie (et du minuteur). Par défaut,`0`, ce qui représente la fin de la session du navigateur.

L’appel de cette méthode renvoie une chaîne qui contient le nombre de jours, d’heures, de minutes et/ou de secondes qu’il a fallu entre l’ `"start"` action et `"stop"` .

## Exemples d’appels

### Exemple n° 1

Utilisez ces appels pour déterminer le délai entre le moment où un visiteur commence le processus de passage en caisse et le moment où il effectue un achat.

Démarrez le minuteur lorsque le visiteur commence le passage en caisse :

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Arrêtez le minuteur lorsque le visiteur effectue l’achat et définissez prop1 sur la différence de temps entre arrêt et début :

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 capture le temps nécessaire pour terminer le processus d’achat.

### Exemple n° 2

Si vous souhaitez que plusieurs minuteries soient exécutées simultanément (pour mesurer différents processus), vous devez définir manuellement l’argument du cookie cn.  Si, par exemple, vous souhaitez mesurer le temps nécessaire à l’exécution d’un achat, définissez le code suivant...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...mais si vous souhaitez également mesurer (en même temps) le temps nécessaire au remplissage d’un formulaire d’inscription, vous devez également exécuter le code suivant :

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

Dans le deuxième exemple, event1 est destiné à capturer le début d’un processus d’enregistrement qui peut prendre jusqu’à 7 jours pour être terminé, quelle que soit la raison, et event2 est destiné à capturer la fin de l’enregistrement.  s.prop2 capture le temps nécessaire pour terminer le processus d’enregistrement

## Historique des versions

### 3.1 (30 septembre 2019)

* Ajout d’une logique qui requiert une valeur &quot;start&quot; ou &quot;stop&quot; dans le premier argument.  Toutes les autres valeurs transmises empêchent l’exécution du module externe.
* Mise à jour `inList 2.0` du module externe vers `inList 2.1`.

### 3.0 (23 août 2018)

* Mise à jour du `formatTime v1.0` module externe vers `formatTime v1.1`.

### 3.0 (17 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).
* Correction de bogues mineurs.

### 21 juin 2016)

* Suppression de la dépendance sur le `p_fo` module externe.
* Ajout de la compatibilité avec le code H et AppMeasurement.
* Ajout de la journalisation de la console.
