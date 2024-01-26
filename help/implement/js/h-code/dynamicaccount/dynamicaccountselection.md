---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection active ou désactive la sélection de comptes dynamiques.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont pas prises en charge dans les bibliothèques d’AppMeasurements actuelles ou dans la collecte de données Adobe Experience Platform.

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
