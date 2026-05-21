---
title: decodeLinkParameters
description: Activez ou désactivez les variables de suivi des liens de double codage AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 8%

---

# decodeLinkParameters

La variable `decodeLinkParameters` est une valeur booléenne qui détermine si les variables de suivi des liens sont codées une fois (si elles sont définies sur `true`) ou deux fois (si elles sont définies sur `false`). Cela n’affecte que les `linkName` (qui font partie de la méthode [`tl()`](../functions/tl-method.md)) et les [`linkURL`](linkurl.md). AppMeasurement version 2.24.0 ou ultérieure est nécessaire pour l’utiliser. La valeur par défaut de cette variable est `false`.

Dans les versions d’AppMeasurement antérieures à la version v2.24.0, les variables de suivi des liens étaient toujours codées en URL deux fois. Bien que cela ne pose pas de problème pour les implémentations qui reposent généralement sur des caractères codés sur un seul octet, le codage double a créé des valeurs incorrectement codées pour les caractères codés sur plusieurs octets dans les rapports. La définition de cette variable sur `true` encode les valeurs de suivi des liens une fois, ce qui est généralement le comportement souhaité.

* Si votre implémentation utilise des caractères multi-octet et que les variables de suivi des liens sont décodées par URL pour compenser le double codage AppMeasurement, définissez cette variable sur `false`. Cette valeur permet de conserver les fonctionnalités AppMeasurement existantes.
* Si votre implémentation utilise des caractères multi-octet et que vous n’utilisez pas de valeurs de suivi des liens de décodage d’URL, Adobe recommande de définir cette variable sur `true`.
* Si votre implémentation n’utilise pas de caractères multi-octet, cette variable n’est pas obligatoire. Cependant, Adobe recommande de définir cette variable sur `true` dans les cas où des caractères multi-octet peuvent être envoyés.

## Paramètres de lien de double encodage à l’aide de la SDK Web

Cette variable est spécifique à AppMeasurement et n’est nécessaire dans aucun type d’implémentation de Web SDK.

## Double codage des paramètres de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.decodeLinkParameters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.decodeLinkParameters` est une valeur booléenne qui détermine si les valeurs de suivi des liens sont codées en double. Si cette variable n’est pas définie, sa valeur par défaut est `false` pour conserver la fonctionnalité pour les implémentations existantes. Adobe recommande de définir cette valeur sur `true` pour toutes les nouvelles implémentations de , en particulier si vous voyez des valeurs codées URL dans les rapports de suivi des liens.

```js
s.decodeLinkParameters = true;
```
