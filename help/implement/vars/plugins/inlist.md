---
title: inList
description: Permet de vérifier si une valeur est contenue dans une autre valeur délimitée par des caractères.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 87%

---

# Plug-in Adobe : inList

{{plug-in}}

Le plug-in `inList` vous permet de vérifier si une valeur existe déjà dans une chaîne délimitée ou un objet Array de JavaScript. Plusieurs autres plug-ins dépendent du plug-in `inList` pour fonctionner. Ce plug-in offre un avantage certain par rapport à la méthode `indexOf()` de JavaScript où vous ne trouvez pas de chaînes partielles. Par exemple, si vous avez utilisé ce plug-in pour vérifier `"event2"`, il ne correspondra pas à une chaîne contenant `"event25"`. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin de vérifier les valeurs dans des chaînes ou des tableaux délimités, ou si vous souhaitez utiliser votre propre logique `indexOf()`.

## Installation du module externe à l’aide du SDK Web ou de l’extension SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans le SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

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
   * Type d’action : initialisation d’inList
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `inList` renvoie une valeur booléenne selon ses entrées. Elle utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne ou tableau) : liste délimitée de valeurs ou objet Array de JavaScript à rechercher.
* **`vtc`** (obligatoire, chaîne) : valeur à rechercher.
* **`d`** (facultatif, chaîne) : délimiteur utilisé pour séparer les valeurs individuelles dans l’argument `lv`. La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`cc`** (facultatif, booléen) : si cet argument est défini sur `true` ou `1`, une vérification sensible à la casse est effectuée. S’il est défini sur `false` ou omis, une vérification non sensible à la casse est effectuée. La valeur par défaut est `false`.

Lʼappel de cette fonction renvoie la valeur `true` si une correspondance est trouvée, et `false` sʼil nʼy en a aucune.

## Exemples

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### v2.1 (26 septembre 2019)

* Ajout de la possibilité que l’argument `cc` ne soit pas une valeur booléenne. Par exemple, `1` est une valeur de vérification de la casse valide.

### v2.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).

### v1.01 (27 septembre 2017)

* Code optimisé pour réduire la taille

### v1.0 (2009)

* Version initiale.
