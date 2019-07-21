---
description: Les modules externes JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.
keywords: Mise en œuvre d’Analytics
seo-description: Les modules externes JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.
seo-title: Appel des modules externes avec la fonction doplugins
solution: Analytics
subtopic: Modules externes
title: Appel des modules externes avec la fonction doplugins
topic: Développeur et mise en œuvre
uuid: 95 dd 01 de -8136-4 ec 9-aac 9-4 a 3 d 5371 b 839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Appel des modules externes avec la fonction doplugins

Les modules externes JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## Exemple de code {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

AppMeasurement pour JavaScript :

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

Code H :

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>Le code H et les versions antérieures utilisent une syntaxe différente pour prendre en charge certains navigateurs très anciens (tels que IE 4 et 5).

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## Utilisation de la fonction doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* La fonction permet d'attribuer facilement des valeurs aux variables ou d'extraire des valeurs des paramètres de chaîne [!UICONTROL de requête] sur n'importe quelle page du site. Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. Gardez à l’esprit que les modifications apportées au fichier JavaScript sont parfois différées. Les visiteurs récurrents sur votre site utilisent souvent des versions en cache du fichier JavaScript. Il se peut donc que les mises à jour du fichier ne soient pas appliquées immédiatement à tous les visiteurs ; il peut parfois s’écouler un mois avant leur application.

L’exemple suivant illustre l’utilisation de la fonction *`doPlugins`* pour définir une valeur par défaut pour une variable et pour obtenir une valeur à partir de la chaîne de requête.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## Modules externes installés {#section_C5494347D85940A78670032199787CD0}

Pour déterminer si un module externe est inclus dans votre fichier JavaScript et est prêt à l’emploi, accédez à la section [!UICONTROL Plugins Section] du fichier JavaScript. L’exemple suivant illustre la fonction [!UICONTROL getQueryParam].

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

