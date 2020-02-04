---
title: ' apl (appendToList)'
description: Ajoutez des valeurs aux variables qui prennent en charge plusieurs valeurs.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe : apl (appendToList)

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `apl` module externe vous permet d’ajouter en toute sécurité de nouvelles valeurs à des variables délimitées par des listes, telles que `events`, `linkTrackVars`, variables de liste, etc.

* Si la valeur que vous souhaitez ajouter n’existe pas dans la variable, le code ajoute la valeur à la fin de la chaîne.
* Si la valeur que vous souhaitez ajouter existe déjà dans la variable, ce module externe ne modifie pas la valeur. Cette fonctionnalité permet à votre implémentation d’éviter les valeurs en double.
* Si la variable que vous souhaitez ajouter est vide, le module externe la définit sur la nouvelle valeur.

Adobe recommande d’utiliser ce module externe si vous souhaitez ajouter de nouvelles valeurs aux variables existantes qui contiennent une chaîne de valeurs délimitées. Ce module externe n’est pas nécessaire si vous préférez concaténer des chaînes pour des variables contenant des valeurs délimitées.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Si ce n’est déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser APL (Ajouter à la liste)
1. Enregistrez et publiez les modifications apportées à la règle.

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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `apl` méthode utilise les arguments suivants :

* **`lv`**(obligatoire, chaîne) : Variable qui contient une liste délimitée d’éléments à laquelle ajouter une nouvelle valeur
* **`vta`**(obligatoire, chaîne) : Liste délimitée par des virgules des nouvelles valeurs à ajouter à la valeur de l’`lv`argument.
* **`d1`**(facultatif, chaîne) : Délimiteur utilisé pour séparer les valeurs individuelles déjà contenues dans l’`lv`argument.  La valeur par défaut est une virgule (`,`) lorsqu’elle n’est pas définie.
* **`d2`**(facultatif, chaîne) : Délimiteur de sortie. La valeur par défaut est la même que`d1`lorsqu’elle n’est pas définie.
* **`cc`**(facultatif, booléen) : Indicateur qui indique si une vérification sensible à la casse est utilisée. Si`true`vous le souhaitez, la vérification de duplication est sensible à la casse. Si elle est`false`ou non définie, la vérification de duplication n’est pas sensible à la casse. Par défaut,`false`.

La `apl` méthode renvoie la valeur de l’ `lv` argument plus les valeurs non dupliquées de l’ `vta` argument.

## Exemples d’appels

### Exemple n° 1

Si la variable...

```js
s.events = "event22,event24";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.apl(s.events, "event23");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event24,event23";
```

### Exemple n° 2

Si la variable...

```js
s.events = "event22,event23";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.apl(s.events, "event23");
```

...la valeur finale de s.events sera toujours :

```js
s.events = "event22,event23";
```

Dans cet exemple, l’appel apl n’a apporté aucune modification à s.events, car s.events contenait déjà &quot;event23&quot;.

### Exemple n° 3

Si la variable...

```js
s.events = ""; //blank value
```

...et le code suivant s&#39;exécute...

```js
s.events = s.apl(s.events, "event23");
```

... la valeur finale de s.events sera...

```js
s.events = "event23";
```

### Exemple n° 4

Si la variable...

```js
s.prop4 = "hello|people";
```

...et le code suivant s&#39;exécute...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...la valeur finale de s.prop4 sera toujours...

```js
s.prop4 = "hello|people";
```

...mais la valeur finale de s.eVar5 sera

```js
s.eVar5 = "hello|people|today";
```

N’oubliez pas que le module externe renvoie uniquement une valeur ; il ne &quot;réinitialise&quot; pas nécessairement la variable transmise par le biais de l’argument lv.

### Exemple n° 5

Si la variable...

```js
s.prop4 = "hello|people";
```

...et le code suivant s&#39;exécute...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... la valeur finale de s.prop4 sera...

```js
s.prop4 = "hello|people,today";
```

Veillez à ce que le délimiteur reste cohérent entre ce qui se trouve dans la valeur de l’argument lv et ce qui se trouve dans les arguments d1/d2.

### Exemple n° 6

Si la variable...

```js
s.events = "event22,event23";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23,EVentT23";
```

Bien que cet exemple ne soit pas pratique, il montre la nécessité d’être prudent lors de l’utilisation de l’indicateur sensible à la casse.

### Exemple n° 7

Si la variable...

```js
s.events = "event22,event23";
```

...et le code suivant s&#39;exécute...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...la valeur finale de s.events sera :

```js
s.events = "event22,event23,event24,event25");
```

Le module externe n’ajoute pas &quot;event23&quot; à s.events, car il existe déjà dans s.events.  Cependant, il ajoute event24 et event25 à s.events car aucun des deux n’était auparavant contenu dans s.events.

### Exemple n° 8

Si la variable...

```js
s.linkTrackVars = "events,eVar1";
```

...et le code suivant s&#39;exécute...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...la valeur finale de s.linkTrackVars sera :

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Les trois derniers arguments (c.-à-d. &quot;,&quot;, &quot;,&quot;, false) à la fin de cet appel d’appel ne sont pas nécessaires, mais ne nuisent pas non plus à &quot;quoi que ce soit&quot; en étant définies puisqu’elles correspondent aux valeurs d’argument par défaut.

### Exemple n° 9

Si la variable...

```js
s.events = "event22,event24";
```

...et le code suivant s&#39;exécute...

```js
s.apl(s.events, "event23");
```

...la valeur finale de s.events sera toujours :

```js
s.events = "event22,event24";
```

L’exécution du plug-in tout seul (sans affecter la valeur renvoyée à une variable) ne &quot;réinitialise&quot; pas en fait la variable transmise par l’intermédiaire de l’argument lv.

### Exemple n° 10

Si la variable...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...et le code suivant s&#39;exécute...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... la valeur finale de s.list2 sera :

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Etant donné que les deux arguments de délimiteur sont différents, la valeur transmise sera délimitée par le premier argument de délimiteur (&quot;|&quot;), puis associée par le second argument de délimiteur (&quot;-&quot;).

## Historique des versions

### 3.2 (25 septembre 2019)

* Correction de problèmes de compatibilité avec les `apl` appels utilisant des versions antérieures du module externe
* Suppression des avertissements de la console pour réduire la taille
* Ajout de `inList 2.1`

### 3.1 (22 avril 2018)

* `d2` est maintenant défini par défaut sur la valeur de l’ `d1` argument lorsqu’il n’est pas défini

### 3.0 (16 avril 2018)

* Réanalyse/réécriture complète du module externe
* Ajout de la vérification avancée des erreurs
* L’ `vta` argument accepte désormais plusieurs valeurs simultanément.
* Ajout de l’ `d2` argument pour formater la valeur renvoyée
* Modification de l’ `cc` argument en booléen

### 2.5 (18 février 2016)

* Utilise désormais la `inList` méthode de traitement de comparaison

### 2.0 (26 janvier 2016)

* `d` (Délimiteur) est désormais facultatif (virgule par défaut).
* `u` (Indicateur de respect de la casse) est désormais facultatif (non-respect de la casse par défaut)
* Quel que soit l’argument `u` (indicateur de respect de la casse), le plug-in n’ajoute plus de valeur à une liste si la valeur existe déjà dans la liste.