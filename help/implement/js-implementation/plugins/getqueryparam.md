---
description: Renvoie la valeur du paramètre de chaîne de requête spécifié, s’il figure dans l’URL de la page en cours. Des données importantes (codes de suivi de campagne, mots-clés de recherche interne, etc.) sont disponibles dans la chaîne de requête d’une page. Aussi,  getQueryParam vous aide-t-il à les capturer dans des variables Analytics.
keywords: Mise en œuvre d’Analytics
seo-description: Renvoie la valeur du paramètre de chaîne de requête spécifié, s’il figure dans l’URL de la page en cours. Des données importantes (codes de suivi de campagne, mots-clés de recherche interne, etc.) sont disponibles dans la chaîne de requête d’une page. Aussi,  getQueryParam vous aide-t-il à les capturer dans des variables Analytics.
seo-title: getQueryParam
solution: Analytics
subtopic: Modules externes
title: getQueryParam
topic: Développeur et mise en œuvre
uuid: ba 202756-c 728-4 ebc -8 fd 9-5 bc 29 a 9 f 673 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getQueryParam

Renvoie la valeur du paramètre de chaîne de requête spécifié, s’il figure dans l’URL de la page en cours. Des données importantes (codes de suivi de campagne, mots-clés de recherche interne, etc.) sont disponibles dans la chaîne de requête d’une page. Aussi,  getQueryParam vous aide-t-il à les capturer dans des variables Analytics.

>[!IMPORTANT]
>
>Ce plug-in est utilisé par le code H uniquement. [Appmeasurement pour JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) fournit cette fonctionnalité nativement à l'aide [d'Util. getqueryparam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. Le module externe détecte la chaîne de requête spécifiée, le cas échéant, et renseigne sa valeur dans la variable choisie. Si aucun paramètre de chaîne de requête n’est détecté avec cette valeur, une chaîne vide est renvoyée. If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

If you wanted to use *`s.campaign`* to capture campaign tracking codes available as values of the *`cid`* query parameter, you would enter the following in the *`doPlugins()`* function in your [!DNL AppMeasurement] for JavaScript code:

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. Vous pouvez le constater à l’aide du débogueur [!DNL DigitalPulse], lequel doit afficher *v0=123456* dans le cadre de la demande d’image.

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. Vous pouvez les remplacer par tout paramètre de chaîne de requête existant sur votre site.

Le module externe *`getQueryParam`* compte deux arguments (options) supplémentaires que vous pouvez utiliser pour capturer des données dans des variables Analytics :

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

Si *p* est une liste de paramètres de chaîne de requête et que plusieurs paramètres de ce type figurent dans l’URL, toutes les valeurs sont renvoyées dans une liste séparée par le délimiteur, *d*, lequel peut-être un seul caractère ou une chaîne, comme par exemple « : » (espace-deux-points-espace). Si *d* est omis, aucun délimiteur n’est utilisé entre les valeurs. S’il convient d’affecter la priorité à un paramètre de chaîne de requête par rapport à un autre, utilisez une instruction *if*, comme illustré ci-dessous.

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

Depuis la version v2.0 de *`getQueryParam`*, le module externe accepte un troisième argument facultatif, *u*, qui vous permet d’indiquer l’URL à partir de laquelle vous souhaitez extraire des paramètres de chaîne de requête. Par défaut (c’est-à-dire si le troisième argument n’est pas renseigné), le module externe utilise l’URL de la page. Si vous souhaitez, par exemple, extraire une chaîne de requête du référent, vous pouvez utiliser le code suivant :

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

L’indicateur « f » doit être utilisé dans ce troisième argument avec des cadres lorsque le paramètre de chaîne de requête nécessaire figure dans la barre d’adresse plutôt que dans l’URL du cadre en cours :

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

Lorsque vous utilisez des cadres et le paramètre *f*, il est conseillé d’employer le module externe *`getValOnce`* pour éviter que le code de suivi de campagne ne soit envoyé avec chaque page vue.

>[!NOTE]
>
>Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

**Code du module externe**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```

