---
title: inList
description: Vérifiez si une valeur est contenue dans une autre valeur délimitée par des caractères.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Module externe Adobe :inList

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `inList` module externe vous permet de vérifier si une valeur existe déjà dans une chaîne délimitée ou dans un objet de tableau JavaScript. Plusieurs autres plug-ins dépendent du `inList` plug-in pour fonctionner. Ce plug-in fournit un avantage distinct par rapport à la méthode JavaScript `indexOf()` où vous ne trouvez pas de chaînes partielles. Par exemple, si vous avez utilisé ce plug-in pour vérifier `"event2"`, il ne correspondra pas à une chaîne contenant `"event25"`. Ce module externe n’est pas nécessaire si vous n’avez pas besoin de rechercher des valeurs dans des chaînes ou des tableaux délimités, ou si vous souhaitez utiliser votre propre `indexOf()` logique.

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
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `inList` méthode utilise les arguments suivants :

* **`lv`**(obligatoire, chaîne ou tableau) : Liste délimitée de valeurs ou objet de tableau JavaScript à rechercher
* **`vtc`**(obligatoire, chaîne) : La valeur à rechercher
* **`d`**(facultatif, chaîne) : Délimiteur utilisé pour séparer les valeurs individuelles dans l’`lv`argument. La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`cc`**(facultatif, booléen) : Si cette valeur est définie sur`true`, une vérification sensible à la casse est effectuée. Si la valeur est définie sur`false`ou omis, une vérification non sensible à la casse est effectuée. Par défaut,`false`.

L’appel de cette méthode renvoie `true` s’il trouve une correspondance et `false` s’il ne trouve pas de correspondance.

## Exemples d’appels

### Exemple n° 1

Si la variable...

```js
s.events="event22,event24";
```

...et le code suivant s&#39;exécute...

```js
if(s.inList(s.events,"event22"))
```

...l’instruction conditionnelle if sera vraie.

### Exemple n° 2

Si la variable...

```js
s.events="event22,event24";
```

...et le code suivant s&#39;exécute...

```js
if(s.inList(s.events,"event2"))
```

...l’instruction conditionnelle if sera false car l’appel inList n’a pas fait de correspondance exacte entre event2 et l’une des valeurs délimitées de s.events.

### Exemple n° 3

Si la variable...

```js
s.events="event22,event24";
```

...et le code suivant s&#39;exécute...

```js
if(!s.inList(s.events,"event23"))
```

...l’instruction conditionnelle if sera vraie car l’appel inList n’a pas fait de correspondance exacte entre event23 et l’une des valeurs délimitées de s.events (notez l’opérateur &quot;NOT&quot; au début de l’appel de variable inList).

### Exemple n° 4

Si la variable...

```js
s.events = "event22,event23";
```

...et le code suivant s&#39;exécute...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...l’instruction conditionnelle if sera false.  Bien que cet exemple ne soit pas pratique, il montre la nécessité d’être prudent lors de l’utilisation de l’indicateur sensible à la casse.

### Exemple n° 5

Si la variable...

```js
s.linkTrackVars = "events,eVar1";
```

...et le code suivant s&#39;exécute...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...l’instruction conditionnelle if sera false.  Valeur de l’argument d transmise à l’appel (c.-à-d. &quot;|&quot;) suppose que les valeurs individuelles dans s.linkTrackVars sont délimitées par un caractère barre verticale, alors qu&#39;en réalité, les valeurs sont délimitées par une virgule.  Dans ce cas, le plug-in tente de faire correspondre la valeur entière de s.linkTrackVars (c.-à-d. &quot;events,eVar1&quot;) et la valeur à rechercher (c.-à-d. &quot;eVar1&quot;).

## Historique des versions

### v2.1 (26 septembre 2019)

* Ajout de l’option permettant à l’ `cc` argument de ne pas être une valeur booléenne. Par exemple, `1` est une valeur de vérification de la casse valide.

### v2.0 (17 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).

### v1.01 (27 septembre 2017)

* Code optimisé pour réduire la taille

### v1.0 (2009)

* Version initiale.


