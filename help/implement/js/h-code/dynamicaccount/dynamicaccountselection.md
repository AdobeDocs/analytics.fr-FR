---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection active ou désactive la sélection de compte dynamique.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: 'https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%
---
# dynamicAccountSelection

>[!IMPORTANT]
>
>Les comptes dynamiques sont uniquement pris en charge à l’aide des mises en œuvre JavaScript héritées (code H). Ces variables ne sont actuellement pas prises en charge dans les bibliothèques AppMeasurement ou la collecte de données Adobe Experience Platform.

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
