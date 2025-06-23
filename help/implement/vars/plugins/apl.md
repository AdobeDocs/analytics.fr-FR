---
title: apl (appendToList)
description: Permet d’ajouter des valeurs aux variables qui prennent en charge plusieurs valeurs.
feature: Appmeasurement Implementation
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 90%

---

# Plug-in Adobe : apl (appendToList)

{{plug-in}}

Le plug-in `apl` vous permet d’ajouter en toute sécurité de nouvelles valeurs à des variables délimitées par, comme [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) et d’autres.

* Si la valeur que vous souhaitez ajouter n’existe pas dans la variable, le code ajoute la valeur à la fin de la chaîne.
* Si la valeur que vous souhaitez ajouter existe déjà dans la variable, ce plug-in ne modifie pas la valeur. Cette fonctionnalité permet à votre mise en œuvre d’éviter les valeurs en double.
* Si la variable que vous souhaitez ajouter est vide, le plug-in la définit sur la nouvelle valeur.

Adobe recommande d’utiliser ce plug-in si vous souhaitez ajouter de nouvelles valeurs aux variables existantes qui contiennent une chaîne de valeurs délimitées. Ce plug-in n’est pas nécessaire si vous préférez concaténer des chaînes pour des variables contenant des valeurs délimitées.

## Installez le plug-in à l’aide de l’extension Web SDK ou Web SDK

Ce plug-in n’est pas encore pris en charge pour une utilisation dans le SDK Web.

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
   * Type d’action : initialisation d’APL (Append To List)
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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `apl` utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne) : variable qui contient une liste délimitée d’éléments à laquelle ajouter une nouvelle valeur.
* **`vta`** (obligatoire, chaîne) : liste délimitée par des virgules indiquant la ou les nouvelles valeurs à ajouter à la valeur de l’argument `lv`.
* **`d1`** (facultatif, chaîne) : délimiteur utilisé pour séparer les valeurs individuelles déjà contenues dans l’argument `lv`.  La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`d2`** (facultatif, chaîne) : délimiteur de sortie. La valeur par défaut est la même que celle de `d1` lorsqu’elle n’est pas définie.
* **`cc`** (facultatif, booléen) : indicateur précisant si une vérification sensible à la casse est utilisée. Si la valeur est définie sur `true`, la vérification de duplication est sensible à la casse. Si elle est définie sur `false` ou non définie, la vérification de duplication n’est pas sensible à la casse. La valeur par défaut est `false`.

La fonction `apl` renvoie la valeur de lʼargument `lv` plus toutes les valeurs non dupliquées de lʼargument `vta`.

## Exemples

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Historique des versions

### 4.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 3.2 (25 septembre 2019)

* Correction de problèmes de compatibilité avec les appels `apl` qui utilisaient d’anciennes versions du plug-in.
* Suppression des avertissements sur la console pour en réduire la taille.
* Ajout de `inList 2.1`.

### 3.1 (22 avril 2018)

* L’argument `d2` prend désormais par défaut la valeur de l’argument `d1` lorsqu’il n’est pas défini.

### 3.0 (16 avril 2018)

* Réanalyse/réécriture complète du plug-in.
* Ajout d’une vérification avancée des erreurs.
* L’argument `vta` accepte désormais plusieurs valeurs en même temps.
* Ajout de l’argument `d2` pour formater la valeur renvoyée.
* Modification de l’argument `cc` en une valeur booléenne.

### 2.5 (18 février 2016)

* Utilisation de la fonction `inList` pour le traitement des comparaisons.

### 2.0 (26 janvier 2016)

* Argument `d` (délimiteur) désormais facultatif (par défaut, une virgule).
* Argument `u` (indicateur de respect de la casse) désormais facultatif (par défaut, non-respect de la casse).
* Quel que soit l’argument `u` (indicateur de respect de la casse), le plug-in n’ajoute plus de valeur à une liste si elle y figure déjà.
