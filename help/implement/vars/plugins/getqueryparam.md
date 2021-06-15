---
title: getQueryParam
description: Permet d’extraire la valeur du paramètre de chaîne de requête d’une URL.
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: 5a087087c8f54650173391bd7766bfdfd12ccb7e
workflow-type: ht
source-wordcount: '918'
ht-degree: 100%

---

# Plug-in Adobe : getQueryParam

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getQueryParam` vous permet d’extraire la valeur de tout paramètre de chaîne de requête contenu dans une URL. Il est utile pour extraire des codes de campagne, internes et externes, provenant des URL de page d’entrée. Il convient également pour l’extraction de termes de recherche ou d’autres paramètres de chaîne de requête.

Ce plug-in fournit des fonctionnalités puissantes pour analyser des URL complexes, notamment les hachages et les URL contenant plusieurs paramètres de chaîne de requête. Si vous avez uniquement besoin de paramètres de chaîne de requête simples, Adobe recommande d’utiliser les fonctionnalités de paramètre d’URL dans Launch ou la méthode [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluse dans AppMeasurement.

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
   * Type d’action : initialisation de getQueryParam
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getQueryParam` utilise les arguments suivants :

* **`qsp`** (obligatoire) : liste, délimitée par des virgules, de paramètres de chaîne de requête à rechercher dans l’URL. Elle n’est pas sensible à la casse.
* **`de`** (facultatif) : délimiteur à utiliser si plusieurs paramètres de chaîne de requête correspondent. Valeur par défaut définie sur une chaîne vide.
* **`url`** (facultatif) : URL, chaîne ou variable personnalisée à partir de laquelle extraire les valeurs des paramètres de chaîne de requête. La valeur par défaut est `window.location`.

L’appel de cette méthode renvoie une valeur en fonction des arguments ci-dessus et de l’URL :

* Si aucun paramètre de chaîne de requête correspondant n’est trouvé, la méthode renvoie une chaîne vide.
* Si un paramètre de chaîne de requête correspondant est trouvé, la méthode renvoie la valeur de ce paramètre.
* Si un paramètre de chaîne de requête correspondant est trouvé mais que la valeur est vide, la méthode renvoie `true`.
* Si plusieurs paramètres de chaîne de requête correspondants sont trouvés, la méthode renvoie une chaîne dont chaque valeur de paramètre est délimitée par la chaîne dans l’argument `de`.

## Exemples d’appels

### Exemple 1

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1
```

Le code suivant définit s.campaign sur « trackingcode1 » :

```js
s.campaign=s.getQueryParam('cid');
```

### Exemple 2

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur « trackingcode1:123456 » :

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Exemple 3

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur « trackingcode1123456 » :

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Exemple 4

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

Le code suivant définit s.campaign sur « 123456 » :

```js
s.campaign=s.getQueryParam('ecid');
```

### Exemple 5

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur « 123456 » :

```js
s.campaign=s.getQueryParam('ecid');
```

**Remarque :** le plug-in remplace l’URL du caractère de hachage de la vérification par un point d’interrogation si ce dernier n’existe pas.  Si l’URL contient un point d’interrogation placé avant le caractère de hachage, le plug-in remplace l’URL du caractère de hachage de la vérification par une esperluette.

### Exemple 6

Si l’URL actuelle est la suivante…

```js
http://www.abc123.com/
```

…et si la variable s.testURL est définie comme suit :

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

Le code suivant ne définit pas du tout s.campaign :

```js
s.campaign=s.getQueryParam('cid');
```

Cependant, le code suivant définit s.campaign sur « trackingcode1 » :

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Remarque :** le troisième paramètre peut être n’importe quelle chaîne/variable que le code utilisera pour rechercher les paramètres de chaîne de requête dans

Le code suivant définit s.eVar2 sur « 123456|trackingcode1|true|300 » :

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* La valeur de 123456 provient du paramètre ecid de la variable s.testURL.
* La valeur de trackingcode1 provient du paramètre cid de la variable s.testURL.
* La valeur de true provient de l’existence (mais pas de la valeur) du paramètre d’emplacement après le caractère de hachage dans la variable s.testURL.

La valeur de 300 provient de la valeur du paramètre pos de la variable s.testURL.

## Historique des versions

### 4.0.1 (26 mars 2021)

* Mise à jour du problème en raison duquel le statut non défini était renvoyé au lieu de &quot;&quot; si le paramètre de requête n’était pas présent dans la chaîne de requête.

### 4.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.
* Suppression des dépendances sur pt plug-in.

### 3.3 (24 septembre 2019)

* Contournement d’une logique inutile pour réduire la taille du code.

### 3.2 (15 mai 2018)

* Déplacement des fonctions `findParameterValue` et `getParameterValue` dans la fonction `getQueryParam`.

### 3.1 (10 mai 2018)

* Correction d’un problème lié à la récupération de paramètres de chaîne de requête sans valeur.

### 3.0 (16 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Fonctions d’assistance renommées en `findParameterValue` et `getParameterValue` à des fins de lisibilité.
* Suppression de la nécessité d’ajouter un argument pour rechercher les paramètres contenus dans le hachage de l’URL.

### 2.5 (8 janvier 2016)

* Compatible avec le code H et AppMeasurement (nécessite `s.pt` avec AppMeasurement).

### 2,4

* Ajout du paramètre `h`, permettant au code de rechercher les paramètres de chaîne de requête trouvés après le caractère de hachage (`#`).

### 2,3

* Correction d’un problème de régression où le plug-in ne fonctionnait que lorsque le hachage se trouvait après le code de suivi.

### 2,2

* Suppression des caractères de hachage (et de tout ce qui suit) contenus dans la valeur renvoyée.

### 2,1

* Compatible avec le code H.10
