---
title: inList
description: Permet de vérifier si une valeur est contenue dans une autre valeur délimitée par des caractères.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : inList

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `inList` vous permet de vérifier si une valeur existe déjà dans une chaîne délimitée ou un objet Array de JavaScript. Plusieurs autres plug-ins dépendent du plug-in `inList` pour fonctionner. Ce plug-in offre un avantage certain par rapport à la méthode `indexOf()` de JavaScript où vous ne trouvez pas de chaînes partielles. Par exemple, si vous avez utilisé ce plug-in pour vérifier `"event2"`, il ne correspondra pas à une chaîne contenant `"event25"`. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin de vérifier les valeurs dans des chaînes ou des tableaux délimités, ou si vous souhaitez utiliser votre propre logique `indexOf()`.

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
   * Type d’action : initialisation d’inList
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
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `inList` utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne ou tableau) : liste délimitée de valeurs ou objet Array de JavaScript à rechercher.
* **`vtc`** (obligatoire, chaîne) : valeur à rechercher.
* **`d`** (facultatif, chaîne) : délimiteur utilisé pour séparer les valeurs individuelles dans l’argument `lv`. La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`cc`** (facultatif, booléen) : si cet argument est défini sur `true`, une vérification sensible à la casse est effectuée. S’il est défini sur `false` ou omis, une vérification non sensible à la casse est effectuée. La valeur par défaut est `false`.

L’appel de cette méthode renvoie la valeur `true` si une correspondance est trouvée, et `false` s’il n’y en a aucune.

## Exemples d’appels

### Exemple 1

Si…

```js
s.events="event22,event24";
```

…et que le code suivant s’exécute…

```js
if(s.inList(s.events,"event22"))
```

…alors l’instruction conditionnelle if est définie sur true.

### Exemple 2

Si…

```js
s.events="event22,event24";
```

…et que le code suivant s’exécute…

```js
if(s.inList(s.events,"event2"))
```

…alors l’instruction conditionnelle if est définie sur false car l’appel inList n’a pas établi de correspondance exacte entre event2 et l’une des valeurs délimitées de s.events.

### Exemple 3

Si…

```js
s.events="event22,event24";
```

…et que le code suivant s’exécute…

```js
if(!s.inList(s.events,"event23"))
```

…alors l’instruction conditionnelle if est définie sur true car l’appel inList n’a pas établi de correspondance exacte entre event23 et l’une des valeurs délimitées de s.events (notez l’opérateur « NOT » au début de l’appel de variable inList).

### Exemple 4

Si…

```js
s.events = "event22,event23";
```

…et que le code suivant s’exécute…

```js
if(s.inList(s.events,"EVenT23","",1))
```

…alors l’instruction conditionnelle if est définie sur false.  Bien que cet exemple ne soit pas concret, il démontre la nécessité de faire preuve de prudence lors de l’utilisation de l’indicateur sensible à la casse.

### Exemple 5

Si…

```js
s.linkTrackVars = "events,eVar1";
```

…et que le code suivant s’exécute…

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

…alors l’instruction conditionnelle if est définie sur false.  La valeur de l’argument d transmise à l’appel (c’est-à-dire « | ») laisse supposer que les valeurs individuelles dans s.linkTrackVars sont délimitées par une barre verticale, alors qu’en réalité, elles sont délimitées par une virgule.  Dans ce cas, le plug-in tente d’établir une correspondance entre la valeur totale de s.linkTrackVars (c’est-à-dire « events,eVar1 ») et la valeur à rechercher (c’est-à-dire « eVar1 »).

## Historique des versions

### v2.1 (26 septembre 2019)

* Ajout de la possibilité que l’argument `cc` ne soit pas une valeur booléenne. Par exemple, `1` est une valeur de vérification de la casse valide.

### v2.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).

### v1.01 (27 septembre 2017)

* Code optimisé pour réduire la taille

### v1.0 (2009)

* Version initiale.


