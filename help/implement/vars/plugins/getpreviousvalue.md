---
title: getPreviousValue
description: Permet de récupérer la dernière valeur transmise dans une variable.
feature: Variables
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 97%

---

# Plug-in Adobe : getPreviousValue

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getPreviousValue` vous permet de définir une variable sur une valeur déterminée lors d’un précédent accès. Ce plug-in n’est pas nécessaire si votre mise en œuvre contient toutes les valeurs souhaitées dans l’accès actif.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getPreviousValue
1. Save and publish the changes to the rule.-->

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
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
