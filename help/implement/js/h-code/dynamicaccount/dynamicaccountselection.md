---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection active ou désactive la sélection de comptes dynamiques.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques AppMeasurement ou la collecte de données Adobe Experience Platform actuelles.

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
