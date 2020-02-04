---
title: formatTime
description: Convertir un nombre de secondes en son équivalent en minutes, heures, etc.
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Module externe Adobe :formatTime

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `formatTime` module externe vous permet de prendre n’importe quel nombre de secondes et de les présenter sous forme de graphique, arrondi à la valeur de référence souhaitée. Adobe recommande d’utiliser ce module externe si vous souhaitez capturer une valeur de temps en secondes et la convertir au format de compartiment (minutes, jours ou semaines, par exemple). Ce plug-in n’est pas nécessaire si vous ne souhaitez pas regrouper des valeurs de seconde base dans un format arrondi dans le temps.

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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `formatTime` méthode utilise les arguments suivants :

* **`ns`**(obligatoire, entier) : Le nombre de secondes à convertir ou à formater
* **`tf`**(facultatif, chaîne) : Type de format dans lequel retourner les secondes ; par défaut, secondes
   * Définissez cette variable sur `"d"` si vous souhaitez que l’heure soit exprimée en jours (arrondie par défaut à la valeur de référence de 1/4 jour la plus proche).
   * Définissez cette variable sur `"h"` si vous souhaitez obtenir l’heure en heures (arrondie par défaut au taux de référence de 1/4 heure le plus proche).
   * Définissez cette valeur sur `"m"` si vous souhaitez que le temps soit en minutes (arrondi par défaut à la valeur de référence de 1/2 minute la plus proche).
   * Définissez cette valeur sur `"s"` si vous souhaitez que le temps soit en secondes (arrondi par défaut au repère de 5 secondes le plus proche).
* **`bml`**(facultatif, numéro) : Longueur des repères d’arrondi. Valeurs par défaut des repères répertoriés dans l&#39;`tf`argument

La méthode renvoie le nombre de secondes formatées à l’aide de l’unité spécifiée dans l’ `tf` argument. Si l’ `tf` argument n’est pas défini :

* Tout ce qui est inférieur à une minute est arrondi au repère de 5 secondes le plus proche
* Tout ce qui se trouve entre une minute et une heure est arrondi à la valeur de référence de 1/2 minute la plus proche
* Tout ce qui se trouve entre une heure et une journée est arrondi au point de référence du quart d’heure le plus proche.
* Tout élément supérieur à une journée est arrondi au point de référence du jour le plus proche

## Exemples

### Exemple n° 1

Le code suivant...

```js
s.eVar1 = s.formatTime(38242);
```

...définira s.eVar1 sur &quot;10,5 heures&quot;

L’argument transmis - 38 242 secondes - est égal à 10 heures, 37 minutes et 22 secondes.  Puisque l’argument tf n’est pas défini dans cet appel et que le nombre de secondes transmises est compris entre une heure et une journée, le module externe renvoie le nombre de secondes converties au repère de quart d’heure le plus proche.

### Exemple n° 2

Le code suivant...

```js
s.eVar1 = s.formatTime(38250);
```

...définit s.eVar1 sur &quot;10,75 heures&quot;. L’argument transmis - 38 250 secondes - est égal à 10 heures, 37 minutes et 30 secondes.  Dans ce cas, l’arrondissement du nombre de secondes transmises au repère de quart d’heure le plus proche définit la valeur finale sur 10,75 heures.

### Exemple n° 3

Le code suivant...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...définira s.eVar1 sur &quot;637,5 minutes&quot;

Dans ce cas, l’argument &quot;m&quot; force le plug-in à convertir les secondes en la valeur de référence de ½ minute la plus proche.

### Exemple n° 4

Le code suivant...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...définira s.eVar1 sur &quot;640 minutes&quot;

La valeur de l’argument tf (&quot;m&quot;) force le plug-in à convertir les secondes en minutes, mais la valeur de l’argument bml (20) force également le plug-in à arrondir la conversion minute au point de repère de 20 minutes le plus proche.

### Exemple n° 5

Le code suivant...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...définira s.eVar1 sur &quot;126 secondes&quot;, qui est la référence de 2 secondes la plus proche sur 125 secondes.

### Exemple n° 6

Le code suivant...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...définira s.eVar1 sur &quot;3 minutes&quot;, qui est la référence de 3 minutes la plus proche sur 125 secondes.

### Exemple n° 7

Le code suivant...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...définira s.eVar1 sur &quot;2,4 minutes&quot;, qui est l’indicateur de 2/5 minutes le plus proche (p. ex. 0,4 = 2/5) à 145 secondes

## Historique des versions

### 1.1 (21 mai 2018)

* Ajout de l’ `bml` argument pour permettre une plus grande flexibilité dans l’arrondi

### 1.0 (15 avril 2018)

* Version initiale.
