---
title: getQueryParam
description: Extrayez la valeur du paramètre de chaîne de requête d’une URL.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Module externe Adobe : getQueryParam

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getQueryParam` module externe vous permet d’extraire la valeur de tout paramètre de chaîne de requête contenu dans une URL. Il est utile pour extraire des codes de campagne, internes et externes, des URL de page d’entrée. Elle est également utile lors de l’extraction de termes de recherche ou d’autres paramètres de chaîne de requête.

Ce plug-in fournit des fonctionnalités puissantes pour analyser des URL complexes, notamment des hachages et des URL contenant plusieurs paramètres de chaîne de requête. Si vous avez uniquement besoin de paramètres de chaîne de requête simples, Adobe recommande d’utiliser les fonctionnalités de paramètre d’URL dans Launch ou la `Util.getQueryParam` méthode incluse dans AppMeasurement.

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

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getQueryParam` méthode utilise les arguments suivants :

* **`qsp`**(obligatoire) : Liste délimitée par des virgules de paramètres de chaîne de requête à rechercher dans l’URL. Il n’est pas sensible à la casse.
* **`de`**(facultatif) : Délimiteur à utiliser si plusieurs paramètres de chaîne de requête correspondent. Valeur par défaut définie sur une chaîne vide.
* **`url`**(facultatif) : URL, chaîne ou variable personnalisée à partir de laquelle extraire les valeurs des paramètres de chaîne de requête. Par défaut,`window.location`.

L’appel de cette méthode renvoie une valeur en fonction des arguments ci-dessus et de l’URL :

* Si aucun paramètre de chaîne de requête correspondant n’est trouvé, la méthode renvoie une chaîne vide.
* Si un paramètre de chaîne de requête correspondant est trouvé, la méthode renvoie la valeur du paramètre de chaîne de requête.
* Si un paramètre de chaîne de requête correspondant est trouvé mais que la valeur est vide, la méthode renvoie `true`.
* Si plusieurs paramètres de chaîne de requête correspondants sont trouvés, la méthode renvoie une chaîne avec chaque valeur de paramètre délimitée par la chaîne dans l’ `de` argument.

## Exemples d’appels

### Exemple n° 1

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1
```

Le code suivant définit s.campaign sur &quot;trackingcode1&quot; :

```js
s.campaign=s.getQueryParam('cid');
```

### Exemple n° 2

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur &quot;trackingcode1:123456&quot; :

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Exemple n° 3

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur &quot;trackingcode1123456&quot; :

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Exemple n° 4

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

Le code suivant définit s.campaign sur &quot;123456&quot; :

```js
s.campaign=s.getQueryParam('ecid');
```

### Exemple n° 5

Si l’URL actuelle est la suivante :

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

Le code suivant définit s.campaign sur &quot;123456&quot;.

```js
s.campaign=s.getQueryParam('ecid');
```

**** Remarque : Le plug-in remplace l’URL du caractère de hachage de la vérification par un point d’interrogation si aucun point d’interrogation n’existe.  Si l&#39;URL contient un point d&#39;interrogation placé avant le caractère de hachage, le module remplace l&#39;URL vers le caractère de hachage de Check par une esperluette ;

### Exemple n° 6

Si l&#39;URL actuelle est la suivante...

```js
http://www.abc123.com/
```

...et si la variable s.testURL est définie comme suit :

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

Le code suivant ne définit pas du tout s.campaign :

```js
s.campaign=s.getQueryParam('cid');
```

Cependant, le code suivant définit s.campaign sur &quot;trackingcode1&quot; :

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**** Remarque : le troisième paramètre peut être n’importe quelle chaîne/variable que le code utilisera pour rechercher les paramètres de chaîne de requête dans

Le code suivant définit s.eVar2 sur &quot;123456|trackingcode1|true|300&quot; :

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* La valeur 123456 provient du paramètre ecid de la variable s.testURL.
* La valeur de trackingcode1 provient du paramètre cid dans la variable s.testURL
* La valeur de true provient de l’existence (mais pas de la valeur) du paramètre d’emplacement après le caractère de hachage dans la variable s.testURL.

La valeur 300 provient de la valeur du paramètre pos dans la variable s.testURL.

## Historique des versions

### 3.3 (24 septembre 2019)

* Contournement de la logique inutile pour réduire la taille du code

### 3.2 (15 mai 2018)

* Déplacement `findParameterValue` et `getParameterValue` fonctions dans la `getQueryParam` fonction

### 3.1 (10 mai 2018)

* Correction d’un problème lié à la capture de paramètres de chaîne de requête sans valeur.

### 3.0 (16 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).
* Les fonctions d’aide ont été renommées `findParameterValue` et `getParameterValue` à des fins de lisibilité.
* Suppression de la nécessité d’ajouter un argument pour rechercher les paramètres contenus dans le hachage d’URL

### 2.5 (8 janvier 2016)

* Compatible avec le code H et AppMeasurement (nécessite `s.pt` AppMeasurement).

### 2.4

* Ajout du `h` paramètre, permettant au code de rechercher les paramètres de chaîne de requête trouvés après le caractère de hachage (`#`)

### 2.3

* Correction d’un problème de régression en raison duquel le module externe ne fonctionnait que lorsque le hachage était présent après le code de suivi.

### 2.2

* Supprime maintenant les caractères de hachage (et tout ce qui suit) de la valeur renvoyée.

### 2.1

* Compatible avec le code H.10
