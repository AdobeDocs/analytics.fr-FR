---
title: getQueryParam
description: Permet d’extraire la valeur du paramètre de chaîne de requête d’une URL.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 74%

---

# Plug-in Adobe : getQueryParam

{{plug-in}}

Le plug-in `getQueryParam` vous permet d’extraire la valeur de tout paramètre de chaîne de requête contenu dans une URL. Il est utile pour extraire des codes de campagne, internes et externes, provenant des URL de page d’entrée. Il convient également pour l’extraction de termes de recherche ou d’autres paramètres de chaîne de requête.

Ce plug-in fournit des fonctionnalités puissantes pour analyser des URL complexes, notamment les hachages et les URL contenant plusieurs paramètres de chaîne de requête. Si vous avez uniquement besoin de paramètres de chaîne de requête simples, Adobe recommande d’utiliser les fonctionnalités de paramètre d’URL à l’aide du SDK Web ou de l’extension Adobe Analytics ou de la variable [`Util.getQueryParam()`](../functions/util-getqueryparam.md) inclus dans AppMeasurement.

## Installation du module externe à l’aide de l’extension SDK Web

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK Web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** sur la gauche, puis cliquez sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** sur la gauche, puis cliquez sur le bouton **[!UICONTROL Catalogue]** tab
1. Recherchez et installez le **[!UICONTROL Plug-ins SDK Web courants]** extension .
1. Cliquez sur **[!UICONTROL Éléments de données]** sur la gauche, puis cliquez sur l’élément de données souhaité.
1. Définissez le nom de l’élément de données souhaité avec la configuration suivante :
   * Extension : Plug-ins SDK Web courants
   * Élément de données: `getQueryParam`
1. Définissez les paramètres de votre choix à droite.
1. Enregistrez et publiez les modifications sur l’élément de données.

## Installation manuelle du plug-in implémentant le SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans une mise en oeuvre manuelle du SDK Web.

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
   * Type d’action : initialisation de getQueryParam
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
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

La fonction `getQueryParam` utilise les arguments suivants :

* **`qsp`** (obligatoire) : liste, délimitée par des virgules, de paramètres de chaîne de requête à rechercher dans l’URL. Elle n’est pas sensible à la casse.
* **`de`** (facultatif) : délimiteur à utiliser si plusieurs paramètres de chaîne de requête correspondent. Valeur par défaut définie sur une chaîne vide.
* **`url`** (facultatif) : URL, chaîne ou variable personnalisée à partir de laquelle extraire les valeurs des paramètres de chaîne de requête. La valeur par défaut est `window.location`.

Lʼappel de cette fonction renvoie une valeur en fonction des arguments ci-dessus et de lʼURL :

* Si aucun paramètre de chaîne de requête correspondant nʼest trouvé, la fonction renvoie une chaîne vide.
* Si un paramètre de chaîne de requête correspondant est trouvé, la fonction renvoie la valeur de ce paramètre.
* Si un paramètre de chaîne de requête correspondant est trouvé mais que la valeur est vide, la fonction renvoie `true`.
* Si plusieurs paramètres de chaîne de requête correspondants sont trouvés, la fonction renvoie une chaîne dont chaque valeur de paramètre est délimitée par la chaîne dans lʼargument `de`.

## Exemples

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

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
