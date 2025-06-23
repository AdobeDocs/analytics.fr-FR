---
title: getPreviousValue
description: Permet de récupérer la dernière valeur transmise dans une variable.
feature: Appmeasurement Implementation
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 77%

---

# Plug-in Adobe : getPreviousValue

{{plug-in}}

Le plug-in `getPreviousValue` vous permet de définir une variable sur une valeur déterminée lors d’un précédent accès. Ce plug-in n’est pas nécessaire si votre mise en œuvre contient toutes les valeurs souhaitées dans l’accès actif.

## Installation du plug-in à l’aide de l’extension Web SDK

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Web SDK.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** à gauche, puis sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** à gauche, puis sur l’onglet **[!UICONTROL Catalogue]**
1. Recherchez et installez l’extension **[!UICONTROL Plug-ins Web SDK courants]**.
1. Cliquez sur **[!UICONTROL Éléments de données]** à gauche, puis sur l’élément de données de votre choix.
1. Définissez le nom de l’élément de données de votre choix avec la configuration suivante :
   * Extension : plug-ins Web SDK courants
   * Élément de données : `getPreviousValue`
1. Définissez les paramètres souhaités sur la droite.
1. Enregistrez et publiez les modifications apportées à l’élément de données.

## Installation du plug-in implémentant manuellement le SDK Web

Ce plug-in n’est pas encore pris en charge pour une utilisation dans le cadre d’une implémentation manuelle de Web SDK.

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
   * Type d’action : initialisation de getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getPreviousValue` utilise les arguments suivants :

* **`v`** (chaîne, obligatoire) : variable dont la valeur doit être transmise à la demande d’image suivante. Une variable courante utilisée est `s.pageName` pour obtenir la valeur de la page précédente.
* **`c`** (chaîne, facultatif) : nom du cookie qui stocke la valeur.  Si cet argument n’est pas défini, il prend par défaut la valeur `"s_gpv"`.

Lorsque vous appelez cette fonction, elle renvoie la valeur de la chaîne contenue dans le cookie. Le plug-in réinitialise ensuite l’expiration du cookie, et lui attribue la valeur de variable de l’argument `v`. Le cookie expire après 30 minutes d’inactivité.

## Exemples

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## Spécificités peu communes

Si la variable associée à lʼargument `v` est définie sur une nouvelle valeur et que le plug-in `getPreviousValue` sʼexécute MAIS quʼun appel au serveur Analytics nʼest PAS envoyé en même temps, la nouvelle valeur de lʼargument `v` est toujours considérée comme la « valeur précédente » lors de la prochaine exécution du plug-in.
Supposons, par exemple, que le code suivant s’exécute sur la première page de la visite :

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Ce code génère un appel au serveur dans lequel la valeur de `pageName` est « Home » et prop7 nʼest pas défini.  Cependant, lʼappel à `getPreviousValue` enregistre la valeur de `pageName` dans le cookie `gpv_Page`. Supposons quʼimmédiatement après, sur la même page, le code suivant soit exécuté :

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Comme la fonction `t()` ne sʼexécute pas dans ce bloc de code, aucune autre demande dʼimage nʼest envoyée.  Cependant, si le code de la fonction `getPreviousValue` sʼexécute cette fois-ci, `prop7` est défini sur la valeur précédente de `pageName` (« Home »), puis enregistre la nouvelle valeur de `pageName` (« New value ») dans le cookie `gpv_Page`. Supposons ensuite que le visiteur accède à une autre page et que le code suivant sʼexécute sur cette page :

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Lorsque la fonction `t()` sʼexécute, elle crée une demande dʼimage dans laquelle la valeur de `pageName` est « Page 2 » et celle de `prop7` est « New value », qui était la valeur de `pageName` lorsque le dernier appel à `getPreviousValue` a eu lieu. La valeur `prop7` de `"Home"` nʼa jamais été contenue dans une demande dʼimage, même si « Home » était la première valeur transmise à `pageName`.

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### v2.0 (7 octobre 2019)

* Nouvelle version (réécriture complète de la logique).
