---
description: Les modules externes AppMeasurement pour JavaScript sont des programmes ou des fonctions qui effectuent plusieurs fonctions avancées.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Utilisation des modules d’implémentation
topic: Developer and implementation
uuid: 7ffcfe89-b7e2-45e4-b771-942d5ae07c39
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# Utilisation des modules d’implémentation

Les plug-ins sont des fragments de code qui exécutent plusieurs fonctions avancées pour faciliter la mise en oeuvre d’Analytics.

Ces modules externes étendent les capacités de votre fichier JavaScript en apportant des fonctionnalités qui ne sont pas disponibles avec l’implémentation de base. Adobe propose de nombreux autres modules dans le cadre de solutions avancées. Contactez votre gestionnaire de compte si vous souhaitez capturer des données à l’aide de JavaScript, mais ne savez pas comment procéder.

JavaScript plug-ins are usually called by the doPlugins function, which is executed when the `t` method is called in the Code to Paste.

Par conséquent, si vous définissez une variable dans la fonction *`doPlugins`*, vous risquez d’en remplacer une que vous avez définie sur la page HTML. La seule fois où la fonction*`doPlugins`* n’est pas appelée est lorsque la variable [!UICONTROL usePlugins] est définie sur « false ».

## Exemple de code {#section_6940FD16F2E94753A1C39694D0CF5FBA}

L’exemple de code ci-dessous montre à quoi ressemble la fonction *`doPlugins`*dans votre fichier JavaScript :

AppMeasurement pour JavaScript:

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
}
```

Code H :

```js
/* Plugin Config */
s.usePlugins=true
function s_doPlugins(s) {
 /* Add calls to plug-ins here */
}
s.doPlugins=s_doPlugins
```

> [!NOTE] Le code H et les versions antérieures utilisent une syntaxe différente pour la prise en charge de navigateurs très anciens (tels que Microsoft IE 4 et 5).

## Changement du nom de la fonction doPlugins {#section_70B7D58E057B48058E25907AB3726725}

La fonction *`doPlugins`*est généralement appelée*`s_doPlugins`*. Dans certains cas (en général, lorsque plusieurs versions du code peuvent apparaître sur une seule page), il se peut que le nom de la fonction *`doPlugins`*soit modifié. S’il s’avère nécessaire de renommer la fonction*`doPlugins`* standard pour éviter des conflits, attribuez-lui le nom de fonction correct *`doPlugins`*, comme illustré ci-dessous.

```js
/* Plugin Config */
s_mc.usePlugins=true
function s_mc_doPlugins(s_mc) {
 /* Add calls to plug-ins here */
}
s_mc.doPlugins=s_mc_doPlugins
```

## Utilisation de la fonction doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

La fonction *`doPlugins`*permet d’attribuer facilement des valeurs à des variables ou d’extraire des valeurs de[!UICONTROL paramètres de chaîne de requête]sur n’importe quelle page du site. L’utilisation de*`doPlugins`* se révèle généralement plus facile que de renseigner des valeurs dans la page HTML, dans la mesure où un seul fichier doit être mis à jour. Gardez à l’esprit que les modifications apportées au fichier JavaScript sont parfois différées. Les visiteurs récurrents sur votre site utilisent souvent des versions en cache du fichier JavaScript. Il se peut donc que les mises à jour du fichier ne soient pas appliquées immédiatement à tous les visiteurs ; il peut parfois s’écouler un mois avant leur application.

L’exemple suivant illustre l’utilisation de la fonction *`doPlugins`*pour définir une valeur par défaut pour une variable et pour obtenir une valeur à partir de la chaîne de requête.

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
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
/* You may insert any plug-ins you wish to use here.                 */
/*
 * Plugin: getQueryParam 1.3 - Return query string parameter values
 */
s.getQueryParam=new Function("qp","d",""
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l"
//
// ... more code below ...
//
```

