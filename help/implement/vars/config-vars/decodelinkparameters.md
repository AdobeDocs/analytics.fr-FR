---
title: decodeLinkParameters
description: Activez ou désactivez les variables de suivi des liens de double codage d’AppMeasurement.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: e666a2efae01bad3cc3ccc5c8bfafe009a429588
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# decodeLinkParameters

Le `decodeLinkParameters` est une valeur booléenne qui détermine si les variables de suivi de liens sont codées une seule fois (si la variable est définie sur `true`) ou deux (si la variable est définie sur `false`). Cela n’a d’impact que `linkName` (partie de la variable [`tl()`](../functions/tl-method.md) ) et [`linkURL`](linkurl.md). Il nécessite l’AppMeasurement 2.24.0 ou supérieur à utiliser. La valeur par défaut de cette variable est `false`.

Dans les versions précédentes d’AppMeasurement, les variables de suivi des liens étaient toujours codées deux fois dans l’URL. Bien qu’il ne s’agisse pas d’un problème pour les implémentations qui reposent généralement sur des caractères à un octet, le codage double a créé des valeurs incorrectement codées pour les caractères à plusieurs octets dans les rapports. Définir cette variable sur `true` code une seule fois les valeurs de suivi des liens, ce qui correspond généralement au comportement souhaité.

* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que les variables de suivi des liens sont décodées au moyen d’une URL pour compenser le double codage de l’AppMeasurement, définissez cette variable sur `false`. Cette valeur conserve les fonctionnalités d’AppMeasurement existantes.
* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que vous ne décodez pas les valeurs de suivi des liens, Adobe recommande de définir cette variable sur `true`.
* Si votre mise en oeuvre n’utilise pas de caractères à plusieurs octets, cette variable n’est pas requise. Cependant, Adobe recommande de définir cette variable sur `true` dans les cas où des caractères à plusieurs octets peuvent être envoyés.

## Double encodage des paramètres de lien à l’aide du SDK Web

Cette variable est spécifique à l’AppMeasurement et n’est nécessaire dans aucun type d’implémentation du SDK Web.

## Codage double des paramètres de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.decodeLinkParameters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Le `s.decodeLinkParameters` est une valeur booléenne qui détermine si les valeurs de suivi des liens sont codées deux fois. Si cette variable n’est pas définie, sa valeur par défaut est `false` pour préserver les fonctionnalités des implémentations existantes. Adobe recommande de définir cette valeur sur `true` pour toutes les nouvelles implémentations, en particulier si des valeurs codées URL s’affichent dans les rapports de suivi des liens.

```js
s.decodeLinkParameters = true;
```