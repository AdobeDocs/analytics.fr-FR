---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection active ou désactive la sélection de comptes dynamique.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] Les comptes dynamiques sont uniquement pris en charge à l’aide des implémentations JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans le lancement d’Adobe Experience Platform.

La `dynamicAccountSelection` variable est une valeur booléenne qui détermine si la sélection de compte dynamique est utilisée.

S’il est défini sur `true`, le fichier JavaScript examine `dynamicAccountMatch` et `dynamicAccountList`.

Si cette variable est définie sur `false`, ou si elle n’est pas définie, les variables `dynamicAccountMatch` et `dynamicAccountList` sont ignorées.

Si cette variable n’est pas définie, la valeur par défaut est `false`.

## du lien personnalisé

```js
s.dynamicAccountSelection = [boolean];
```

## Exemple

```js
s.dynamicAccountSelection = true;
```
