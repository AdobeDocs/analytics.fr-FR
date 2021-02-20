---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection active ou désactive la sélection de comptes dynamiques.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 100%

---


# dynamicAccountSelection

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement actuelles ou dans Adobe Experience Platform Launch.

La variable `dynamicAccountSelection` est une valeur booléenne qui détermine si la sélection de compte dynamique est utilisée.

S’il est défini sur `true`, le fichier JavaScript examine `dynamicAccountMatch` et `dynamicAccountList`.

Si cette variable est définie sur `false`, ou si elle n’est pas définie, les variables `dynamicAccountMatch` et `dynamicAccountList` sont ignorées.

Si cette variable n’est pas définie, la valeur par défaut est `false`.

## Syntaxe

```js
s.dynamicAccountSelection = [boolean];
```

## Exemple

```js
s.dynamicAccountSelection = true;
```
