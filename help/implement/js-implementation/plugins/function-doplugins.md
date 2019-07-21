---
description: Les modules externes JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.
keywords: Mise en œuvre d’Analytics
seo-description: Les plug-ins JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.
seo-title: Fonction doPlugins
solution: Analytics
subtopic: Modules externes
title: Fonction doPlugins
topic: Développeur et mise en œuvre
uuid: 367 d 5550-f 8 e 2-477 d -8681-18 ae 9665 d 699
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Fonction doPlugins

Les modules externes JavaScript sont généralement appelés par la fonction doPlugins, elle-même exécutée lorsque la fonction t() est appelée dans le code à insérer.

Par conséquent, si vous définissez une variable dans la fonction `doPlugins`, vous risquez d’en remplacer une que vous avez définie sur la page HTML. The only time the `doPlugins` function is not called is when the *`usePlugins`* variable is set to `false`.

**Exemple de code**

The `doPlugins` function is typically called `s_doPlugins`. Dans certains cas cependant (en général, lorsque plusieurs versions du code [!DNL Analytics] peuvent apparaître sur une seule page), vous pouvez renommer la fonction `doPlugins`. If the standard `doPlugins` function needs to be renamed to avoid conflicts, assign `doPlugins` the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**Utilisation de la fonction doPlugins**

Cette fonction permet d’attribuer facilement des valeurs à des variables ou d’extraire des valeurs depuis des paramètres de chaîne de requête sur n’importe quelle page du site. Utiliser la fonction `doPlugins` peut se révéler plus facile que de renseigner des valeurs dans la page HTML, dans la mesure où un seul fichier doit être mis à jour. Les modifications apportées au fichier JavaScript sont parfois différées. Les visiteurs récurrents sur votre site utilisent souvent des versions en cache du fichier JavaScript. Il se peut donc que les mises à jour du fichier ne soient pas appliquées immédiatement à tous les visiteurs ; il peut parfois s’écouler un mois avant leur application.

L’exemple suivant illustre l’utilisation de la fonction `doPlugins` pour définir une valeur par défaut pour une variable et pour obtenir une valeur à partir de la chaîne de requête.

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**Modules externes installés**

Pour savoir si un module externe est inclus dans votre fichier JavaScript et s’il est prêt à l’emploi, rendez-vous dans la [!UICONTROL section Plugins] du fichier en question. L’exemple ci-dessous illustre la fonction `getQueryParam` telle qu’elle se présente dans la [!UICONTROL section Plugins].

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

