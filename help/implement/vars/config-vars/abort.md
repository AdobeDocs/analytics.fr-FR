---
title: abort
description: La variable abort est une valeur booléenne qui empêche l’envoi d’un accès aux serveurs de collecte de données Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# abort

La variable `abort` est une valeur booléenne qui peut empêcher l’envoi de l’appel de suivi suivant à Adobe.

## Utilisation de la variable abort dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## Syntaxe AppMeasurement et éditeur de code personnalisé dans Launch

La variable `abort` est une valeur booléenne. Sa valeur par défaut est `false`.

* Si celle-ci est définie sur `true`, l’appel de suivi suivant ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) n’envoie aucune donnée à Adobe.
* Si celle-ci est définie sur `false` ou non définie, cette variable ne fait rien.

```js
s.abort = true;
```

>[!NOTE] La variable `abort` est réinitialisée à `false` après chaque appel de suivi. Si vous devez abandonner les appels de suivi suivants sur la même page, définissez de nouveau `abort` sur `true`.

## Exemple

La variable `abort` peut être définie dans la fonction [`doPlugins()`](../functions/doplugins.md), qui est la dernière fonction à exécuter avant l’envoi d’une demande d’image à Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Vous pouvez centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.
