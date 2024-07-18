---
title: decodeLinkParameters
description: Activez ou désactivez l’AppMeasurement des variables de suivi des liens à double codage.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 8%

---

# decodeLinkParameters

La variable `decodeLinkParameters` est une valeur booléenne qui détermine si les variables de suivi des liens sont codées une fois (si elles sont définies sur `true`) ou deux fois (si elles sont définies sur `false`). Elle n’a un impact que sur `linkName` (faisant partie de la méthode [`tl()`](../functions/tl-method.md)) et [`linkURL`](linkurl.md). Il nécessite l’utilisation de l’AppMeasurement v2.24.0 ou version ultérieure. La valeur par défaut de cette variable est `false`.

Dans les versions d’AppMeasurement antérieures à la version 2.24.0, les variables de suivi des liens étaient toujours codées deux fois dans l’URL. Bien qu’il ne s’agisse pas d’un problème pour les implémentations qui reposent généralement sur des caractères à un octet, le codage double a créé des valeurs incorrectement codées pour les caractères à plusieurs octets dans les rapports. La définition de cette variable sur `true` code une fois les valeurs de suivi des liens, ce qui correspond généralement au comportement souhaité.

* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que les variables de suivi des liens sont décodées par URL pour compenser le double codage de l’AppMeasurement, définissez cette variable sur `false`. Cette valeur conserve les fonctionnalités d’AppMeasurement existantes.
* Si votre mise en oeuvre utilise des caractères à plusieurs octets et que vous ne décodez pas les valeurs de suivi des liens, Adobe recommande de définir cette variable sur `true`.
* Si votre mise en oeuvre n’utilise pas de caractères à plusieurs octets, cette variable n’est pas requise. Cependant, Adobe recommande de définir cette variable sur `true` dans les cas où des caractères à plusieurs octets peuvent être envoyés.

## Double encodage des paramètres de lien à l’aide du SDK Web

Cette variable est spécifique à l’AppMeasurement et n’est nécessaire dans aucun type d’implémentation du SDK Web.

## Codage double des paramètres de lien à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.decodeLinkParameters dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.decodeLinkParameters` est une valeur booléenne qui détermine si les valeurs de suivi des liens sont codées deux fois. Si cette variable n’est pas définie, sa valeur par défaut est `false` pour préserver les fonctionnalités des implémentations existantes. Adobe recommande de définir cette valeur sur `true` pour toutes les nouvelles implémentations, en particulier si des valeurs codées URL apparaissent dans les rapports de suivi de liens.

```js
s.decodeLinkParameters = true;
```
