---
title: doPlugins
description: Permet de configurer la logique juste avant qu’un accès ne soit compilé et envoyé à Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 100%

---


# doPlugins

La variable `doPlugins` agit comme un « dernier appel » pour définir des valeurs dans votre mise en œuvre. Si l(option [`usePlugins`](../config-vars/useplugins.md) est activée, celle-ci s’exécute automatiquement juste avant que n’importe quel type de demande d’image ne soit compilé et envoyé à Adobe, notamment :

* Tous les appels de page vue ([`t()`](t-method.md))
* Tous les appels de suivi de liens ([`tl()`](tl-method.md)), y compris les liens de téléchargement et de sortie automatiques

Utilisez la variable `doPlugins` pour appeler le code du plug-in et définir les valeurs des variables finales juste avant la compilation et l’envoi d’une demande d’image à Adobe.

## Plug-ins dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.doPlugins dans AppMeasurement et le code personnalisé de Launch

Définissez la variable `s.doPlugins` sur une fonction contenant le code souhaité. La fonction s’exécute automatiquement lorsque vous effectuez un appel de suivi.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Définissez une fonction sur la variable `doPlugins` une seule fois dans votre mise en œuvre. Si vous définissez la variable `doPlugins` plusieurs fois, seul le code le plus récent est utilisé.

## Exemples

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
> Les versions précédentes d’AppMeasurement comportaient un code légèrement différent `doPlugins()`. Adobe recommande d’utiliser le format ci-dessus (bonne pratique).
