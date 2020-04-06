---
title: formatTime
description: Permet de convertir un nombre de secondes en son équivalent en minutes, heures, etc.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : formatTime

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `formatTime` vous permet de prendre un nombre quelconque de secondes et de les restituer dans un format condensé, en les arrondissant à une valeur de référence souhaitée. Adobe recommande d’utiliser ce plug-in si vous souhaitez saisir une valeur de temps en secondes et la convertir dans un format condensé (minutes, jours ou semaines, par exemple). Ce plug-in n’est pas nécessaire si vous ne souhaitez pas condenser les valeurs exprimées en secondes dans un format temporel arrondi.

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
   * Type d’action : initialisation de formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `formatTime` utilise les arguments suivants :

* **`ns`** (obligatoire, entier) : nombre de secondes à convertir ou à formater
* **`tf`** (facultatif, chaîne) : type de format dans lequel restituer les secondes. Par défaut, il s’agit des secondes.
   * Définissez cette variable sur `"d"` si vous souhaitez que le temps soit exprimé en jours (arrondi par défaut à la référence d’un quart de jour la plus proche).
   * Définissez cette variable sur `"h"` si vous souhaitez que le temps soit exprimé en heures (arrondi par défaut à la référence d’un quart d’heure la plus proche).
   * Définissez cette variable sur `"m"` si vous souhaitez que le temps soit exprimé en minutes (arrondi par défaut à la référence d’une demi-minute la plus proche).
   * Définissez cette variable sur `"s"` si vous souhaitez que le temps soit exprimé en secondes (arrondi par défaut à la référence de cinq secondes la plus proche).
* **`bml`** (facultatif, nombre) : durée des références de l’arrondi. Par défaut, les références figurant dans l’argument `tf`.

La méthode renvoie le nombre de secondes formatées à l’aide de l’unité spécifiée dans l’argument `tf`. Si l’argument `tf` n’est pas défini :

* Tout ce qui est inférieur à une minute est arrondi à la référence de cinq secondes la plus proche.
* Tout ce qui se situe entre une minute et une heure est arrondi à la référence d’une demi-minute la plus proche.
* Tout ce qui se situe entre une heure et un jour est arrondi à la référence d’un quart d’heure la plus proche.
* Tout ce qui est supérieur à un jour est arrondi à la référence de jour la plus proche.

## Exemples

### Exemple 1

Le code suivant…

```js
s.eVar1 = s.formatTime(38242);
```

…définit s.eVar1 sur « 10,5 heures ».

L’argument transmis, soit 38 242 secondes, équivaut à 10 heures, 37 minutes et 22 secondes.  Comme l’argument tf n’est pas défini dans cet appel et que le nombre de secondes transmises se situe entre une heure et une journée, le plug-in renvoie le nombre de secondes converties à la référence d’un quart d’heure la plus proche.

### Exemple 2

Le code suivant…

```js
s.eVar1 = s.formatTime(38250);
```

...définit s.eVar1 sur « 10,75 heures ».
L’argument transmis, soit 38 250 secondes, équivaut à 10 heures, 37 minutes et 30 secondes.  Dans ce cas, l’arrondissement du nombre de secondes transmises à la référence d’un quart d’heure la plus proche définit la valeur finale sur 10,75 heures.

### Exemple 3

Le code suivant…

```js
s.eVar1 = s.formatTime(38242, "m");
```

…définit s.eVar1 sur « 637,5 minutes ».

Dans ce cas, l’argument « m » force le plug-in à convertir les secondes à la référence d’une demi-minute la plus proche.

### Exemple 4

Le code suivant…

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

…définit s.eVar1 sur « 640 minutes ».

La valeur de l’argument tf (« m ») force le plug-in à convertir les secondes en minutes, mais la valeur de l’argument bml (20) force également le plug-in à arrondir la conversion en minutes à la référence de 20 minutes la plus proche.

### Exemple 5

Le code suivant…

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

…définit s.eVar1 sur « 126 secondes », qui est la référence de 2 secondes la plus proche de 125 secondes.

### Exemple 6

Le code suivant…

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

…définit s.eVar1 sur « 3 minutes », qui est la référence de 3 minutes la plus proche de 125 secondes.

### Exemple 7

Le code suivant…

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

…définit s.eVar1 sur « 2,4 minutes », qui est la référence de 2/5e de minute la plus proche (par exemple 0,4 = 2/5) de 145 secondes.

## Historique des versions

### 1.1 (21 mai 2018)

* Ajout de l’argument `bml` pour permettre une plus grande flexibilité au niveau de l’arrondi.

### 1.0 (15 avril 2018)

* Version initiale.
