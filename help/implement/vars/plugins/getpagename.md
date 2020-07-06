---
title: getPageName
description: Permet de créer un pageName facile à lire à partir du chemin d’accès au site web actuel.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 100%

---


# Plug-in Adobe : getPageName

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPageName` crée une version formatée facile à lire et conviviale de l’URL actuelle. Adobe recommande d’utiliser ce plug-in si vous souhaitez une valeur [`pageName`](../page-vars/pagename.md) facile à définir et à comprendre dans les rapports. Ce plug-in n’est pas nécessaire si vous disposez déjà d’une structure d’appellation pour la variable `pageName`, par exemple via une couche de données. Il est préférable de l’utiliser lorsque vous n’avez pas d’autre solution pour définir la variable `pageName`.

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
   * Type d’action : initialisation de getPageName
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
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getPageName` utilise les arguments suivants :

* **`si`** (facultatif, chaîne) : identifiant inséré au début de la chaîne représentant l’identifiant du site. Cette valeur peut être un identifiant numérique ou un nom convivial. Lorsqu’elle n’est pas définie, elle prend par défaut le domaine actuel.
* **`qv`** (facultatif, chaîne) : liste, délimitée par des virgules, de paramètres de chaîne de requête qui, s’ils figurent dans l’URL, sont ajoutés à la chaîne.
* **`hv`** (facultatif, chaîne) : liste, délimitée par des virgules, de paramètres trouvés dans le hachage de l’URL qui, s’ils figurent dans l’URL, sont ajoutés à la chaîne.
* **`de`** (facultatif, chaîne) : délimiteur permettant de séparer les différentes parties de la chaîne. Par défaut, il s’agit d’une barre verticale (`|`).

La méthode renvoie une chaîne contenant une version formatée de l’URL. Cette chaîne est généralement attribuée à la variable `pageName`, mais peut également être utilisée dans d’autres variables.

## Exemples d’appels

### Exemple 1

Si l’URL actuelle était…

```js
https://mail.google.com/mail/u/0/#inbox
```

…et que le code suivant s’exécute…

```js
s.pageName = getPageName()
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Exemple 2

Si l’URL actuelle était…

```js
https://mail.google.com/mail/u/0/#inbox
```

…et que le code suivant s’exécute…

```js
s.pageName = getPageName("gmail")
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "gmail|mail|u|0";
```

### Exemple 3

Si l’URL actuelle était…

```js
https://www.google.com/
```

…et que le code suivant s’exécute…

```js
s.pageName = getPageName()
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "www.google.com|home"
```

**Remarque** : lorsque le code s’exécute sur une URL qui ne contient pas de chemin d’accès, il ajoute toujours la valeur de « home » à la fin de la valeur renvoyée.

### Exemple 4

Si l’URL actuelle était…

```js
https://www.google.com/
```

…et que le code suivant s’exécute…

```js
s.pageName = getPageName("google","","","|")
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "google|home"
```

### Exemple 5

Si l’URL actuelle était…

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

…et que le code suivant s’exécute…

```js
s.pageName = getPageName()
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Cependant, si le code suivant s’exécute à la place…

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

…alors la valeur finale de s.pageName est :

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Mise à niveau par rapport aux versions précédentes

La version 4.0+ du plug-in getPageName ne dépend pas de l’existence de l’objet AppMeasurement d’Adobe Analytics (soit l’objet « s ») pour fonctionner.  Si vous choisissez d’effectuer la mise à niveau vers cette version, veillez à modifier le code qui appelle le plug-in en supprimant toutes les instances de l’objet « s » de l’appel.
Par exemple, modifiez ceci :

```js
s.pageName = s.getPageName();
```

…par cela :

```js
s.pageName = getPageName();
```

## Historique des versions

### 4.1 (17 septembre 2019)

* Modification de la valeur du délimiteur par défaut en une barre verticale (de deux points + espace).

### 4.0 (22 mai 2018)

* Réanalyse/réécriture complète du plug-in.
