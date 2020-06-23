---
title: apl (appendToList)
description: Permet d’ajouter des valeurs aux variables qui prennent en charge plusieurs valeurs.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : apl (appendToList)

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `apl` vous permet d’ajouter en toute sécurité de nouvelles valeurs à des variables délimitées par, comme [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) et d’autres.

* Si la valeur que vous souhaitez ajouter n’existe pas dans la variable, le code ajoute la valeur à la fin de la chaîne.
* Si la valeur que vous souhaitez ajouter existe déjà dans la variable, ce plug-in ne modifie pas la valeur. Cette fonctionnalité permet à votre mise en œuvre d’éviter les valeurs en double.
* Si la variable que vous souhaitez ajouter est vide, le plug-in la définit sur la nouvelle valeur.

Adobe recommande d’utiliser ce plug-in si vous souhaitez ajouter de nouvelles valeurs aux variables existantes qui contiennent une chaîne de valeurs délimitées. Ce plug-in n’est pas nécessaire si vous préférez concaténer des chaînes pour des variables contenant des valeurs délimitées.

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
   * Type d’action : initialisation d’APL (Append To List)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `apl` utilise les arguments suivants :

* **`lv`** (obligatoire, chaîne) : variable qui contient une liste délimitée d’éléments à laquelle ajouter une nouvelle valeur.
* **`vta`** (obligatoire, chaîne) : liste délimitée par des virgules indiquant la ou les nouvelles valeurs à ajouter à la valeur de l’argument `lv`.
* **`d1`** (facultatif, chaîne) : délimiteur utilisé pour séparer les valeurs individuelles déjà contenues dans l’argument `lv`.  La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`d2`** (facultatif, chaîne) : délimiteur de sortie. La valeur par défaut est la même que celle de `d1` lorsqu’elle n’est pas définie.
* **`cc`** (facultatif, booléen) : indicateur précisant si une vérification sensible à la casse est utilisée. Si la valeur est définie sur `true`, la vérification de duplication est sensible à la casse. Si elle est définie sur `false` ou non définie, la vérification de duplication n’est pas sensible à la casse. La valeur par défaut est `false`.

La méthode `apl` renvoie la valeur de l’argument `lv` plus toutes les valeurs non dupliquées de l’argument `vta`.

## Exemples d’appels

### Exemple 1

Si…

```js
s.events = "event22,event24";
```

…et que le code suivant s’exécute…

```js
s.events = s.apl(s.events, "event23");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event24,event23";
```

### Exemple 2

Si…

```js
s.events = "event22,event23";
```

…et que le code suivant s’exécute…

```js
s.events = s.apl(s.events, "event23");
```

…alors la valeur finale de s.events reste :

```js
s.events = "event22,event23";
```

Dans cet exemple, l’appel apl n’a apporté aucune modification à s.events, car cette variable contenait déjà event23.

### Exemple 3

Si…

```js
s.events = ""; //blank value
```

…et que le code suivant s’exécute…

```js
s.events = s.apl(s.events, "event23");
```

…alors la valeur finale de s.events est…

```js
s.events = "event23";
```

### Exemple 4

Si…

```js
s.prop4 = "hello|people";
```

…et que le code suivant s’exécute…

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

…alors la valeur finale de s.prop4 reste…

```js
s.prop4 = "hello|people";
```

…mais la valeur finale de s.eVar5 est :

```js
s.eVar5 = "hello|people|today";
```

Pour rappel, le plug-in renvoie uniquement une valeur. Il ne « réinitialise » pas nécessairement la variable transmise par le biais de l’argument lv.

### Exemple 5

Si…

```js
s.prop4 = "hello|people";
```

…et que le code suivant s’exécute…

```js
s.prop4 = s.apl(s.prop4, "today");
```

…alors la valeur finale de s.prop4 est…

```js
s.prop4 = "hello|people,today";
```

Veillez à ce que le délimiteur reste cohérent entre la valeur de l’argument lv et celle des arguments d1/d2.

### Exemple 6

Si…

```js
s.events = "event22,event23";
```

…et que le code suivant s’exécute…

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,EVentT23";
```

Bien que cet exemple ne soit pas concret, il démontre la nécessité de faire preuve de prudence lors de l’utilisation de l’indicateur sensible à la casse.

### Exemple 7

Si…

```js
s.events = "event22,event23";
```

…et que le code suivant s’exécute…

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

…alors la valeur finale de s.events est :

```js
s.events = "event22,event23,event24,event25");
```

Le plug-in n’ajoute pas event23 à s.events, car il s’y trouve déjà.  Cependant, il ajoute event24 et event25 à s.events car ni l’un ni l’autre n’y figurait auparavant.

### Exemple 8

Si…

```js
s.linkTrackVars = "events,eVar1";
```

…et que le code suivant s’exécute…

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

…alors la valeur finale de s.linkTrackVars est :

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Les trois derniers arguments (c’est-à-dire &quot;,&quot;, &quot;,&quot;, false) à la fin de cet appel apl ne sont pas nécessaires, mais leur définition ne présente aucun inconvénient puisqu’ils correspondent aux valeurs d’argument par défaut.

### Exemple 9

Si…

```js
s.events = "event22,event24";
```

…et que le code suivant s’exécute…

```js
s.apl(s.events, "event23");
```

…alors la valeur finale de s.events reste :

```js
s.events = "event22,event24";
```

Exécuter le plug-in seul (sans attribuer la valeur renvoyée à une variable) ne « réinitialise » pas réellement la variable transmise par le biais de l’argument lv.

### Exemple 10

Si…

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

…et que le code suivant s’exécute…

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

…alors la valeur finale de s.list2 est…

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Comme les deux arguments du délimiteur sont différents, la valeur transmise sera délimitée par le premier argument du délimiteur (« | ») et ensuite associée au second argument du délimiteur (« - »).

## Historique des versions

### 3.2 (25 septembre 2019)

* Correction de problèmes de compatibilité avec les appels `apl` qui utilisaient d’anciennes versions du plug-in.
* Suppression des avertissements sur la console pour en réduire la taille.
* Ajout de `inList 2.1`.

### 3.1 (22 avril 2018)

* L’argument `d2` prend désormais par défaut la valeur de l’argument `d1` lorsqu’il n’est pas défini.

### 3.0 (16 avril 2018)

* Réanalyse/réécriture complète du plug-in.
* Ajout d’une vérification avancée des erreurs.
* L’argument `vta` accepte désormais plusieurs valeurs en même temps.
* Ajout de l’argument `d2` pour formater la valeur renvoyée.
* Modification de l’argument `cc` en une valeur booléenne.

### 2.5 (18 février 2016)

* Utilisation de la méthode `inList` pour le traitement des comparaisons.

### 2.0 (26 janvier 2016)

* Argument `d` (délimiteur) désormais facultatif (par défaut, une virgule).
* Argument `u` (indicateur de respect de la casse) désormais facultatif (par défaut, non-respect de la casse).
* Quel que soit l’argument `u` (indicateur de respect de la casse), le plug-in n’ajoute plus de valeur à une liste si elle y figure déjà.