---
title: doubleEncodeLinkParameters
description: Activez ou désactivez les variables de suivi des liens de double codage d’AppMeasurement.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# doubleEncodeLinkParameters

Le `doubleEncodeLinkParameters` est une valeur booléenne qui détermine si les variables de suivi de liens sont codées une seule fois (si la variable est définie sur `false`) ou deux (si la variable est définie sur `true`). Cela n’a d’impact que `linkName` (partie de la variable [`tl()`](../functions/tl-method.md) ) et [`linkURL`](linkurl.md). Il nécessite l’AppMeasurement 2.23.1 ou supérieur à utiliser. La valeur par défaut de cette variable est `true`.

Dans les versions précédentes d’AppMeasurement, les variables de suivi des liens étaient toujours codées deux fois dans l’URL. Bien qu’il ne s’agisse pas d’un problème pour les implémentations qui reposent généralement sur des caractères à un octet, le codage double a créé des valeurs incorrectement codées pour les caractères à plusieurs octets dans les rapports. Définir cette variable sur `false` code une seule fois les valeurs de suivi des liens, ce qui correspond généralement au comportement souhaité.

* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que les variables de suivi des liens sont décodées au moyen d’une URL pour compenser le double codage de l’AppMeasurement, définissez cette variable sur `true`. Cette valeur conserve les fonctionnalités d’AppMeasurement existantes.
* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que vous ne décodez pas les valeurs de suivi des liens, Adobe recommande de définir cette variable sur `false`.
* Si votre mise en oeuvre n’utilise pas de caractères à plusieurs octets, cette variable n’est pas requise. Cependant, Adobe recommande de définir cette variable sur `false` dans les cas où des caractères à plusieurs octets peuvent être envoyés.

## Double encodage des paramètres de lien à l’aide du SDK Web

Cette variable est spécifique à l’AppMeasurement et n’est nécessaire dans aucun type d’implémentation du SDK Web.

## Codage double des paramètres de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.doubleEncodeLinkParameters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Le `s.doubleEncodeLinkParameters` est une valeur booléenne qui détermine si les valeurs de suivi des liens sont codées deux fois. Si cette variable n’est pas définie, sa valeur par défaut est `true` pour préserver les fonctionnalités des implémentations existantes. Adobe recommande de définir cette valeur sur `false` pour toutes les nouvelles implémentations, en particulier si des valeurs codées URL s’affichent dans les rapports de suivi des liens.

```js
s.doubleEncodeLinkParameters = false;
```
