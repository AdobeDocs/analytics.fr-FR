---
title: doPlugins
description: Configurez la logique juste avant qu’un accès ne soit compilé et envoyé à Adobe.
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# doPlugins

La `doPlugins` variable agit comme un &quot;dernier appel&quot; pour définir des valeurs dans votre implémentation. Le cas `usePlugins` échéant, `true`elle s’exécute automatiquement juste avant que n’importe quel type de demande d’image ne soit compilé et envoyé à Adobe, notamment :

* Tous les appels de page vue (`t`)
* Tous les appels de suivi de liens (`tl`), y compris les liens de téléchargement et de sortie automatiques

Utilisez la `doPlugins` variable pour appeler le code du module externe et définir les valeurs des variables finales juste avant la compilation et l’envoi d’une demande d’image à Adobe.

## Modules externes dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.doPlugins dans AppMeasurement et lancement du code personnalisé

Définissez la `s.doPlugins` variable sur une fonction contenant le code souhaité. La fonction s’exécute automatiquement lorsque vous effectuez un appel de suivi.

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] Définissez une fonction sur la `doPlugins` variable une seule fois dans votre implémentation. Si vous définissez la `doPlugins` variable plusieurs fois, seul le code le plus récent est utilisé.

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

> [!NOTE] Les versions précédentes d’AppMeasurement comportaient un code légèrement différent `doPlugins()` . Adobe recommande d’utiliser le format ci-dessus comme pratique recommandée.
