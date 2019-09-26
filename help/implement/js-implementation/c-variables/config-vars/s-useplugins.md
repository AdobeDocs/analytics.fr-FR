---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

Lorsque [!UICONTROL usePlugins] a la valeur "true", la *`s_doPlugins`* fonction est appelée avant chaque demande d’image.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | N/D | True |

## Syntaxe et valeurs possibles

```js
s.usePlugins=true|false
```

La variable [!UICONTROL usePlugins] doit être définie sur « true » ou « false ».

## Exemples

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

La variable [!UICONTROL usePlugins] doit être définie sur « false » (ou ne pas être déclarée) si la fonction *`s_doPlugins`* function is not declared in your JavaScript file.

## Paramètres de configuration

Aucun