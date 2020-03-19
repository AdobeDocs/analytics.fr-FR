---
title: getPageName
description: Créez un nom de page facile à lire à partir du chemin d’accès au site Web actuel.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Module externe Adobe : getPageName

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getPageName` module externe crée une version formatée facile à lire et conviviale de l’URL actuelle. Adobe recommande d’utiliser ce module externe si vous souhaitez définir une [`pageName`](../page-vars/pagename.md) valeur facile à comprendre dans les  de. Ce module externe n’est pas nécessaire si vous disposez déjà d’une structure d’appellation pour la `pageName` variable, par exemple via une couche de données. Il est préférable de l’utiliser lorsque vous n’avez pas d’autre solution pour définir la `pageName` variable.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe   une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l&#39; [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Catalog] bouton
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si vous ne l’avez pas déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   *  : Core - Bibliothèque chargée (Haut de la page)
1. Ajouter une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser getPageName
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous l’extension Adobe Analytics.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getPageName` méthode utilise les arguments suivants :

* **`si`** (facultatif, chaîne) : ID inséré au début de la chaîne représentant l’ID du site. Cette valeur peut être un ID numérique ou un nom convivial. Lorsqu’elle n’est pas définie, elle est définie par défaut sur le domaine actif.
* **`qv`** (facultatif, chaîne) : Un délimité par des virgules de paramètres de chaîne de  qui, s’il se trouve dans l’URL, sont ajoutés à la chaîne
* **`hv`** (facultatif, chaîne) : délimité par des virgules de paramètres trouvés dans le hachage d’URL qui, s’il est trouvé dans l’URL, sont ajoutés à la chaîne
* **`de`** (facultatif, chaîne) : Délimiteur permettant de séparer des parties individuelles de la chaîne. Valeur par défaut de la barre verticale (`|`).

La méthode renvoie une chaîne contenant une version au format convivial de l’URL. Cette chaîne est généralement attribuée à la `pageName` variable, mais elle peut également être utilisée dans d’autres variables.

## Exemples d’appels

### Exemple n° 1

Si l&#39;URL actuelle était...

```js
https://mail.google.com/mail/u/0/#inbox
```

...et le code suivant s&#39;exécute...

```js
s.pageName = getPageName()
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Exemple n° 2

Si l&#39;URL actuelle était...

```js
https://mail.google.com/mail/u/0/#inbox
```

...et le code suivant s&#39;exécute...

```js
s.pageName = getPageName("gmail")
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "gmail|mail|u|0";
```

### Exemple n° 3

Si l&#39;URL actuelle était...

```js
https://www.google.com/
```

...et le code suivant s&#39;exécute...

```js
s.pageName = getPageName()
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "www.google.com|home"
```

**Remarque**: Lorsque le code s’exécute sur une URL qui ne contient pas de chemin d’accès, il ajoute toujours la valeur &quot;home&quot; à la fin de la valeur renvoyée.

### Exemple n° 4

Si l&#39;URL actuelle était...

```js
https://www.google.com/
```

...et le code suivant s&#39;exécute...

```js
s.pageName = getPageName("google","","","|")
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "google|home"
```

### Exemple n° 5

Si l&#39;URL actuelle était...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...et le code suivant s&#39;exécute...

```js
s.pageName = getPageName()
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Cependant, si le code suivant s’exécute à la place...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...la valeur finale de s.pageName sera :

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Mise à niveau à partir des versions précédentes

La version 4.0+ du plug-in getPageName ne dépend pas de l’existence de l’objet AppMeasurement d’Adobe Analytics (c.-à-d. l’objet &quot;s&quot;) à exécuter.  Si vous choisissez d’effectuer la mise à niveau vers cette version, veillez à modifier le code qui appelle le module en supprimant toutes les instances de l’objet &quot;s&quot; de l’appel.
Par exemple, modifiez ceci :

```js
s.pageName = s.getPageName();
```

...à ceci :

```js
s.pageName = getPageName();
```

## Historique des versions

### 4.1 (17 septembre 2019)

* Modification de la valeur du délimiteur par défaut en un caractère barre verticale (deux-points + espace).

### 4.0 (22 mai 2018)

* Réanalyse/réécriture complète du module externe
