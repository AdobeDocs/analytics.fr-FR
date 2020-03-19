---
title: avorter
description: La variable abort est une valeur booléenne qui empêche l’envoi d’un accès aux serveurs de collecte de données Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# avorter

La `abort` variable est une valeur booléenne qui peut empêcher l’envoi de l’appel de suivi suivant à Adobe.

## Utilisation de la variable abort dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## Syntaxe AppMeasurement et éditeur de code personnalisé dans Launch

La `abort` variable est une valeur booléenne. Its default value is `false`.

* S’il est défini sur `true`, l’appel de suivi suivant ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) n’envoie aucune donnée à Adobe.
* Si elle est définie sur `false` ou non, cette variable ne fait rien.

```js
s.abort = true;
```

> [!NOTE] La `abort` variable est réinitialisée `false` après chaque appel de suivi. Si vous devez abandonner les appels de suivi suivants sur la même page, définissez `abort` sur `true` à nouveau.

## Exemple

La `abort` variable peut être définie dans la [`doPlugins()`](../functions/doplugins.md) fonction, qui est la dernière fonction à exécuter avant l’envoi d’une demande d’image à Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Vous pouvez centraliser la logique que vous utilisez pour identifier les   que vous ne souhaitez pas suivre, comme certains liens personnalisés ou externes dans les publicités affichées.
